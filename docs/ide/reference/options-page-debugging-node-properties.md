---
title: Stránka Možnosti, vlastnosti uzlu ladění | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
ms.assetid: 564cc8b2-0084-420e-b560-200cc5621a7e
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 40589b9d429d1d405e09d51ae76ddd8786b78a78
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="options-page-debugging-node-properties"></a>Stránka Možnosti, vlastnosti uzlu ladění
Následující tabulky popisují stránky (nebo vlastnosti kolekce), jsou přidružené **ladění** kategorie, `DTE.Properties("Debugging", <Property Page>)` z **možnosti** dialogové okno.  
  
## <a name="general"></a>Obecné  
 `DTE.Properties("Debugging", "General")`  
  
|Název položky vlastnosti|Hodnota|Popis|  
|------------------------|-----------|-----------------|  
|PromptOnBreakpointDelete|Get/Set (Boolean)|Určuje, zda ladicí program vyzve k zadání oprávnění před odstraněním všechny zarážky v projektu.|  
|BreakAllProcesses|Get/Set (Boolean)|Určuje, zda ladicího programu dělí všechny procesy vždy, když dělí jeden proces.|  
|BreakAtBoundaries|Get/Set (Boolean)|Určuje, jestli ladicího programu dělí spuštění, když výjimku překračuje ohraničení mezi domén nebo mezi spravovaná a nativní kód.|  
|EnableAddressLevelDebugging|Get/Set (Boolean)|Určuje, zda jsou povoleny funkce ladění adresu úrovni.|  
|ShowDisassemblyIfNoSource|Get/Set (Boolean)|Určuje, zda ladicí program zobrazí zpětný překlad kódu, když není k dispozici zdrojového kódu.|  
|EnableBreakpointFilters|Get/Set (Boolean)|Určuje, zda je povoleno filtrování zarážek.|  
|EnableExceptionAssistant|Get/Set (Boolean)|Určuje, jestli Pomocník pro výjimky se používá pro spravované výjimky.|  
|UnwindCallstack|Get/Set (Boolean)|Určuje, zda ladicího programu unwinds zásobníku volání pro k neošetřené výjimce.|  
|EnableJustMyCode|Get/Set (Boolean)|Určuje, jestli je povolená pouze můj kód pro C# a kód jazyka Visual Basic.|  
|ShowAllMembers|Get/Set (Boolean)|Pro jiné uživatelské objekty Určuje, zda ladicí program zobrazí všechny členy objekt ve windows proměnné. Tato možnost nemá žádný vliv, pokud je povoleno pouze můj kód.|  
|WarnIfNoUserCode|Get/Set (Boolean)|Určuje, zda ladicí program vydá upozornění, když se uživatel pokusí připojit k procesu, který nemá žádný kód uživatele. Tato možnost nemá žádný vliv, pokud je povoleno pouze můj kód.|  
|EnablePropertyEvaluation|Get/Set (Boolean)|Určuje, zda ladicí program automaticky vyhodnotí vlastnosti a funkce implicitní volá ve spravovaném kódu.|  
|CallStringConversion|Get/Set (Boolean)|Určuje, zda ladicí program implicitně volá funkci pro převod řetězců na objekty ve windows proměnné.|  
|EnableSourceServer|Get/Set (Boolean)|Určuje, jestli může ladicího programu přístupového kódu ze zdrojového serveru.|  
|PrintSourceServerDiagnostics|Get/Set (Boolean)|Určuje, zda ve výstupním okně zobrazí diagnostické zprávy týkající se na zdrojovém serveru. Tato možnost nemá žádný vliv, pokud je povolen přístup zdrojového serveru.|  
|HighlightEntireLine|Get/Set (Boolean)|Určuje, zda ladicího programu označuje celý řádek pro zarážky a aktuální příkaz.|  
|RequireSourceToMatch|Get/Set (Boolean)|Určuje, jestli ladicí program vyžaduje zdrojové soubory tak, aby přesně odpovídaly původní verze při otevření soubory pro ladění.|  
|RedirectOutputToImmediate|Get/Set (Boolean)|Určuje, zda je výstup – okno výstup přesměrován na hodnot proměnných.|  
|ShowRawVariableStructure|Get/Set (Boolean)|Určuje, zda se zobrazí objekty ve windows proměnné v základním formátu.|  
|SuppressJitOptimization|Get/Set (Boolean)|Pro spravovaný kód určuje, zda je potlačeno optimalizace za běhu pomocí ladicího programu.|  
|WarnIfNoSymbols|Get/Set (Boolean)|Určuje, zda ladicí program zobrazí upozornění, pokud jsou k dispozici žádné symboly pro ladění, při spuštění procesu.|  
|WarnIfScriptDisabled|Get/Set (Boolean)|Určuje, zda ladicí program zobrazí upozornění, pokud skript není povoleno ladění při spuštění procesu.|  
|ShowMarkersForAllThreads|Get/Set (Boolean)|Určuje, zda ladicí program zobrazí značky přístup z více vláken.|  
|StepOverPropertiesAndOperators|Get/Set (Boolean)|Určuje, jestli má krok přes operátory ve spravovaném kódu pouze a vlastnosti.|  
  
## <a name="edit-and-continue"></a>Upravit a pokračovat  
 `DTE.Properties("Debugging", "EditAndContinue")`  
  
|Název položky vlastnosti|Hodnota|Popis|  
|------------------------|-----------|-----------------|  
|EnableEditAndContinue|Get/Set (Boolean)|Určuje, zda je povoleno upravit a pokračovat. Tato možnost se vztahuje na všechny jazyky, které podporují upravit a pokračovat.|  
|InvokedByCommands|Get/Set (Boolean)|Určuje, zda upravit a pokračovat automaticky provede změny kódu po klepnutí na příkaz ladění, jako **krok** nebo **pokračovat**. Tato možnost se vztahuje pouze na nativní kód.|  
|InvokedByCommandsAskFirst|Get/Set (Boolean)|Určuje, zda upravit a pokračovat vyzve uživatele k oprávnění použít změny kódu, když uživatel vybere ladění příkaz například **krok** nebo **pokračovat**. Tato možnost se vztahuje pouze na nativní kód.|  
|WarnAboutStaleCode|Get/Set (Boolean)|Určuje, zda ladicí program vydá upozornění při spuštění kódu zastaralé nebo zastaralé, povedou upravit a pokračovat. Tato možnost se vztahuje pouze na nativní kód.|  
|RelinkChangesOnStop|Get/Set (krátký)|Určuje, zda Visual Studio relinks použít tak, upravit a pokračovat při spuštění aplikace zastavení změn kódu. Tato možnost se vztahuje pouze na nativní kód.|  
|AllowPrecompiling|Get/Set (krátký)|Určuje, jestli je dovoleno upravit a pokračovat načíst předkompilovaných hlaviček na pozadí. Tato možnost se vztahuje pouze na nativní kód.|  
  
## <a name="just-in-time"></a>za běhu  
 `DTE.Properties("Debugging", "JustInTime")`  
  
|Název položky vlastnosti|Hodnota|Popis|  
|------------------------|-----------|-----------------|  
|JitManaged|Get/Set (Boolean)|Určuje, zda je povoleno ladění JIT pro spravovaný kód.|  
|JitNative|Get/Set (Boolean)|Určuje, zda je povoleno ladění JIT pro nativní kód.|  
|JitScript|Get/Set (Boolean)|Určuje, zda je povoleno ladění JIT pro kód skriptu.|  
  
## <a name="native"></a>Nativní  
 `DTE.Properties("Debugging", "Native")`  
  
|Název položky vlastnosti|Hodnota|Popis|  
|------------------------|-----------|-----------------|  
|LoadDllExports|Get/Set (Boolean)|Určuje, zda ladicí program načte tabulky export knihovny DLL.|  
|EnableRPC|Get/Set (Boolean)|Určuje, zda lze do modelu COM vzdálených volání procedur krok ladicího programu.|  
  
## <a name="see-also"></a>Viz také  
 [Ovládání možnosti nastavení](http://msdn.microsoft.com/Library/a09ed242-7494-4cde-bbd1-7a8ec617965d)   
 [Určení názvů vlastností položky na stránkách možnosti](http://msdn.microsoft.com/Library/d450422d-47c7-4eeb-9f9f-3286264bc5aa)   
 [Stránka Možnosti, písma a barvy vlastnosti uzlu](../../ide/reference/options-page-fonts-and-colors-node-properties.md)   
 [Stránka Možnosti, vlastnosti uzlu textového editoru](../../ide/reference/options-page-text-editor-node-properties.md)   
 [Obecné, ladění, dialogové okno Možnosti](../../debugger/general-debugging-options-dialog-box.md)   
 [Upravit a pokračovat, ladění, dialogové okno Možnosti](http://msdn.microsoft.com/Library/009d225f-ef65-463f-a146-e4c518f86103)   
 [V běhu, ladění, dialogové okno Možnosti](../../debugger/just-in-time-debugging-options-dialog-box.md)