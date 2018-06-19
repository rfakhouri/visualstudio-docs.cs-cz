---
title: Cílení na Edge vs. Starší moduly v rozhraních API JsRT | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cbc7df6c-0bc9-48f5-b9ad-b9ed31c42f92
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 50947cbd619f086daecc1e09f88a4b238a36ee41
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789270"
---
# <a name="targeting-edge-vs-legacy-engines-in-jsrt-apis"></a>Cílení na Edge vs. Starší moduly v rozhraních API JsRT
Od verze Windows 10, jednu z těchto změn, které jsme provedli Chakra (JavaScript stroj), který je v souladu s Windows 10 prohlížeče strategie podporu nový modul vykreslování okraj, je podpora dva různé stroje Chakra:  
  
-   Modul staré Chakra (označované taky jako *starší modul* nebo jscript9.dll níže), je dodáván s a podporuje aplikace Internet Explorer 11. Tento modul není aktivní v čase a zůstane zásadně neliší od verze Win8.1 nebo IE11.  
  
-   Nový modul Chakra (označované taky jako *Edge modul* nebo chakra.dll níže), je dodáván s a podporuje nový prohlížeč v systému Windows 10, Microsoft Edge. Tento modul bude průběžně aktualizovat a bude podporovat "živé" [Edge](http://blogs.msdn.com/b/ie/archive/2014/11/11/living-on-the-edge-our-next-step-in-interoperability.aspx) modul. Životností Edge modul znamená, že na rozdíl od modul starší modul okraj nebude přenášet jakoukoli formu funkce skriptu Správa verzí, který se přidá do.  
  
 Při vytváření aplikace pomocí jazyka JavaScript Runtime hostování (JsRT) rozhraní API, můžete cílit na starší verze nebo modul okraj.  
  
-   Pokud potřebujete zdůraznil zpětná kompatibilita existující aplikace, cílí na starší verze modulu.  
  
-   Pokud chcete aplikaci, kterou chcete být dopředného vyhledávání a podpora nové JavaScript funkce jako jejich vydání (například ECMAScript 6), cílové modul okraj.  
  
 Toto téma obsahuje informace, které popisují, jak mít jiné moduly.  
  
## <a name="target-your-preferred-version"></a>Cíl Upřednostňovaná verze  
 Při vytváření aplikace, můžete vybrat verzi JsRT, který podporuje modul Edge nebo modul starší verze. Můžete použít verzi JsRT podle výše uvedených pokynů. Abychom vyhověli tyto rozdíly, byly provedeny následující změny k `JsCreateRuntime`, `JsCreateContext`, a `JsStartDebugging`.  
  
 Pro `JsCreateRuntime`:  
  
-   Pokud je cílem modul starší verze `JsRuntimeVersionEdge` hodnota výčtu je zastaralá a navrhne zprávu pomocí `JsRuntimeVersionInternetExplorer11` místo hodnoty.  
  
-   Pokud je cílem modul okraj, je vynechaný parametr verze `JsCreateRuntime` funkce.  
  
    ```cpp  
    JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);  
    ```  
  
 Pro `JsCreateContext` a `JsStartDebugging`:  
  
-   Pokud je cílem modul starší verze `IDebugApplication` rozhraní slouží k poskytování vlastních metod bez vzdáleného ladění. Pro účely ladění `JsCreateContext` a `JsStartDebugging` funkce přebírat `IDebugApplication` jako parametr.  
  
-   Pokud je cílem modul Edge `IDebugApplication` rozhraní je zastaralé. Chakra modul umožňuje nativní a ladění schopností pomocí ladicího programu sady Visual Studio bez nutnosti implementace skriptů `IDebugApplication` od uživatele. Rozhraní je už parametr pro `JsCreateContext` a `JsStartDebugging` v důsledku.  
  
 Podpisy pro předchozí rozhraní API v starší modul jsou následující:  
  
```cpp  
JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsRuntimeVersion version, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);  
  
JsErrorCode JsCreateContext(JsRuntimeHandle runtime, IDebugApplication *debugApplication, JsContextRef *newContext);  
  
JsErrorCode JsStartDebugging(IDebugApplication *debugApplication);  
```  
  
 Podpisy pro předchozí rozhraní API v rámci stroje hraniční jsou následující:  
  
```cpp  
JsErrorCode JsCreateRuntime(JsRuntimeAttributes attributes, JsThreadServiceCallback callback, _Out_ JsRuntimeHandle* runtime);  
  
JsErrorCode JsCreateContext(JsRuntimeHandle runtime, JsContextRef *newContext);  
  
JsErrorCode JsStartDebugging();  
```  
  
## <a name="compile-for-your-preferred-version-using-visual-c"></a>Kompilace pro vaši upřednostňované verzi pomocí Visual C++  
 Při použití Visual C++, naimportujte rozhraní API JsRT zahrnutím hlavičku jsrt.h a ujistěte se, že tento jsrt.lib je součástí vašeho seznamu vstupní soubory linkeru:  
  
```cpp  
#include <jsrt.h>  
```  
  
 ![Přidání jsrt.lib jako vstupní soubor linkeru](../chakra-hosting/media/js-chakra.png "JS_Chakra_")  
  
 Pokud chcete zacílit binární soubory modulu okraj, je třeba definovat makro `USE_EDGEMODE_JSRT` před zahrnutím jsrt.h a místo propojení proti jsrt.lib, měli byste použít propojení proti chakrart.lib:  
  
```cpp  
#define USE_EDGEMODE_JSRT  
#include <jsrt.h>  
```  
  
 ![Přidání chakrart.lib jako vstupní soubor linkeru](../chakra-hosting/media/js-chakra-hosting.png "JS_Chakra_Hosting_")  
  
 Pokud začínáte s novou aplikaci, jste nyní připraveni psaní kódu rozhraní API JsRT.  
  
## <a name="compile-for-your-preferred-version-using-net"></a>Kompilace pro vaši upřednostňované verzi pomocí rozhraní .NET  
 Pokud používáte rozhraní .NET a P/Invoke, musíte změnit vaše rozhraní API JsRT [DllImport] deklarace pro import chakra.dll místo jscript9.dll. Kromě toho změnit definici `JsCreateRuntime` odebrat `JsRuntimeVersion` parametr a definice `JsCreateContext` a `JsStartDebugging` odebrat `IDebugApplication` parametr.  
  
 Pro starší verze modulu použijte následující kód.  
  
```c#  
[DllImport("jscript9.dll")]  
public static extern JsErrorCode JsCreateRuntime(  
    JsRuntimeAttributes attributes,  
    JsRuntimeVersion version,  
    JsThreadServiceCallback callback,  
    out JsRuntimeSafeHandle runtime  
);  
  
[DllImport("jscript9.dll")]  
public static extern JsErrorCode JsCreateContext(  
    JsRuntimeSafeHandle runtime,  
    IDebugApplication debugApplication,  
    out JsContextRef newContext  
);   
  
[DllImport("jscript9.dll")]  
public static extern JsErrorCode JsStartDebugging(  
    IDebugApplication debugApplication,  
);  
```  
  
 Pro modul Edge použijte následující kód.  
  
```c#  
[DllImport("chakra.dll")]  
public static extern JsErrorCode JsCreateRuntime(  
    JsRuntimeAttributes attributes,  
    JsThreadServiceCallback callback,  
    out JsRuntimeSafeHandle runtime  
);  
  
[DllImport("chakra.dll")]  
public static extern JsErrorCode JsCreateContext(  
    JsRuntimeSafeHandle runtime,  
    out JsContextRef newContext  
);   
  
[DllImport("chakra.dll")]  
public static extern JsErrorCode JsStartDebugging();  
```  
  
> [!CAUTION]
>  Pokud jsou ručně zařazování ukazatel na funkci (například prostřednictvím LoadLibrary nebo GetProcAddress), je velmi důležité, aby nemíchat deklarace metody, jinak bude unbalance zásobníku, což bude mít za následek nepředvídatelné chování, například způsobuje vaší aplikace došlo k chybě. Ke stejnému problému dojde-li provést globální vyhledávání a nahrazování instancí jscript9.dll ve vašem kódu importu vzhledem k tomu, že budete byste zapomněli `version` parametr probíhá vyřazování.  
  
## <a name="summary"></a>Souhrn  
 Ve Windows 10 jsou rozhraní JavaScript Runtime hostování API rozdělení na dva. Tato rozhraní API teď podporují "živé" Edge modulu, jehož možnosti jazyka bude zarovnán s "živé" Edge modul v Microsoft Edge. Můžete využít tyto možnosti z plochy nebo aplikace pro Store k vytvoření nových užitečných a zajímavých způsobů, jak rozšířit vaše aplikace a využívat moderní webové znalosti základního existujícího kódu. Ale protože existují malé rozdíly v předchozích verzích, musíte být vědět následující body při cílení na Edge nebo starší verze modulu.  
  
-   Aplikace může podporovat jenom jedna verze nástroje JsRT podle procesu.  
  
     Nelze například vytvořit modulu runtime modul okraj a poté starší modul runtime a očekávat, aby se spouštěly správně v rámci jednoho procesu. Toto Nepodporovaná a může vést k nedokumentovanými chování, například selhání načíst druhý knihovnu DLL.  
  
-   Při cílení na Edge modul, vaše aplikace může neočekávaně získat nové funkce v případě základní platformě se automaticky aktualizuje.  
  
     Například aplikace Internet Explorer 11 režim starší verze modulu runtime podporuje vytváření oboru bloku deklarace proměnných, jako `let` a `const`. Pokud chování Edge modul Automatická správa verzí je standardní dříve, kód, který pracovali v režimu Internet Explorer 10, který nemá obor bloku pravidla, může spustili selhání při měl automaticky upgradován na platformu. Při výběru modelu runtime používat, musí to být zabývat. Při Věříme, že cílem by měl modul Edge, kdykoli je to možné, musí být opatrní při používání struktury kódu jazyka JavaScript, které se mohou stát v budoucnu neplatný.  
  
-   JsRT pro Windows Store podporuje pouze modul okraj (chakra.dll). Probíhá pokus o odkaz na všechny API JsRT v jscript9.dll aplikací se nezdaří certifikační.  
  
-   Je důležité Nezaměňujte deklaraci `JsCreateRuntime`, `JsCreateContext`, a `JsStartDebugging` mezi jscript9.dll a chakra.dll, protože výsledkem bude imbalancing zásobníku.  
  
     Při použití C a C++, zobrazí se chyba linkerů Pokud se pokusíte použít nesprávný deklaraci, tak dlouho, dokud nejsou to něco podobného jako volání `LoadLibrary` a potom `GetProcAddress`. Vývojáři rozhraní .NET nemusí jako snadno najít tento problém, proto zkontrolujte kódu při použití této funkce.  
  
## <a name="see-also"></a>Viz také  
 [JavaScript Runtime – hostování](../chakra-hosting/javascript-runtime-hosting.md)