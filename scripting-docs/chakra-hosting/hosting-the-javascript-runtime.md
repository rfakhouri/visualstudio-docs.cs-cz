---
title: Hostování prostředí JavaScript Runtime | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30ec744e-57cc-4ef5-8fe1-d2c27b946548
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2bf213bf262ede7642e05c66e424b860238dc57f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789267"
---
# <a name="hosting-the-javascript-runtime"></a>Hostování prostředí JavaScript Runtime
JavaScript Runtime (JsRT) rozhraní API pro stolní počítače, Windows Store a serverové aplikace spuštěné na operačním systému Windows pro přidání možností skriptování do aplikace pomocí založených na standardech Chakra JavaScript modulem, který je také poskytnout způsob využívaných Microsoft Edge a prohlížeče Internet Explorer. Tato rozhraní API jsou k dispozici ve Windows 10 a všechny verze operačního systému Windows, který má Internet Explorer verze 11.0 nainstalovat na počítač. Další informace najdete v tématu [odkazy (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md). Informace o používání JsRT v aplikacích pro Windows Store najdete v tématu [JsRT a univerzální platformu Windows](#Windows).  
  
> [!NOTE]
>  Tato dokumentace předpokládá obecné pracovní znalost jazyka JavaScript.  
  
## <a name="concepts"></a>Koncepty  
 Vědět, jak k hostování modul jazyka JavaScript pomocí rozhraní API JsRT závisí na dvě klíčové koncepty: moduly runtime a provádění kontexty.  
  
 A *runtime* představuje dokončení prostředí pro spuštění JavaScript. Každý modul runtime, který je vytvořen má svou vlastní izolované paměti haldy shromážděných a ve výchozím nastavení, vlastní za běhu (JIT) vlákna kompilátoru a systém uvolňování paměti (GC) přístup z více vláken. *Kontext spuštění* představuje prostředí JavaScript, který se liší od jiných kontextech provádění vlastní globální objekt jazyka JavaScript. Jeden modul runtime může obsahovat více kontexty spuštění a v takových případech všechny kontexty provádění sdílet JIT kompilátoru a globální Katalog vlákno související s modulem runtime.  
  
 Moduly runtime představují jedním vláknem a provádění. Pouze jeden modul runtime, která může být aktivní na konkrétní vlákno najednou a modul runtime může být pouze na jedno vlákno aktivní najednou. Moduly runtime jsou pronájem zřetězený, takže modul runtime, který není aktuálně aktivní na vlákno (tj. není spuštěný žádný kód JavaScript nebo reagovat na všechny volání z hostitele) lze použít na všechny vlákno, které na ní ještě nemá aktivní modulu runtime.  
  
 Kontexty spouštění, jsou svázané s konkrétní runtime a spouštění kódu v rámci tohoto modulu runtime. Na rozdíl od moduly runtime může být více kontexty provádění aktivní na vlákno ve stejnou dobu. Aby hostitel provádět volání do kontextu spuštění, tento kontext spuštění můžete volat zpět na hostitele a hostitele moci volat v kontextu provádění různých.  
  
 ![Více kontexty provádění](../chakra-hosting/media/js-chakra-hosting.png "JS_Chakra_Hosting")  
  
 V praxi Pokud hostitel musí spuštění kódu v oddělených prostředí kontext provádění jedné lze použít. Podobně pokud je nutné v hostiteli zároveň běželo víc částí kódu, jeden modul runtime je dostačující.  
  
## <a name="memory-management"></a>Správa paměti  
 JavaScript je jazyk uvolnění z paměti, a proto nejsou několik hledisek, které musí být uloženy v paměti při práci s rozhraními API JsRT z jiný jazyk.  
  
 Hlavní aspekt spočívá v uvolňování JavaScript lze zobrazit pouze odkazy na hodnoty na dvou místech: halda jeho runtime a zásobníku. Proto bude odkaz na hodnotu JavaScript, která je uložená v rámci jiné hodnoty JavaScript, nebo v místní proměnné v zásobníku vidět vždy modulem garbage collector. Ale nedostupné uvolňování odkazy, které jsou uložené v jiných umístěních, jako je například haldách spravovat hostitele nebo systému a může vést k předčasnému kolekce hodnot, které se používají pro hostitele.  
  
> [!IMPORTANT]
>  Některé kompilátory jazyka (například Visual Studio C++ compiler) bude optimalizovat tokeny lokální proměnné, kde je to možné. Musí být dbát na to, že lokální proměnné, které odkazují na JavaScript hodnoty jsou v zásobníku, pokud se očekává se, že tyto hodnoty – udržování připojení.  
  
 Pokud odkaz na hodnotu JavaScript se uloží v umístění nejsou viditelné v rámci systému uvolňování paměti, musí ručně přidat a odebrat odkazy pomocí rozhraní API JsRT hostitele.  
  
## <a name="exception-handling"></a>Zpracování výjimek  
 Když při provádění skriptu dojde k výjimce jazyka JavaScript, obsahující runtime je uvést do stavu k výjimce. V výjimka stavu, můžete spustit žádný kód a všechna volání rozhraní API selže s kódem chyby `JsErrorInExceptionState` dokud hostitel načítá a vymaže výjimky pomocí `JsGetAndClearException` rozhraní API. Pokud hostitel vrátí ze zpětného volání, JavaScript bez vymazání runtime ze stavu výjimky, pak výjimce jazyka JavaScript bude znovu také ovládací prvek předává zpět modul JavaScript. To také umožňuje zpětná volání hostitele a "výjimku" výjimce jazyka JavaScript pomocí nastavení modulu runtime do stavu výjimky a pak vrácení ze zpětného volání, hostitele.  
  
 Hostitel není povoleno umožníte její vlastní interní výjimky rozšíří na hostiteli zpětné volání – všechny metody zpětného volání musí catch všechny hostitele výjimky před vrácením řízení modulu runtime.  
  
## <a name="runtime-resource-usage"></a>Využití prostředků modulu runtime  
 Rozhraní API JsRT vystavit počet způsob, jak sledovat a upravit způsob, moduly runtime používat prostředky. Obecně selhání do následujících kategorií:  
  
-   **Přístup z více vláken využití**. Ve výchozím nastavení vytvoří každé runtime vyhrazené vlákna kompilátoru JIT a vyhrazené vlákno globálního katalogu, které služba tohoto modulu runtime. Pokud je vytvořen runtime s `JsRuntimeAttributeDisableBackgroundWork` příznak, pak pracovní JIT a globální Katalog se provede na vlákno runtime místo vlákna na pozadí samostatné pro každou z nich. Hostitel může taky poskytovat přístup z více vláken zpětné volání služby k `JsCreateRuntime` volání, které vám umožní hostitele do plánování práce JIT a globální Katalog žádným způsobem považuje za vhodné.  
  
-   **Využití paměti**. Existuje několik způsobů monitorování a upravit využití paměti modulu runtime. Pokud bude modul runtime spuštěna po dlouhou dobu, můžete zadat hostitele `JsRuntimeAttributeEnableIdleProcessing` příznak při vytváření modulu runtime a pak zavolají `JsIdle` když hostitel je ve stavu nečinnosti. To umožňuje modul odložení některé pracovní paměti čištění a účetnictví až do doby nečinnosti.  
  
     Hostitele můžete monitorovat kolekce voláním `JsSetRuntimeBeforeCollectCallback`. Můžete také sledovat přidělení provedené halda voláním `JsSetRuntimeMemoryAllocationCallback`. Všimněte si, že toto rozhraní API není zpětné volání při každé JavaScript přidělení, stačí, když modul runtime haldy vyžaduje více místa, ze kterého chcete přidělit. Zpětné volání přidělení paměti je povoleno tak, aby odepřel požadavek, který aktivuje uvolnění paměti a, pokud je k dispozici, není dostatek paměti nedostatku paměti v modulu runtime.  
  
     Hostitele lze také zavolat `JsSetRuntimeMemoryLimit` můžete použít pro nastavení limitu pro velikost paměti modulu runtime. Pokud se modul runtime dotkne omezení, spustí uvolnění paměti a pokud je k dispozici žádné paměti, bude vyvolána nedostatku paměti modulem runtime.  
  
-   **Skript přerušení a vyhodnocení**. Můžete volat hostitele `JsDisableRuntimeExecution` ukončit spuštění v rámci modulu runtime. Toto volání lze kdykoli a z libovolného vlákna. Vzhledem k tomu, že skript ukončení závisí na dosažení ochrana body vložit do kódu, skript nemusí ukončit přesně v okamžiku, ale bude jím velmi krátké později. Koncové body ochrana ve výchozím nastavení jsou umístěny v generovaný kód můžete a nemusí zahrnovat všechny situace, jako je například nekonečné smyčce. Vytváření modulu runtime s `JsRuntimeAttributeAllowScriptInterrupt` příznak způsobí, že modul runtime, chcete-li vložit další kontroly pro nekonečné smyčky, často za cenu malé zatížení.  
  
     Pokud hostitel chce zakáže generování nativního kódu kompilátorem JIT, můžete zadat `JsRuntimeAttributeDisableNativeCodeGeneration` příznak. Hostitele lze také zakáže dynamicky spuštění skriptů skripty samotné zadáním `JsRuntimeAttributeDisableEval` příznak.  
  
## <a name="debugging-and-profiling"></a>Ladění a profilování  
 Rozhraní API JsRT podporuje ladění a profilování prostřednictvím technologie aktivní skriptování.  
  
 Od verze Windows 10, modul JavaScript Chakra podporuje, starší modul a modul okraj a můžete vybrat buď v JsRT (viz [cílení na Edge vs. Starší moduly](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md) podrobnosti). Ladění skriptu v sadě Visual Studio funguje jinak mezi starší verze a modul okraj. S modulem starší verze, musí hostitel znát zajistit [idebugapplication – rozhraní](../winscript/reference/idebugapplication-interface.md) ukazatele, který můžete získat [iprocessdebugmanager – rozhraní](../winscript/reference/iprocessdebugmanager-interface.md) instance. S modulem Edge `IDebugApplication` je zastaralý a Chakra povolí nativní modul a skriptu schopnosti ladění pomocí ladicího programu sady Visual Studio bez nutnosti implementace `IDebugApplication` od uživatele.  
  
 Chcete-li skripty v kontextu provádění debuggable, je modul Chakra přejít k používání méně efektivní provádění metody kódu. Jako takový debuggable obvykle spuštění kódu pomaleji než-debuggable kódu. V důsledku toho se modulem starší verze hostitele můžete buď spustit ladění v kontextu provádění od začátku tím, že poskytuje `IDebugApplication` ukazatel předem pomocí `JsCreateContext`, nebo můžete Počkejte, dokud ladění je potřeba a pak zavolají `JsStartDebugging`. S modulem Edge `JsCreateContext` už trvá `IDebugApplication` parametr, a výsledkem je skript debuggable až po `JsStartDebugging` je volána. Při ladění pomocí sady Visual Studio, musí být povolena možnost ladicí program "Skript".  
  
 Kód jazyka JavaScript v kontextu spuštění můžete profilovaným v jednom ze dvou způsobů. Příkazového řádku Visual Studio Profiler (vsperf.exe) můžete použít ve Windows 8.1 a novější verze s přepínačem /js k vytvoření sestavy s cílem spustit kód jazyka JavaScript v aplikaci. Nebo můžete volat přímo hostitele `JsStartProfiling` a `JsStopProfiling` a poskytování zpětné volání udělat profilace sám sebe. Hostitele můžete také zkontrolovat stav shromážděných halda paměti voláním `JsEnumerateHeap`. Profilace v JsRT funguje stejným způsobem jako mezi starší verze a modul okraj. Nicméně, profilace API JsRT (`JsStartProfiling`, `JsStopProfiling`, `JsEnumerateHeap`, a `JsIsEnumeratingHeap`) nejsou k dispozici pro univerzální aplikace pro Windows.  
  
<a name="Windows"></a>   
## <a name="jsrt-and-the-universal-windows-platform"></a>JsRT a univerzální platformu Windows  
 Rozhraní API JsRT můžete použít pro přidání možností skriptování do aplikace pro univerzální Windows. Bude nutné aplikaci Universal Windows, která používá rozhraní API JsRT cílové rozhraní API JSRT Edge zase cíle modul Chakra okraj. Další informace najdete v tématu [cílení na Edge vs. Starší moduly](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md). Dokončení rozhraní API JsRT je k dispozici pro univerzální aplikace pro Windows, s výjimkou profilování a haldy podporu – výčet (`JsStartProfiling`, `JsStopProfiling`, `JsEnumerateHeap`, a `JsIsEnumeratingHeap` nepodporují).  
  
 JsRT také umožňuje skripty, které nativně získat přístup k žádnému [univerzální platformu Windows (UWP) rozhraní API](https://msdn.microsoft.com/en-us/library/windows/apps/br211377.aspx) po vystavení obor názvů rozhraní API prostřednictvím rozhraní API JsRT Edge `JsProjectWinRTNamespace`. Zatímco univerzální aplikace Windows vyžadují žádné nastavení kromě plánování nezbytné obory názvů v aplikaci Windows Classic (Win32), inicializace knihovny COM delegovaný čerpací mechanismus musí být povoleno v `JsSetProjectionEnqueueCallback` povolit událostí a Asynchronní rozhraní API. Následující ukázka Win32 využívá asynchronní UWP rozhraní API pro vytvoření klientem http získat obsah z identifikátoru Uri:  
  
```cpp  
typedef struct _jsCall {  
    JsProjectionCallback jsCallback;  
    JsProjectionCallbackContext jsContext;  
    HANDLE event;  
} jsCall;  
  
// Set up delegated pumping mechanism; not necessary in UWP applications.  
jsCall outstandingCall = {};  
CoInitializeEx(nullptr, COINIT_MULTITHREADED);  
JsSetProjectionEnqueueCallback([](JsProjectionCallback jsCallback,   
JsProjectionCallbackContext jsContext, void *callbackState) {  
    jsCall* call = (jsCall*)callbackState;  
    call->jsCallback = jsCallback;  
    call->jsContext = jsContext;  
    SetEvent(call->event);  
    },  
&outstandingCall);  
HANDLE event = CreateEventEx(NULL, NULL, CREATE_EVENT_MANUAL_RESET, EVENT_ALL_ACCESS);  
outstandingCall.event = event;  
  
// Project necessary namespaces.  
JsProjectWinRTNamespace(L"Windows.Foundation");  
JsProjectWinRTNamespace(L"Windows.Web");  
  
// Get content from an Uri.  
JsRunScript(L"var uri = new Windows.Foundation.Uri(\"http://somedatasource.com\"); " \  
    L"var httpClient = new Windows.Web.Http.HttpClient();" \  
    L"httpClient.getStringAsync(uri).done(function (content) { " \  
    L"    // do something with the string content " \    
    L"}, onError); " \  
    L"function onError(reason) { " \  
    L"    // error handling " \        
    L"}",   
    currentSourceContext, L"", &result);  
  
// Wait for async call to come in and then execute; not necessary in UWP applications.  
WaitForSingleObjectEx(outstandingCall.event, 10000, FALSE) == WAIT_OBJECT_0;  
outstandingCall.jsCallback(outstandingCall.jsContext);  
  
```  
  
## <a name="see-also"></a>Viz také  
 [JavaScript Runtime – ukázková aplikace](http://go.microsoft.com/fwlink/p/?LinkID=306674&clcid=0x409)   
 [Referenční dokumentace (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)   
 [JavaScript Runtime – hostování](../chakra-hosting/javascript-runtime-hosting.md)