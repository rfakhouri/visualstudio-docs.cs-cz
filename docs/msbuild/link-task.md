---
title: "Propojení úkolů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.ForceFileOutput
- VC.Project.VCLinkerTool.LinkStatus
- VC.Project.VCLinkerTool.CLRUnmanagedCodeCheck
- VC.Project.VCLinkerTool.SpecifySectionAttributes
- VC.Project.VCLinkerTool.SupportNobindOfDelayLoadedDLL
- VC.Project.VCLinkerTool.MinimumRequiredVersion
- VC.Project.VCLinkerTool.PerUserRedirection
- VC.Project.VCLinkerTool.CreateHotPatchableImage
- VC.Project.VCLinkerTool.DataExecutionPrevention
- VC.Project.VCLinkerTool.TreatLinkerWarningsAsErrors
- vc.task.link
- VC.Project.VCLinkerTool.ImageHasSafeExceptionHandlers
- VC.Project.VCLinkerTool.CLRSupportLastError
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild (Visual C++), Link task
- Link task (MSBuild (Visual C++))
ms.assetid: 0a61f168-3113-4fa7-83a3-d9142e2a33f8
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: a5c92a6faa558445bf85637f2e51ab7fb0e7a856
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="link-task"></a>Úloha odkazu
Zabalí nástroj linkeru jazyka Visual C++ link.exe. Nástroj linkeru propojí běžné objekt souboru formátu (COFF) objekt souborů a knihoven vytvořit soubor spustitelný soubor (.exe) nebo dynamická knihovna (DLL). Další informace najdete v tématu [možnosti Linkeru](/cpp/build/reference/linker-options).  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry **odkaz** úloh. Většina úloh parametry a několik sad parametrů, odpovídají možnosti příkazového řádku.  
  
-   **AdditionalDependencies**  
  
     Volitelné **řetězec []** parametr.  
  
     Určuje seznam vstupních souborů k přidání do příkazu.  
  
     Další informace najdete v tématu [vstupní soubory LINK](/cpp/build/reference/link-input-files).  
  
-   **AdditionalLibraryDirectories**  
  
     Volitelné **řetězec []** parametr.  
  
     Přepíše danou cestu knihovny prostředí. Zadejte název adresáře.  
  
     Další informace najdete v tématu [/Libpath (další proměnná Libpath)](/cpp/build/reference/libpath-additional-libpath).  
  
-   **AdditionalManifestDependencies**  
  
     Volitelné **řetězec []** parametr.  
  
     Určuje atributy, které bude uložena v umístění `dependency` části souboru manifestu.  
  
     Další informace najdete v tématu [/MANIFESTDEPENDENCY (určit závislosti manifestu)](/cpp/build/reference/manifestdependency-specify-manifest-dependencies). Viz také "Vydavatele konfigurační soubory" na [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) webu.  
  
-   **AdditionalOptions**  
  
     Volitelné **řetězec** parametr.  
  
     Seznam možností linkeru jako zadaného na příkazovém řádku. Například **"*** nebo možnost 1 /option2 /option#*". Tento parametr použijte k určení možnosti linkeru, které nejsou reprezentovány jakékoliv **odkaz** parametr úloh.  
  
     Další informace najdete v tématu [možnosti Linkeru](/cpp/build/reference/linker-options).  
  
-   **AddModuleNamesToAssembly**  
  
     Volitelné **řetězec []** parametr.  
  
     Přidá odkaz na modul k sestavení.  
  
     Další informace najdete v tématu [/ASSEMBLYMODULE (Přidání modulu MSIL do sestavení)](/cpp/build/reference/assemblymodule-add-a-msil-module-to-the-assembly).  
  
-   **AllowIsolation**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, způsobí, že operační systém manifest vyhledávání a načte. Pokud `false`, označuje, zda jsou načteny knihovny DLL, jako kdyby byl žádný manifest.  
  
     Další informace najdete v tématu [/ALLOWISOLATION (vyhledání manifestu)](/cpp/build/reference/allowisolation-manifest-lookup).  
  
-   **AssemblyDebug**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, vysílá **atribut DebuggableAttribute** atribut společně s ladicí informace o sledování a zakáže JIT optimalizace. Pokud `false`, vysílá **atribut DebuggableAttribute** atribut ale zakáže ladicí informace o sledování a umožňuje JIT optimalizace.  
  
     Další informace najdete v tématu [/ASSEMBLYDEBUG (přidat atribut DebuggableAttribute)](/cpp/build/reference/assemblydebug-add-debuggableattribute).  
  
-   **AssemblyLinkResource**  
  
     Volitelné **řetězec []** parametr.  
  
     Vytvoří odkaz na prostředek rozhraní .NET Framework ve výstupním souboru; soubor prostředků není umístěn ve výstupním souboru. Zadejte název prostředku.  
  
     Další informace najdete v tématu [/ASSEMBLYLINKRESOURCE (vytvořit odkaz na prostředek rozhraní .NET Framework)](/cpp/build/reference/assemblylinkresource-link-to-dotnet-framework-resource).  
  
-   **AttributeFileTracking**  
  
     Implicitní **Boolean** parametr.  
  
     Povolí podrobnější souborů sledování k zachycení odkaz Přírůstkové na chování. Vždy vrátí hodnotu `true`.  
  
-   **BaseAddress**  
  
     Volitelné **řetězec** parametr.  
  
     Nastaví základní adresa pro program nebo sestavuje knihovny DLL. Zadejte `{address[,size] | @filename,key}`.  
  
     Další informace najdete v tématu [/BASE (základní adresa)](/cpp/build/reference/base-base-address).  
  
-   **BuildingInIDE**  
  
     Volitelné **Boolean** parametr.  
  
     V případě hodnoty true označuje, že je MSBuild vyvolat z prostředí IDE. Jinak hodnota označuje, že je MSBuild vyvolat z příkazového řádku.  
  
     Tento parametr má žádné – možnost linkeru ekvivalentní.  
  
-   **CLRImageType**  
  
     Volitelné **řetězec** parametr.  
  
     Nastaví typ běžné bitové kopie language runtime (CLR).  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídající možnosti linkeru.  
  
    -   **Výchozí** - *\<žádné >*  
  
    -   **ForceIJWImage** - **/CLRIMAGETYPE:IJW**  
  
    -   **ForcePureILImage** - **/CLRIMAGETYPE: PURE**  
  
    -   **ForceSafeILImage** - **/CLRIMAGETYPE:SAFE**  
  
     Další informace najdete v tématu [/CLRIMAGETYPE (zadat typ z obrázku CLR)](/cpp/build/reference/clrimagetype-specify-type-of-clr-image).  
  
-   **CLRSupportLastError**  
  
     Volitelné **řetězec** parametr.  
  
     Zachovává poslední kód chyby, funkce volané přes mechanismus P/Invoke.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídající možnosti linkeru.  
  
    -   **Enabled** - **/CLRSupportLastError**  
  
    -   **Disabled** - **/CLRSupportLastError:NO**  
  
    -   **SystemDlls** - **/CLRSupportLastError:SYSTEMDLL**  
  
     Další informace najdete v tématu [/CLRSUPPORTLASTERROR (zachovat poslední kód chyby pro volání PInvoke)](/cpp/build/reference/clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls).  
  
-   **CLRThreadAttribute**  
  
     Volitelné **řetězec** parametr.  
  
     Explicitně určuje atribut vláken pro vstupní bod aplikace CLR.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídající možnosti linkeru.  
  
    -   **DefaultThreadingAttribute** - **/CLRTHREADATTRIBUTE:NONE**  
  
    -   **MTAThreadingAttribute** - **/CLRTHREADATTRIBUTE:MTA**  
  
    -   **STAThreadingAttribute** - **/CLRTHREADATTRIBUTE:STA**  
  
     Další informace najdete v tématu [/CLRTHREADATTRIBUTE (nastavit CLR vláken atribut)](/cpp/build/reference/clrthreadattribute-set-clr-thread-attribute).  
  
-   **CLRUnmanagedCodeCheck**  
  
     Volitelné **Boolean** parametr.  
  
     Určuje, zda se uplatní linkeru **SuppressUnmanagedCodeSecurityAttribute** na generované linkeru P/Invoke volání ze spravovaného kódu do nativních knihoven DLL.  
  
     Další informace najdete v tématu [/CLRUNMANAGEDCODECHECK (přidat atribut SupressUnmanagedCodeSecurityAttribute)](/cpp/build/reference/clrunmanagedcodecheck-add-supressunmanagedcodesecurityattribute).  
  
-   **CreateHotPatchableImage**  
  
     Volitelné **řetězec** parametr.  
  
     Připraví bitovou kopii této technologie.  
  
     Zadejte jednu z následujících hodnot, které odpovídá možnosti linkeru.  
  
    -   **Povolit** - **/FUNCTIONPADMIN**  
  
    -   **X86Image** - **/FUNCTIONPADMIN:5**  
  
    -   **X64Image** - **/FUNCTIONPADMIN:6**  
  
    -   **ItaniumImage** - **/FUNCTIONPADMIN:16**  
  
     Další informace najdete v tématu [/FUNCTIONPADMIN (vytvořit kopii opravitelnou za provozu)](/cpp/build/reference/functionpadmin-create-hotpatchable-image).  
  
-   **DataExecutionPrevention**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, označuje, že spustitelný soubor testoval být kompatibilní s funkcí Zabránění spuštění dat systému Windows.  
  
     Další informace najdete v tématu [/NXCOMPAT (kompatibilní s předcházením spuštění dat)](/cpp/build/reference/nxcompat-compatible-with-data-execution-prevention).  
  
-   **DelayLoadDLLs**  
  
     Volitelné **řetězec []** parametr.  
  
     Tento parametr způsobí, že *odložené načtení* knihoven DLL. Zadejte název knihovny DLL pro odložené načtení.  
  
     Další informace najdete v tématu [/DELAYLOAD (Import odloženého načtení)](/cpp/build/reference/delayload-delay-load-import).  
  
-   **DelaySign**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, částečně podepisuje sestavení. Výchozí hodnota je `false`.  
  
     Další informace najdete v tématu [/delaysign (částečně podepsání sestavení)](/cpp/build/reference/delaysign-partially-sign-an-assembly).  
  
-   **Ovladače**  
  
     Volitelné **řetězec** parametr.  
  
     Zadejte tento parametr k vytvoření ovladač režimu jádra systému Windows NT.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídající možnosti linkeru.  
  
    -   **NotSet** - *\<none>*  
  
    -   **Ovladač** -   **/Driver**  
  
    -   **UpOnly** - **/DRIVER:UPONLY**  
  
    -   **WDM** - **/DRIVER:WDM**  
  
     Další informace najdete v tématu [/Driver (ovladač režimu jádra systému Windows NT)](/cpp/build/reference/driver-windows-nt-kernel-mode-driver).  
  
-   **EmbedManagedResourceFile**  
  
     Volitelné **řetězec []** parametr.  
  
     Vloží soubor prostředků v sestavení. Zadejte název souboru požadovaný prostředek. Volitelně zadejte logický název, který slouží k načtení zdroje, a **PRIVÁTNÍ** možnost, která v manifestu sestavení označuje, že se soubor prostředků je soukromé.  
  
     Další informace najdete v tématu [/ASSEMBLYRESOURCE (vložení spravované prostředků)](/cpp/build/reference/assemblyresource-embed-a-managed-resource).  
  
-   **EnableCOMDATFolding**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, umožňuje identické sekvence COMDAT skládání.  
  
     Další informace najdete v tématu `ICF[= iterations]` argument [/OPT (optimalizace)](/cpp/build/reference/opt-optimizations).  
  
-   **EnableUAC**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, určuje, že informace řízení uživatelských účtů (UAC) se vloží do manifestu programu.  
  
     Další informace najdete v tématu [/MANIFESTUAC (vložené informace UAC v manifestu)](/cpp/build/reference/manifestuac-embeds-uac-information-in-manifest).  
  
-   **EntryPointSymbol**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje funkci vstupního bodu jako počáteční adresa pro soubor .exe nebo DLL. Zadejte název funkce jako hodnotu parametru.  
  
     Další informace najdete v tématu [/Entry (Symbol vstupního bodu)](/cpp/build/reference/entry-entry-point-symbol).  
  
-   **FixedBaseAddress**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, vytvoří program nebo knihovnu DLL, kterou je možné načíst pouze v jeho upřednostňovaná základní adresa.  
  
     Další informace najdete v tématu [/FIXED (pevné základní adresa)](/cpp/build/reference/fixed-fixed-base-address).  
  
-   **ForceFileOutput**  
  
     Volitelné **řetězec** parametr.  
  
     Informuje linkeru pro vytvoření souboru platný .exe nebo knihovny DLL i v případě, že symbol odkazuje ale není definované nebo je násobení definované.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **Povolit** -   **/FORCE**  
  
    -   **MultiplyDefinedSymbolOnly** - **/FORCE:MULTIPLE**  
  
    -   **UndefinedSymbolOnly** - **/FORCE:UNRESOLVED**  
  
     Další informace najdete v tématu [/Force (vynutit výstup souboru)](/cpp/build/reference/force-force-file-output).  
  
-   **ForceSymbolReferences**  
  
     Volitelné **řetězec []** parametr.  
  
     Tento parametr řekne linkeru pro přidání určený symbol do tabulky symbolů.  
  
     Další informace najdete v tématu [/INCLUDE (vynutit odkazy na symboly)](/cpp/build/reference/include-force-symbol-references).  
  
-   **FunctionOrder**  
  
     Volitelné **řetězec** parametr.  
  
     Tento parametr optimalizuje vašeho programu tím, že zadaný zabalené funkce (COMDATs) do bitové kopie v předurčeném pořadí.  
  
     Další informace najdete v tématu [/ORDER (funkce uveďte v pořadí)](/cpp/build/reference/order-put-functions-in-order).  
  
-   **GenerateDebugInformation**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, vytvoří ladicí informace pro soubor .exe nebo DLL.  
  
     Další informace najdete v tématu [/Debug (Generovat ladicí informace)](/cpp/build/reference/debug-generate-debug-info).  
  
-   **GenerateManifest**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, vytvoří soubor manifestu vedle sebe.  
  
     Další informace najdete v tématu [/MANIFEST (Manifest vytvořit-souběžného sestavení)](/cpp/build/reference/manifest-create-side-by-side-assembly-manifest).  
  
-   **GenerateMapFile**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, vytvoří *souboru s mapováním*. Přípona názvu souboru souboru s mapováním je .map.  
  
     Další informace najdete v tématu [/map (Generovat soubor mapování)](/cpp/build/reference/map-generate-mapfile).  
  
-   **HeapCommitSize**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje množství fyzické paměti v haldě přidělit najednou.  
  
     Další informace najdete v tématu `commit` argument [/HEAP (nastavit velikost haldy)](/cpp/build/reference/heap-set-heap-size). Další informace naleznete **HeapReserveSize** parametr.  
  
-   **HeapReserveSize**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje celkový haldy přidělení virtuální paměti.  
  
     Další informace najdete v tématu `reserve` argument [/HEAP (nastavit velikost haldy)](/cpp/build/reference/heap-set-heap-size). Další informace naleznete **HeapCommitSize** parametr v této tabulce.  
  
-   **IgnoreAllDefaultLibraries**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, informuje linkeru k odebrání jednoho nebo více výchozí knihovny ze seznamu knihoven vyhledávání při se přeloží externí odkazy.  
  
     Další informace najdete v tématu [/NODEFAULTLIB (Ignorovat knihovny)](/cpp/build/reference/nodefaultlib-ignore-libraries).  
  
-   **IgnoreEmbeddedIDL**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, určuje, že všechny IDL – atributy ve zdrojovém kódu by neměl být zpracován do souboru IDL.  
  
     Další informace najdete v tématu [/IGNOREIDL (nemáte proces atributy do MIDL)](/cpp/build/reference/ignoreidl-don-t-process-attributes-into-midl).  
  
-   **IgnoreImportLibrary**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, určuje, že by neměl být knihovny importu generované tuto konfiguraci importovat do závislé projektů.  
  
     Tento parametr neodpovídá možnost linkeru.  
  
-   **IgnoreSpecificDefaultLibraries**  
  
     Volitelné **řetězec []** parametr.  
  
     Určuje jeden nebo více názvů výchozí knihovny ignorovat. Oddělte více knihoven středníky.  
  
     Další informace najdete v tématu [/NODEFAULTLIB (Ignorovat knihovny)](/cpp/build/reference/nodefaultlib-ignore-libraries).  
  
-   **ImageHasSafeExceptionHandlers**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, linkeru vytvoří bitovou kopii pouze v případě, že ho také vytvoření tabulky obslužné rutiny bezpečné výjimek obrázku.  
  
     Další informace najdete v tématu [/SAFESEH (bitová kopie má bezpečné obslužné rutiny výjimek)](/cpp/build/reference/safeseh-image-has-safe-exception-handlers).  
  
-   **ImportLibrary**  
  
     Název knihovny importu zadán uživatel, který nahrazuje názvu výchozí knihovny.  
  
     Další informace najdete v tématu [/IMPLIB (knihovna importu názvů)](/cpp/build/reference/implib-name-import-library).  
  
-   **KeyContainer**  
  
     Volitelné **řetězec** parametr.  
  
     Kontejner, který obsahuje klíč pro podepsané sestavení.  
  
     Další informace najdete v tématu [/keycontainer (zadat kontejner klíče pro podepsání sestavení)](/cpp/build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly). Další informace naleznete **KeyFile** parametr v této tabulce.  
  
-   **KeyFile**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje soubor, který obsahuje klíč pro podepsané sestavení.  
  
     Další informace najdete v tématu [/keyfile (zadat klíč nebo pár klíč pro podepsání sestavení)](/cpp/build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly). Další informace naleznete **KeyContainer** parametr.  
  
-   **LargeAddressAware**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, aplikace dokáže zvládat adresy větší než 2 GB.  
  
     Další informace najdete v tématu [/LARGEADDRESSAWARE (zpracování velkých adres)](/cpp/build/reference/largeaddressaware-handle-large-addresses).  
  
-   **LinkDLL**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, knihovny DLL jako hlavní výstupní soubor sestavení.  
  
     Další informace najdete v tématu [/DLL (sestavit knihovnu DLL)](/cpp/build/reference/dll-build-a-dll).  
  
-   **LinkErrorReporting**  
  
     Volitelné **řetězec** parametr.  
  
     Umožňuje zadat informace o chybě (LED) interní kompilátoru přímo společnosti Microsoft.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **NoErrorReport** -   **/errorreport: žádné**  
  
    -   **PromptImmediately** - **/ERRORREPORT:PROMPT**  
  
    -   **QueueForNextLogin** - **/ERRORREPORT:QUEUE**  
  
    -   **SendErrorReport** - **/ERRORREPORT:SEND**  
  
     Další informace najdete v tématu [/errorreport (sestava interními chybami Linkeru)](/cpp/build/reference/errorreport-report-internal-linker-errors).  
  
-   **LinkIncremental**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, umožňuje přírůstkové propojování.  
  
     Další informace najdete v tématu [/incremental (přírůstkově odkaz)](/cpp/build/reference/incremental-link-incrementally).  
  
-   **LinkLibraryDependencies**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, určuje, že knihovna výstupy z závislosti projektu jsou automaticky propojení v.  
  
     Tento parametr neodpovídá možnost linkeru.  
  
-   **LinkStatus**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, určuje, že je linkeru zobrazíte indikátor průběhu, který ukazuje, jaké procento odkaz je kompletní.  
  
     Další informace najdete v tématu `STATUS` argument [/ltgc (vytváření kódu v době propojování)](/cpp/build/reference/ltcg-link-time-code-generation).  
  
-   **LinkTimeCodeGeneration**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje možnosti pro optimalizace na základě profilu.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **Výchozí** - *\<žádné >*  
  
    -   **UseLinkTimeCodeGeneration** - **/LTCG**  
  
    -   **PGInstrument** - **/LTCG:PGInstrument**  
  
    -   **PGOptimization** - **/LTCG:PGOptimize**  
  
    -   **PGUpdate**  
  
         \- **/LTCG:PGUpdate**  
  
     Další informace najdete v tématu [/ltgc (vytváření kódu v době propojování)](/cpp/build/reference/ltcg-link-time-code-generation).  
  
-   **ManifestFile**  
  
     Volitelné **řetězec** parametr.  
  
     Výchozí název souboru manifestu se změní na zadaný název souboru.  
  
     Další informace najdete v tématu [/MANIFESTFILE (název souboru manifestu)](/cpp/build/reference/manifestfile-name-manifest-file).  
  
-   **MapExports**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, informuje linkeru chcete zahrnout do souboru s mapováním exportovaných funkcí.  
  
     Další informace najdete v tématu `EXPORTS` argument [/MAPINFO (zahrnout informace do souboru mapování)](/cpp/build/reference/mapinfo-include-information-in-mapfile).  
  
-   **MapFileName**  
  
     Volitelné **řetězec** parametr.  
  
     Název výchozí mapování souboru se změní na zadaný název souboru.  
  
-   **MergedIDLBaseFileName**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje název souboru a příponu názvu souboru.  
  
     Další informace najdete v tématu [/IDLOUT (název výstupní soubory MIDL)](/cpp/build/reference/idlout-name-midl-output-files).  
  
-   **MergeSections**  
  
     Volitelné **řetězec** parametr.  
  
     Kombinuje části bitovou kopii. Zadejte `from-section=to-section`.  
  
     Další informace najdete v tématu [/Merge (kombinovat oddílů)](/cpp/build/reference/merge-combine-sections).  
  
-   **MidlCommandFile**  
  
     Volitelné **řetězec** parametr.  
  
     Zadejte název souboru, který obsahuje možnosti příkazového řádku MIDL.  
  
     Další informace najdete v tématu [/MIDL (zadejte možnosti příkazového řádku MIDL)](/cpp/build/reference/midl-specify-midl-command-line-options).  
  
-   **MinimumRequiredVersion**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje minimální požadovaná verze subsystému. Argumenty jsou desítková číslice v rozsahu 0 až 65535.  
  
-   **ModuleDefinitionFile**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje název [soubor definice modulu](/cpp/build/reference/module-definition-dot-def-files).  
  
     Další informace najdete v tématu [/def (zadat soubor definice modulu)](/cpp/build/reference/def-specify-module-definition-file).  
  
-   **MSDOSStubFileName**  
  
     Volitelné **řetězec** parametr.  
  
     Připojí zadaný programu zástupného kódu MS-DOS Win32 programu.  
  
     Další informace najdete v tématu [/stub (název souboru zástupného kódu MS-DOS)](/cpp/build/reference/stub-ms-dos-stub-file-name).  
  
-   **NoEntryPoint**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, určuje pouze knihovny DLL.  
  
     Další informace najdete v tématu [/NOENTRY (bez vstupního bodu)](/cpp/build/reference/noentry-no-entry-point).  
  
-   **ObjectFiles**  
  
     Implicitní **řetězec []** parametr.  
  
     Určuje soubory objektů, které jsou propojeny.  
  
-   **OptimizeReferences**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, eliminuje funkce nebo data, která se nikdy odkazuje.  
  
     Další informace najdete v tématu `REF` argument [/OPT (optimalizace)](/cpp/build/reference/opt-optimizations).  
  
-   **Výstupní soubor**  
  
     Volitelné **řetězec** parametr.  
  
     Přepíše výchozí název a umístění program, který vytvoří linkeru.  
  
     Další informace najdete v tématu [/OUT (název výstupního souboru)](/cpp/build/reference/out-output-file-name).  
  
-   **PerUserRedirection**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true` a zaregistrujte výstupní je povolena, vynutí registru zapisuje do **HKEY_CLASSES_ROOT** přesměrovat na **HKEY_CURRENT_USER**.  
  
-   **PreprocessOutput**  
  
     Volitelné `ITaskItem[]` parametr.  
  
     Definuje pole výstup preprocesoru položek, které je možné využívat a vygenerované úlohami.  
  
-   **PreventDllBinding**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, Bind.exe pozná, že by neměla být vázána propojený obrázek.  
  
     Další informace najdete v tématu [/ALLOWBIND (zabránit DLL vazby)](/cpp/build/reference/allowbind-prevent-dll-binding).  
  
-   **Profil**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, vytváří výstupního souboru, který lze použít s **nástroje pro sledování výkonu** profileru.  
  
     Další informace najdete v tématu [/Profile (Profiler nástrojů výkonu)](/cpp/build/reference/profile-performance-tools-profiler).  
  
-   **ProfileGuidedDatabase**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje název souboru .pgd, který se použije k uložení informace o spuštěným programem  
  
     Další informace najdete v tématu [/PGD (určit databázi pro optimalizace Profile-Guided)](/cpp/build/reference/pgd-specify-database-for-profile-guided-optimizations).  
  
-   **ProgramDatabaseFile**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje název databáze programu (PDB), který vytváří linkeru.  
  
     Další informace najdete v tématu [/pdb (použít databázi programu)](/cpp/build/reference/pdb-use-program-database).  
  
-   **RandomizedBaseAddress**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, generuje spustitelné bitové kopie, který může být náhodně rebased při načítání, pomocí *adres náhodného přeskupování rozložení místa* (technologie ASLR) funkce systému Windows.  
  
     Další informace najdete v tématu [/DYNAMICBASE (použijte adresu místa rozložení náhodné)](/cpp/build/reference/dynamicbase-use-address-space-layout-randomization).  
  
-   **RegisterOutput**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, zaregistruje primárnímu výstupu toto sestavení.  
  
-   **SectionAlignment**  
  
     Volitelné **celé číslo** parametr.  
  
     Určuje zarovnání každého oddílu v lineární adresní prostor programu. Hodnota parametru je jednotka počet bajtů a je druhou mocninou dva.  
  
     Další informace najdete v tématu [/ALIGN (zarovnání oddílů)](/cpp/build/reference/align-section-alignment).  
  
-   **SetChecksum**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, nastaví kontrolního součtu v hlavičce souboru s příponou .exe.  
  
     Další informace najdete v tématu [/Release (nastavení kontrolního součtu)](/cpp/build/reference/release-set-the-checksum).  
  
-   **ShowProgress**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje podrobností sestavy průběhu pro operace propojení.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **NotSet** - *\<none>*  
  
    -   **LinkVerbose** - **/VERBOSE**  
  
    -   **LinkVerboseLib** - **/VERBOSE:Lib**  
  
    -   **LinkVerboseICF** - **/VERBOSE:ICF**  
  
    -   **LinkVerboseREF** - **/VERBOSE:REF**  
  
    -   **LinkVerboseSAFESEH** - **/VERBOSE:SAFESEH**  
  
    -   **LinkVerboseCLR** - **/VERBOSE:CLR**  
  
     Další informace najdete v tématu [verbose (Tisk zpráv průběhu)](/cpp/build/reference/verbose-print-progress-messages).  
  
-   **Zdroje**  
  
     Požadované `ITaskItem[]` parametr.  
  
     Definuje pole MSBuild zdrojového souboru položek, které je možné využívat a vygenerované úlohami.  
  
-   **SpecifySectionAttributes**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje atributy oddílu. Přepíše atributy, které byly nastaveny při kompilace souboru .obj pro oddíl.  
  
     Další informace najdete v tématu [/SECTION (určit atributy oddílu)](/cpp/build/reference/section-specify-section-attributes).  
  
-   **StackCommitSize**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje množství fyzické paměti v každém přidělení při přidělení další paměť.  
  
     Další informace najdete v tématu `commit` argument [/STACK (přidělení zásobníku)](/cpp/build/reference/stack-stack-allocations).  
  
-   **StackReserveSize**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje velikost alokační celkový zásobníku v virtuální paměti.  
  
     Další informace najdete v tématu `reserve` argument [/STACK (přidělení zásobníku)](/cpp/build/reference/stack-stack-allocations).  
  
-   **StripPrivateSymbols**  
  
     Volitelné **řetězec** parametr.  
  
     Vytvoří druhý soubor databáze (PDB) program, který vynechá znaky, které nechcete distribuovat zákazníkům. Zadejte název druhého souboru PDB.  
  
     Další informace najdete v tématu [/PDBSTRIPPED (Odstranit privátní symboly)](/cpp/build/reference/pdbstripped-strip-private-symbols).  
  
-   **Subsystém**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje prostředí pro spustitelný soubor.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **NotSet** - *\<none>*  
  
    -   **Konzole** - **/SUBSYSTEM:CONSOLE**  
  
    -   **Windows** - **/SUBSYSTEM:WINDOWS**  
  
    -   **Nativní** - **/SUBSYSTEM:NATIVE**  
  
    -   **Aplikace rozhraní EFI** - **/SUBSYSTEM:EFI_APPLICATION**  
  
    -   **Ovladač služby spouštěcí EFI** - **/SUBSYSTEM:EFI_BOOT_SERVICE_DRIVER**  
  
    -   **ROZHRANÍ EFI ROM** - **/SUBSYSTEM:EFI_ROM**  
  
    -   **Modul Runtime rozhraní EFI** - **/SUBSYSTEM:EFI_RUNTIME_DRIVER**  
  
    -   **WindowsCE** - **/SUBSYSTEM:WINDOWSCE**  
  
    -   **POSIX** - **/SUBSYSTEM:POSIX**  
  
     Další informace najdete v tématu [/SUBSYSTEM (zadat subsystém)](/cpp/build/reference/subsystem-specify-subsystem).  
  
-   **SupportNobindOfDelayLoadedDLL**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, informuje linkeru nechcete zahrnout vazbu tabulky Import adres (IAT) do finální image.  
  
     Další informace najdete v tématu `NOBIND` argument [/delay (nastavení importu odloženého načtení)](/cpp/build/reference/delay-delay-load-import-settings).  
  
-   **SupportUnloadOfDelayLoadedDLL**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, informuje o načtení zpoždění podpůrné funkci pro podporu explicitní uvolnění knihovny DLL.  
  
     Další informace najdete v tématu `UNLOAD` argument [/delay (nastavení importu odloženého načtení)](/cpp/build/reference/delay-delay-load-import-settings).  
  
-   **SuppressStartupBanner**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, zabraňuje zobrazení číslo zprávy o autorských právech a verzi, po spuštění úlohy.  
  
     Další informace najdete v tématu [/nologo (Potlačit úvodní nápis při spouštění) (Linker)](/cpp/build/reference/nologo-suppress-startup-banner-linker).  
  
-   **SwapRunFromCD**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, informuje nejdříve zkopírovat linkeru výstup do souboru odkládacího souboru operačního systému, a potom spusťte bitovou kopii z ní.  
  
     Další informace najdete v tématu `CD` argument [/SWAPRUN (Načíst výstup Linkeru do odkládacího souboru)](/cpp/build/reference/swaprun-load-linker-output-to-swap-file). Další informace naleznete **SwapRunFromNET** parametr.  
  
-   **SwapRunFromNET**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, informuje nejdříve zkopírovat linkeru výstup do souboru odkládacího souboru operačního systému, a potom spusťte bitovou kopii z ní.  
  
     Další informace najdete v tématu `NET` argument [/SWAPRUN (Načíst výstup Linkeru do odkládacího souboru)](/cpp/build/reference/swaprun-load-linker-output-to-swap-file). Další informace naleznete **SwapRunFromCD** parametr v této tabulce.  
  
-   **TargetMachine**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje cílovou platformu pro program nebo DLL.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **NotSet** - *\<none>*  
  
    -   **MachineARM** - **/MACHINE:ARM**  
  
    -   **MachineEBC** - **/MACHINE:EBC**  
  
    -   **MachineIA64** - **/MACHINE:IA64**  
  
    -   **MachineMIPS** - **/MACHINE:MIPS**  
  
    -   **MachineMIPS16** - **/MACHINE:MIPS16**  
  
    -   **MachineMIPSFPU** - **/MACHINE:MIPSFPU**  
  
    -   **MachineMIPSFPU16** - **/MACHINE:MIPSFPU16**  
  
    -   **MachineSH4** - **/MACHINE:SH4**  
  
    -   **MachineTHUMB** - **/MACHINE:THUMB**  
  
    -   **MachineX64** - **/MACHINE:X64**  
  
    -   **MachineX86** - **/MACHINE:X86**  
  
     Další informace najdete v tématu [/MACHINE (zadat cílové platformy)](/cpp/build/reference/machine-specify-target-platform).  
  
-   **TerminalServerAware**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, nastaví příznak v poli IMAGE_OPTIONAL_HEADER DllCharacteristics v nepovinné hlavičkové bitové kopie programu. Pokud je nastavený tento příznak, nebude terminálového serveru provádět určité změny aplikace.  
  
     Další informace najdete v tématu [/TSAWARE (vytvořit terminálového serveru aplikace podporující)](/cpp/build/reference/tsaware-create-terminal-server-aware-application).  
  
-   **TrackerLogDirectory**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje adresář protokolu sledovací modul.  
  
-   **TreatLinkerWarningAsErrors**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, způsobí, že žádná výstupní soubor do vyvolala v případě linkeru vygeneruje upozornění.  
  
     Další informace najdete v tématu [wdn (považovat upozornění Linkeru jako chyby)](/cpp/build/reference/wx-treat-linker-warnings-as-errors).  
  
-   **TurnOffAssemblyGeneration**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, vytvoří bitovou kopii pro aktuální soubor výstupu bez sestavení rozhraní .NET Framework.  
  
     Další informace najdete v tématu [/NOASSEMBLY (vytvořit modul MSIL)](/cpp/build/reference/noassembly-create-a-msil-module).  
  
-   **TypeLibraryFile**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje název souboru a příponu názvu souboru .tlb. Zadejte název souboru nebo název a cesta k souboru.  
  
     Další informace najdete v tématu [/TLBOUT (název. Soubor TLB)](/cpp/build/reference/tlbout-name-dot-tlb-file).  
  
-   **TypeLibraryResourceID**  
  
     Volitelné **celé číslo** parametr.  
  
     Označuje hodnotu zadaného uživatelem pro knihovny typů vytvořené linkeru. Zadejte hodnotu od 1 do 65535.  
  
     Další informace najdete v tématu [/TLBID (zadat ID prostředku pro TypeLib)](/cpp/build/reference/tlbid-specify-resource-id-for-typelib).  
  
-   **UACExecutionLevel**  
  
     Volitelné **řetězec** parametr.  
  
     Určuje úroveň požadovaný spuštění pro aplikaci při spuštění v části s řízení uživatelských účtů.  
  
     Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.  
  
    -   **AsInvoker** - `level='asInvoker'`  
  
    -   **HighestAvailable** - `level='highestAvailable'`  
  
    -   **RequireAdministrator** - `level='requireAdministrator'`  
  
     Další informace najdete v tématu `level` argument [/MANIFESTUAC (vložené informace UAC v manifestu)](/cpp/build/reference/manifestuac-embeds-uac-information-in-manifest).  
  
-   **UACUIAccess**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, obchází úrovních ochrany uživatelské rozhraní aplikace a disky vstupní vyšší oprávnění systému Windows na ploše; v opačném `false`.  
  
     Další informace najdete v tématu `uiAccess` argument [/MANIFESTUAC (vložené informace UAC v manifestu)](/cpp/build/reference/manifestuac-embeds-uac-information-in-manifest).  
  
-   **UseLibraryDependencyInputs**  
  
     Volitelné **Boolean** parametr.  
  
     Pokud `true`, se používají vstupů pro nástroj librarian spíše než samotná knihovny výstupy z závislosti projektu soubor knihovny jsou propojeny v.  
  
-   **Verze**  
  
     Volitelné **řetězec** parametr.  
  
     Uveďte číslo verze v hlavičce souboru .exe nebo .dll. Zadejte "`major[.minor]`". `major` a `minor` argumenty jsou desetinná čísla od 0 do 65535.  
  
     Další informace najdete v tématu [/VERSION (informace o verzi)](/cpp/build/reference/version-version-information).  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)