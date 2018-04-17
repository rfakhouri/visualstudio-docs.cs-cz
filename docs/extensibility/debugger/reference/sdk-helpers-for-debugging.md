---
title: Pomocníci SDK pro ladění | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- dbgmetric.lib
- registry, Debugging SDK
- Debugging SDK, registry locations
- dbgmetric.h
- metrics [Debugging SDK]
ms.assetid: 80a52e93-4a04-4ab2-8adc-a7847c2dc20b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e80344b8cec1bc013e044be39638879b049c8d0a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="sdk-helpers-for-debugging"></a>Pomocníci SDK pro ladění
Tyto funkce a deklarace jsou globální podpůrné funkce pro implementaci motorů ladění, vyhodnocovače výrazů a poskytovatelé symbol v jazyce C++.  
  
> [!NOTE]
>  V tuto chvíli neexistují žádné spravované verze těchto funkcí a deklarace.  
  
## <a name="overview"></a>Přehled  
 Aby moduly ladění, vyhodnocovače výrazů a poskytovatelé symbol má být používána v sadě Visual Studio musí být zaregistrován. To se provádí nastavením registru podklíče a položky, které jsou známé jako "nastavení metriky." Následující globální funkce slouží k usnadnění procesu aktualizace tyto metriky. Najdete v části na umístění registru a zjistěte, rozložení jednotlivých podklíč registru, která se aktualizuje tyto funkce.  
  
## <a name="general-metric-functions"></a>Obecné metrika funkce  
 Toto jsou obecné funkce používané v ladění moduly. Specializované funkce pro vyhodnocovače výrazů a symbol poskytovatelé jsou podrobně popsané.  
  
### <a name="getmetric-method"></a>GetMetric – metoda  
 Načte hodnotu metriky z registru.  
  
```cpp  
HRESULT GetMetric(  
   LPCWSTR pszMachine,  
   LPCWSTR pszType,  
   REFGUID guidSection,  
   LPCWSTR pszMetric,  
   DWORD * pdwValue,  
   LPCWSTR pszAltRoot  
);  
```  
  
|Parametr|Popis|  
|---------------|-----------------|  
|pszMachine|[v] Název může být vzdáleného počítače, jehož registrace se zapíšou (`NULL` znamená místní počítač).|  
|pszType|[v] Jeden z typů metriky.|  
|guidSection|[v] Identifikátor GUID konkrétní modul, vyhodnocování, výjimky, atd. Toto nastavení určuje podčásti typ metriky pro konkrétní element.|  
|pszMetric|[v] Metrika ho získat. To odpovídá názvu konkrétní hodnotu.|  
|pdwValue|[v] Umístění úložiště s hodnotou od metriku. Existuje několik typů GetMetric, která vrací typu DWORD (jako v následujícím příkladu), BSTR, identifikátor GUID nebo pole identifikátory GUID.|  
|pszAltRoot|[v] Kořen alternativní registru používat. Nastavte na `NULL` použít výchozí nastavení.|  
  
### <a name="setmetric-method"></a>SetMetric – metoda  
 Nastaví zadanou hodnotu metriky v registru.  
  
```cpp  
HRESULT SetMetric(  
         LPCWSTR pszType,  
         REFGUID guidSection,  
         LPCWSTR pszMetric,  
   const DWORD   dwValue,  
         bool    fUserSpecific,  
         LPCWSTR pszAltRoot  
);  
```  
  
|Parametr|Popis|  
|---------------|-----------------|  
|pszType|[v] Jeden z typů metriky.|  
|guidSection|[v] Identifikátor GUID konkrétní modul, vyhodnocování, výjimky, atd. Toto nastavení určuje podčásti typ metriky pro konkrétní element.|  
|pszMetric|[v] Metrika ho získat. To odpovídá názvu konkrétní hodnotu.|  
|dwValue|[v] Umístění úložiště hodnoty v metriku. Existuje několik typů SetMetric, který může ukládat typu DWORD (v tomto příkladu), BSTR, identifikátor GUID nebo pole identifikátory GUID.|  
|fUserSpecific|[v] Hodnota TRUE, pokud metrika je specifický pro uživatele, a pokud by měly být zapsány do podregistru uživatele místo podregistr místního počítače.|  
|pszAltRoot|[v] Kořen alternativní registru používat. Nastavte na `NULL` použít výchozí nastavení.|  
  
### <a name="removemetric-method"></a>RemoveMetric – metoda  
 Odebere zadaný metrika z registru.  
  
```cpp  
HRESULT RemoveMetric(  
   LPCWSTR pszType,  
   REFGUID guidSection,  
   LPCWSTR pszMetric,  
   LPCWSTR pszAltRoot  
);  
```  
  
|Parametr|Popis|  
|---------------|-----------------|  
|pszType|[v] Jeden z typů metriky.|  
|guidSection|[v] Identifikátor GUID konkrétní modul, vyhodnocování, výjimky, atd. Toto nastavení určuje podčásti typ metriky pro konkrétní element.|  
|pszMetric|[v] Metrika odeberou. To odpovídá názvu konkrétní hodnotu.|  
|pszAltRoot|[v] Kořen alternativní registru používat. Nastavte na `NULL` použít výchozí nastavení.|  
  
### <a name="enummetricsections-method"></a>EnumMetricSections – metoda  
 Provede výčet různých oddílů metriky v registru.  
  
```cpp  
HRESULT EnumMetricSections(  
   LPCWSTR pszMachine,  
   LPCWSTR pszType,  
   GUID *  rgguidSections,  
   DWORD * pdwSize,  
   LPCWSTR pszAltRoot  
);  
```  
  
|Parametr|Popis|  
|---------------|-----------------|  
|pszMachine|[v] Název může být vzdáleného počítače, jehož registrace se zapíšou (`NULL` znamená místní počítač).|  
|pszType|[v] Jeden z typů metriky.|  
|rgguidSections|[ve out] Předběžně přidělené pole identifikátory GUID k vyplnění.|  
|pdwSize|[v] Maximální počet identifikátory GUID, které mohou být uloženy ve `rgguidSections` pole.|  
|pszAltRoot|[v] Kořen alternativní registru používat. Nastavte na `NULL` použít výchozí nastavení.|  
  
## <a name="expression-evaluator-functions"></a>Funkce vyhodnocování výrazu  
  
|Funkce|Popis|  
|--------------|-----------------|  
|GetEEMetric|Načte hodnotu metriky z registru.|  
|SetEEMetric|Nastaví zadanou hodnotu metriky v registru.|  
|RemoveEEMetric|Odebere zadaný metrika z registru.|  
|GetEEMetricFile|Získá název souboru ze zadaného metriky a načte, vrácení obsahu souboru jako řetězec.|  
  
## <a name="exception-functions"></a>Výjimky funkce  
  
|Funkce|Popis|  
|--------------|-----------------|  
|GetExceptionMetric|Načte hodnotu metriky z registru.|  
|SetExceptionMetric|Nastaví zadanou hodnotu metriky v registru.|  
|RemoveExceptionMetric|Odebere zadaný metrika z registru.|  
|RemoveAllExceptionMetrics|Odebere všechny metriky výjimky z registru.|  
  
## <a name="symbol-provider-functions"></a>Symbol funkce zprostředkovatele  
  
|Funkce|Popis|  
|--------------|-----------------|  
|GetSPMetric|Načte hodnotu metriky z registru.|  
|SetSPMetric|Nastaví zadanou hodnotu metriky v registru.|  
|RemoveSPMetric|Odebere zadaný metrika z registru.|  
  
## <a name="enumeration-functions"></a>Funkce – výčet  
  
|Funkce|Popis|  
|--------------|-----------------|  
|EnumMetricSections|Zobrazí všechny metriky pro zadaný typ metriky.|  
|EnumDebugEngine|Vytvoří výčet moduly registrované ladění.|  
|EnumEEs|Vytvoří výčet vyhodnocovače registrované výrazů.|  
|EnumExceptionMetrics|Zobrazí všechny metriky výjimka.|  
  
## <a name="metric-definitions"></a>Definice metrik  
 Tyto definice lze použít pro předdefinované metriky názvy. Názvy odpovídají různé klíče registru a názvy hodnot a jsou definovány jako řetězce široká znaková: například `extern LPCWSTR metrictypeEngine`.  
  
|Předdefinované typy metriky|Popis: Základní klíč pro...|  
|-----------------------------|---------------------------------------|  
|metrictypeEngine|Všechny ladění modul metriky.|  
|metrictypePortSupplier|Všechny metriky dodavatele portu.|  
|metrictypeException|Všechny výjimky metriky.|  
|metricttypeEEExtension|Všechna rozšíření vyhodnocování výrazu.|  
  
|Vlastnosti modulu ladění|Popis|  
|-----------------------------|-----------------|  
|metricAddressBP|Nastavte na nenulovou označíte, podporu pro adresu zarážky.|  
|metricAlwaysLoadLocal|Nastavte na nenulové hodnoty, aby bylo možné vždy načíst modul ladění místně.|  
|metricLoadInDebuggeeSession|NEPOUŽÍVÁ SE|  
|metricLoadedByDebuggee|Nastavte na udávajících modul ladění budou načteny vždy v s nebo program laděné nenulové hodnoty.|  
|metricAttach|Nastavte na nenulovou označíte, podporu pro připojení k existující programy.|  
|metricCallStackBP|Nastavte na nenulovou označíte, podporu pro zarážky zásobníku volání.|  
|metricConditionalBP|Nastavte na nenulovou indikovat podporu pro nastavení podmíněné zarážky.|  
|metricDataBP|Nastavte na nenulovou indikovat podporu pro nastavení zarážek na změny v datech.|  
|metricDisassembly|Nastavte na nenulovou udávajících podpory pro provozní výpisu zpětný překlad.|  
|metricDumpWriting|Nastavte na nenulovou označíte, podporu pro výpis zápisu (vypsání paměti na výstupní zařízení).|  
|metricENC|Nastavte na nenulovou označíte, podporu pro upravit a pokračovat. **Poznámka:** modul vlastní ladění nikdy nesmíte nastavit to nebo by měla vždycky nastavte na hodnotu 0.|  
|metricExceptions|Nastavte na nenulovou indikovat podporu pro výjimky.|  
|metricFunctionBP|Nastavte na nenulovou označíte, podporu pro pojmenované zarážky (zarážky, které rozdělit při volání určité název funkce).|  
|metricHitCountBP|Nastavte na nenulovou indikovat podporu pro nastavení "dosáhl bodu" zarážky (zarážky, které jsou spuštěny až poté, co se dosáhl stanovený počet).|  
|metricJITDebug|Nastavte na nenulovou označíte, podpora ladění za běhu (ladicí program se spustí, když dojde k výjimce v spuštěných procesů).|  
|metricMemory|NEPOUŽÍVÁ SE|  
|metricPortSupplier|Tuto možnost nastavíte na CLSID port dodavatele, pokud jeden je implementována.|  
|metricRegisters|NEPOUŽÍVÁ SE|  
|metricSetNextStatement|Nastavte na nenulové označíte, podporu pro nastavení next – příkaz (který přeskočí provádění zprostředkující příkazů).|  
|metricSuspendThread|Nastavte na nenulovou označíte, podporu pro pozastavení provádění vlákna.|  
|metricWarnIfNoSymbols|Nastavte na nenulovou indikující, že by se uživateli upozornění, pokud nejsou žádné symboly.|  
|metricProgramProvider|Tuto možnost nastavíte na CLSID program zprostředkovatele.|  
|metricAlwaysLoadProgramProviderLocal|Nastavením této hodnoty na nenulovou indikující, že poskytovatel programu by měla být vždy načíst místně.|  
|metricEngineCanWatchProcess|Tuto možnost nastavíte na nenulovou indikující, že modul ladění bude sledovat zpracování událostí místo poskytovatel programu.|  
|metricRemoteDebugging|Tuto možnost nastavíte na nenulovou označíte, podporu pro vzdálené ladění.|  
|metricEncUseNativeBuilder|Nastavením této hodnoty na nenulovou indikující, že upravit a pokračovat Manager, používejte encbuild.dll modul ladění sestavení pro upravit a pokračovat. **Poznámka:** modul vlastní ladění nikdy nesmíte nastavit to nebo by měla vždycky nastavte na hodnotu 0.|  
|metricLoadUnderWOW64|Tuto možnost nastavíte na nenulové hodnoty k označení modul ladění by měly být načteny v procesu pozastaven pod WOW při ladění proces 64-bit; modul ladění, jinak bude načten v sadě Visual Studio procesu (která je spuštěná s pověřeními WOW64).|  
|metricLoadProgramProviderUnderWOW64|Tuto možnost nastavíte na nenulovou označují, že bude poskytovatel programu načíst v procesu pozastaven při ladění 64bitového procesu v rámci WOW; jinak ji budou načteny v sadě Visual Studio procesu.|  
|metricStopOnExceptionCrossingManagedBoundary|Tuto možnost nastavíte na indikující, že proces by se měla zastavit, pokud je vyvolána neošetřená výjimka napříč hranicemi spravované nebo nespravované kód nenulové hodnoty.|  
|metricAutoSelectPriority|Tuto možnost nastavíte na prioritu pro automatický výběr stroje ladění (vyšší hodnoty rovná vyšší prioritu).|  
|metricAutoSelectIncompatibleList|Klíč registru obsahující položky, které v automatický výběr zadat identifikátory GUID pro ladění moduly budou ignorovány. Tyto položky jsou čísla (0, 1, 2 a tak dále) s identifikátorem GUID, vyjádřené jako řetězec.|  
|metricIncompatibleList|Klíč registru obsahující položky, které zadejte identifikátory GUID pro ladění moduly, které jsou kompatibilní s Tento modul ladění.|  
|metricDisableJITOptimization|Tuto možnost nastavíte na nenulovou indikující, že během ladění by mělo být zakázáno optimalizace za běhu (pro spravovaný kód).|  
  
|Vlastnosti vyhodnocování výrazu|Popis|  
|-------------------------------------|-----------------|  
|metricEngine|To obsahuje počet ladění strojů, které podporují vyhodnocení zadaného výrazu.|  
|metricPreloadModules|Tuto možnost nastavíte na nenulovou indikující, že moduly musí být předem načtena při spuštění vyhodnocení výrazu pro program.|  
|metricThisObjectName|Tuto možnost nastavíte na "Tento" název objektu.|  
  
|Vlastnosti rozšíření vyhodnocování výrazu|Popis|  
|-----------------------------------------------|-----------------|  
|metricExtensionDll|Název knihovny DLL, která podporuje tuto příponu.|  
|metricExtensionRegistersSupported|Seznam registry podporována.|  
|metricExtensionRegistersEntryPoint|Vstupní bod pro přístup k Registry.|  
|metricExtensionTypesSupported|Seznam typů podporována.|  
|metricExtensionTypesEntryPoint|Vstupní bod pro přístup k typy.|  
  
|Vlastnosti dodavatele portu|Popis|  
|------------------------------|-----------------|  
|metricPortPickerCLSID|CLSID výběr portu (dialogové okno uživatele můžete použít a porty vyberte a přidejte porty, které se použije pro ladění).|  
|metricDisallowUserEnteredPorts|Nenulové hodnoty, pokud uživatel zadal porty nelze přidat do portu dodavatele (díky tomu dialogové okno Výběr port, v podstatě jen pro čtení).|  
|metricPidBase|Základní proces ID použité dodavatelem portu při přidělování ID procesu.|  
  
|Předdefinované SP typy úložiště|Popis|  
|-------------------------------|-----------------|  
|storetypeFile|Symboly jsou uloženy v samostatném souboru.|  
|storetypeMetadata|Symboly jsou uloženy jako metadata v sestavení.|  
  
|Ostatní vlastnosti|Popis|  
|------------------------------|-----------------|  
|metricShowNonUserCode|Tuto možnost nastavíte na zobrazíte nonuser kód nenulové hodnoty.|  
|metricJustMyCodeStepping|Tuto možnost nastavíte na nenulovou indikující, že krokování může dojít pouze v uživatelského kódu.|  
|metricCLSID|CLSID pro objekt typu určité metriky.|  
|metricName|Popisný název pro objekt typu určité metriky.|  
|metricLanguage|Název jazyka.|  
  
## <a name="registry-locations"></a>Umístění registru  
 Metriky jsou číst a zapisovat do registru, konkrétně v `VisualStudio` podklíč.  
  
> [!NOTE]
>  Ve většině případů, metriky se zapíše na HKEY_LOCAL_MACHINE klíč. Někdy však HKEY_CURRENT_USER být cílový klíč. Dbgmetric.lib zpracovává oba klíče. Při získávání metriky, vyhledávání HKEY_CURRENT_USER první pak HKEY_LOCAL_MACHINE. Při nastavení metriky parametr určuje, který nejvyšší úrovně klíč se má použít.  
  
 *[klíč registru]*\  
  
 `Software`\  
  
 `Microsoft`\  
  
 `VisualStudio`\  
  
 *[kořenové verze]*\  
  
 *[metriky kořenové]*\  
  
 *[metriky typu]*\  
  
 *[metrika] = [hodnota metriky]*  
  
 *[metrika] = [hodnota metriky]*  
  
 *[metrika] = [hodnota metriky]*  
  
|Zástupný symbol|Popis|  
|-----------------|-----------------|  
|*[klíč registru]*|`HKEY_CURRENT_USER` nebo `HKEY_LOCAL_MACHINE`.|  
|*[kořenové verze]*|Verze sady Visual Studio (například `7.0`, `7.1`, nebo `8.0`). Ale tohoto kořenového adresáře můžete také změnit pomocí **/rootsuffix** přepnout **devenv.exe**. Pro VSIP, se tento modifikátor obvykle **Exp**, takže kořenu verze by, například 8.0Exp.|  
|*[metriky kořenové]*|To znamená buď `AD7Metrics` nebo `AD7Metrics(Debug)`, v závislosti na tom, jestli se používá verzi dbgmetric.lib ladění. **Poznámka:** zda dbgmetric.lib se používá, tyto zásady vytváření názvů je třeba postupovat podle Pokud máte rozdíly mezi ladění a vydání verze, které se musí projevit v registru.|  
|*[metriky typu]*|Typ Metrika se používá k zapsání: `Engine`, `ExpressionEvaluator`, `SymbolProvider`atd. Všechny jsou definované jako dbgmetric.h jako `metricTypeXXXX`, kde `XXXX` je název konkrétního typu.|  
|*[metrika]*|Název položky přiřadit hodnotu, aby tak nastavte metriku. Skutečné organizace metrik, závisí na typu metriky.|  
|*[hodnota metriky]*|Hodnotu přiřazenou metriky. Typ měli hodnota (string, počet, apod.) závisí na metriky.|  
  
> [!NOTE]
>  Všechny identifikátory GUID, které jsou uložené ve formátu `{GUID}`. Například `{123D150B-FA18-461C-B218-45B3E4589F9B}`.  
  
### <a name="debug-engines"></a>Ladění moduly  
 Toto je organizace metriku ladění moduly v registru. `Engine` je název metriky typu pro modul ladění a odpovídá *[metriky typ]* ve výše uvedené podstrom registru.  
  
 `Engine`\  
  
 *[identifikátor guid modulu]*\  
  
 `CLSID` = *[identifikátor guid třídy]*  
  
 *[metrika] = [hodnota metriky]*  
  
 *[metrika] = [hodnota metriky]*  
  
 *[metrika] = [hodnota metriky]*  
  
 `PortSupplier`\  
  
 `0` = *[port dodavatele guid]*  
  
 `1` = *[port dodavatele guid]*  
  
|Zástupný symbol|Popis|  
|-----------------|-----------------|  
|*[identifikátor guid modulu]*|Identifikátor GUID modulu ladění.|  
|*[identifikátor guid třídy]*|Identifikátor GUID třídu, která implementuje tento modul ladění.|  
|*[port dodavatele guid]*|Identifikátor GUID port dodavatele, pokud existuje. Mnoho modulů ladění použít výchozí port dodavatele a proto nezadávejte vlastní dodavatele. V tomto případě podklíč `PortSupplier` bude chybět.|  
  
### <a name="port-suppliers"></a>Port dodavatelů  
 Toto je organizace metrik dodavatele port v registru. `PortSupplier` je název metriky typu pro dodavatele port a odpovídá *[metriky typ]*.  
  
 `PortSupplier`\  
  
 *[port dodavatele guid]*\  
  
 `CLSID` = *[identifikátor guid třídy]*  
  
 *[metrika] = [hodnota metriky]*  
  
 *[metrika] = [hodnota metriky]*  
  
|Zástupný symbol|Popis|  
|-----------------|-----------------|  
|*[port dodavatele guid]*|Identifikátor GUID dodavatele portu|  
|*[identifikátor guid třídy]*|Identifikátor GUID třídy, která implementuje tento port dodavatele|  
  
### <a name="symbol-providers"></a>Zprostředkovatelé – symbol  
 Toto je organizace metrik dodavatele symbol v registru. `SymbolProvider` je název metriky typu pro zprostředkovatele symbol a odpovídá *[metriky typ]*.  
  
 `SymbolProvider`\  
  
 *[symbol zprostředkovatele guid]*\  
  
 `file`\  
  
 `CLSID` = *[identifikátor guid třídy]*  
  
 *[metrika] = [hodnota metriky]*  
  
 *[metrika] = [hodnota metriky]*  
  
 `metadata`\  
  
 `CLSID` = *[identifikátor guid třídy]*  
  
 *[metrika] = [hodnota metriky]*  
  
 *[metrika] = [hodnota metriky]*  
  
|Zástupný symbol|Popis|  
|-----------------|-----------------|  
|*[symbol zprostředkovatele guid]*|Identifikátor GUID zprostředkovatele – symbol|  
|*[identifikátor guid třídy]*|Identifikátor GUID třídy, která implementuje tohoto zprostředkovatele – symbol|  
  
### <a name="expression-evaluators"></a>Vyhodnocovače výrazů  
 Toto je organizace metriky vyhodnocování výrazu v registru. `ExpressionEvaluator` je název metriky typu pro vyhodnocovací filtr výrazů a odpovídá *[metriky typ]*.  
  
> [!NOTE]
>  Typ metriky pro `ExpressionEvaluator` není definován v dbgmetric.h, jak se předpokládá, všechny změny metriky pro vyhodnocovače výrazů bude projít funkce metriky vyhodnocování odpovídající výraz (rozložení `ExpressionEvaluator` podklíč je trochu komplikovanější, takže podrobnosti jsou skrytá uvnitř dbgmetric.lib).  
  
 `ExpressionEvaluator`\  
  
 *[jazyk guid]*\  
  
 *[identifikátor guid dodavatele]*\  
  
 `CLSID` = *[identifikátor guid třídy]*  
  
 *[metrika] = [hodnota metriky]*  
  
 *[metrika] = [hodnota metriky]*  
  
 `Engine`\  
  
 `0` = *[guid modul ladění]*  
  
 `1` = *[guid modul ladění]*  
  
|Zástupný symbol|Popis|  
|-----------------|-----------------|  
|*[jazyk guid]*|Identifikátor GUID jazyka|  
|*[identifikátor guid dodavatele]*|Identifikátor GUID dodavatele|  
|*[identifikátor guid třídy]*|Identifikátor GUID třídy, která implementuje toto vyhodnocovací filtr výrazů|  
|*[guid modul ladění]*|Identifikátor GUID modulu ladění, který tento vyhodnocovací filtr výrazů funguje s|  
  
### <a name="expression-evaluator-extensions"></a>Rozšíření vyhodnocování výrazu  
 Toto je organizace rozšíření metriky vyhodnocování výrazu v registru. `EEExtensions` je název metriky typu pro výraz rozšíření vyhodnocování a odpovídá *[metriky typ]*.  
  
 `EEExtensions`\  
  
 *[identifikátor guid rozšíření]*\  
  
 *[metrika] = [hodnota metriky]*  
  
 *[metrika] = [hodnota metriky]*  
  
|Zástupný symbol|Popis|  
|-----------------|-----------------|  
|*[identifikátor guid rozšíření]*|Identifikátor GUID rozšíření vyhodnocování výrazu|  
  
### <a name="exceptions"></a>Výjimky  
 Toto je organizace metrik výjimky v registru. `Exception` je název metriky typu výjimky a odpovídá *[metriky typ]*.  
  
 `Exception`\  
  
 *[guid modul ladění]*\  
  
 *[typy výjimek]*\  
  
 *[výjimka]*\  
  
 *[metrika] = [hodnota metriky]*  
  
 *[metrika] = [hodnota metriky]*  
  
 *[výjimka]*\  
  
 *[metrika] = [hodnota metriky]*  
  
 *[metrika] = [hodnota metriky]*  
  
|Zástupný symbol|Popis|  
|-----------------|-----------------|  
|*[guid modul ladění]*|Identifikátor GUID modulu ladění, který podporuje výjimky.|  
|*[typy výjimek]*|Obecné název podklíč identifikace třídy výjimek, které mohou být zpracovány. Typické názvů **výjimky jazyka C++**, **výjimky Win32**, **výjimky modulu CLR**, a **nativní kontroluje Run-Time**. Tyto názvy se také používají k identifikaci určité třídy výjimky pro uživatele.|  
|*[výjimka]*|Název výjimku: například **_com_error** nebo **řízení-Break**. Tyto názvy se také používají k identifikaci určité výjimky pro uživatele.|  
  
## <a name="requirements"></a>Požadavky  
 Tyto soubory jsou umístěny v [!INCLUDE[vs_dev10_ext](../../../extensibility/debugger/reference/includes/vs_dev10_ext_md.md)] adresáře instalace sady SDK (ve výchozím nastavení, *[jednotka]*\Program Files\Microsoft Visual Studio 2010 SDK\\).  
  
 Záhlaví: includes\dbgmetric.h  
  
 Knihovny: libs\ad2de.lib, libs\dbgmetric.lib  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace ke knihovně API](../../../extensibility/debugger/reference/api-reference-visual-studio-debugging.md)