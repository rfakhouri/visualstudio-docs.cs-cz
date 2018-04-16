---
title: LIB – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology: msbuild
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCLibrarianTool.Name
- VC.Project.VCLibrarianTool.TreatLibWarningsAsErrors
- VC.Project.VCLibrarianTool.Verbose
- vc.task.lib
- VC.Project.VCLibrarianTool.ErrorReporting
- VC.Project.VCLibrarianTool.LinkLibraryDependencies
- VC.Project.VCLibrarianTool.LinkTimeCodeGeneration
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), LIB task
- LIB task (MSBuild (Visual C++))
ms.assetid: e062c7f9-cc69-4a83-9361-1bb5355e5fe8
caps.latest.revision: 7
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 13b6ceb908e45cf98f32f89605bf48f8e747b7aa
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="lib-task"></a>LIB – úloha
Zabalí nástroj Microsoft 32bitový Správce knihovny lib.exe. Správce knihovny vytváří a spravuje knihovnu běžných objekt souboru formátu () objekt soubory COFF. Správce knihovny můžete také vytvořit export souborů a knihoven importovat do definice odkaz exportovat. Další informace najdete v tématu [LIB odkaz](/cpp/build/reference/lib-reference) a [systémem LIB](/cpp/build/reference/running-lib).  
  
## <a name="parameters"></a>Parametry  
 Následující tabulka popisuje parametry **LIB** úloh. Většina úloh parametry odpovídají možnosti příkazového řádku.  
  
|Parametr|Popis|  
|---------------|-----------------|  
|**AdditionalDependencies**|Volitelné **řetězec []** parametr.<br /><br /> Určuje další položek, které chcete přidat do příkazového řádku.|  
|**AdditionalLibraryDirectories**|Volitelné **řetězec []** parametr.<br /><br /> Přepíše danou cestu knihovny prostředí. Zadejte název adresáře.<br /><br /> Další informace najdete v tématu [/Libpath (další proměnná Libpath)](/cpp/build/reference/libpath-additional-libpath).|  
|**AdditionalOptions**|Volitelné **řetězec** parametr.<br /><br /> Seznam možností lib.exe jako zadaného na příkazovém řádku. Například **"***nebo možnost 1 /option2 /option#*". Tento parametr použijte k určení možností lib.exe, které nejsou reprezentovány jakékoliv **LIB** parametr úloh.<br /><br /> Další informace najdete v tématu [systémem LIB](/cpp/build/reference/running-lib).|  
|**DisplayLibrary**|Volitelné **řetězec** parametr.<br /><br /> Zobrazí informace o knihovně výstup. Zadejte název souboru pro přesměrování informace do souboru. Zadejte "CON" nebo nic k přesměrování informace ke konzole.<br /><br /> Tento parametr odpovídá **/seznamu** možnost lib.exe.|  
|**ErrorReporting**|Volitelné **řetězec** parametr.<br /><br /> Určuje, jak k odeslání společnosti Microsoft informace o interní chybě, pokud se nezdaří lib.exe za běhu.<br /><br /> Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.<br /><br /> -   **NoErrorReport** - **/ERRORREPORT:NONE**<br />-   **PromptImmediately** - **/ERRORREPORT:PROMPT**<br />-   **QueueForNextLogin** - **/ERRORREPORT:QUEUE**<br />-   **SendErrorReport** - **/ERRORREPORT:SEND**<br /><br /> Další informace najdete v tématu **/errorreport** možnost příkazového řádku na [systémem LIB](/cpp/build/reference/running-lib).|  
|**ExportNamedFunctions**|Volitelné **řetězec []** parametr.<br /><br /> Určuje jeden nebo více funkcí pro export.<br /><br /> Tento parametr odpovídá **/EXPORT:** možnost lib.exe.|  
|**ForceSymbolReferences**|Volitelné **řetězec** parametr.<br /><br /> Vynutí lib.exe odkaz na zadaný symbol.<br /><br /> Tento parametr odpovídá **/INCLUDE:** možnost lib.exe.|  
|**IgnoreAllDefaultLibraries**|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, odebere všechny výchozí knihovny ze seznamu knihoven této lib.exe vyhledá při se přeloží externí odkazy.<br /><br /> Tento parametr odpovídá formu bez parametrů **/NODEFAULTLIB** možnost lib.exe.|  
|**IgnoreSpecificDefaultLibraries**|Volitelné **řetězec []** parametr.<br /><br /> Odebere zadaný knihovny ze seznamu knihoven této lib.exe vyhledá při se přeloží externí odkazy.<br /><br /> Tento parametr odpovídá **/NODEFAULTLIB** možnost lib.exe která přebírá `library` argument.|  
|**LinkLibraryDependencies**|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, určuje, že knihovna výstupy z závislosti projektu jsou automaticky propojení v.|  
|**LinkTimeCodeGeneration**|Volitelné `Boolean` parametr.<br /><br /> Pokud `true`, určuje generování kódu v době propojování.<br /><br /> Tento parametr odpovídá **/LCTG** možnost lib.exe.|  
|**MinimumRequiredVersion**|Volitelné **řetězec** parametr.<br /><br /> Určuje minimální požadovaná verze subsystému. Zadejte čárkami oddělený seznam desítková číslice v rozsahu 0 až 65535.|  
|**ModuleDefinitionFile**|Volitelné **řetězec** parametr.<br /><br /> Určuje název souboru definice modulu (.def).<br /><br /> Tento parametr odpovídá **/def** možnost lib.exe která přebírá `filename` argument.|  
|**Jméno**|Volitelné **řetězec** parametr.<br /><br /> Když je sestavena knihovnu importu, určuje název knihovny DLL, pro kterou je vytvořený knihovny importu.<br /><br /> Tento parametr odpovídá **/NAME** možnost lib.exe která přebírá `filename` argument.|  
|**OutputFile**|Volitelné **řetězec** parametr.<br /><br /> Přepíše výchozí název a umístění programu tohoto lib.exe vytvoří.<br /><br /> Tento parametr odpovídá **/OUT** možnost lib.exe která přebírá `filename` argument.|  
|**RemoveObjects**|Volitelné **řetězec []** parametr.<br /><br /> Zadaný objekt z knihovny výstup vynechá. Lib.exe vytvoří výstupní knihovny kombinování všechny objekty (ať už v objektu soubory nebo knihovny) a poté odstranit všechny objekty, které jsou určené tuto možnost.<br /><br /> Tento parametr odpovídá **/odebrat** možnost lib.exe která přebírá `membername` argument.|  
|**Zdroje**|Požadované `ITaskItem[]` parametr.<br /><br /> Určuje seznam zdrojové soubory, které jsou oddělené mezerami.|  
|**SubSystem**|Volitelné **řetězec** parametr.<br /><br /> Určuje prostředí pro spustitelný soubor. Volba subsystému ovlivní symbol vstupního bodu nebo funkce vstupního bodu.<br /><br /> Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.<br /><br /> -   **Konzole** - **/SUBSYSTEM:CONSOLE**<br />-   **Windows** - **/SUBSYSTEM:WINDOWS**<br />-   **Nativní** - **/SUBSYSTEM:NATIVE**<br />-   **Aplikace rozhraní EFI** - **/SUBSYSTEM:EFI_APPLICATION**<br />-   **Ovladač služby spouštěcí EFI** - **/SUBSYSTEM:EFI_BOOT_SERVICE_DRIVER**<br />-   **ROZHRANÍ EFI ROM** - **/SUBSYSTEM:EFI_ROM**<br />-   **EFI Runtime** - **/SUBSYSTEM:EFI_RUNTIME_DRIVER**<br />-   **WindowsCE** - **/SUBSYSTEM:WINDOWSCE**ReplaceThisText<br />-   **POSIX** - **/SUBSYSTEM:POSIX**<br /><br /> Další informace najdete v tématu [/SUBSYSTEM (zadat subsystém)](/cpp/build/reference/subsystem-specify-subsystem).|  
|**SuppressStartupBanner**|Volitelné **Boolean** parametr.<br /><br /> Pokud `true`, zabraňuje zobrazení číslo zprávy o autorských právech a verzi, po spuštění úlohy.<br /><br /> Další informace najdete v tématu **/nologo** možnost v [systémem LIB](/cpp/build/reference/running-lib).|  
|**TargetMachine**|Volitelné **řetězec** parametr.<br /><br /> Určuje cílovou platformu pro program nebo DLL.<br /><br /> Zadejte jednu z následujících hodnot, z nichž každý odpovídá možnosti příkazového řádku.<br /><br /> -   **MachineARM** - **/MACHINE:ARM**<br />-   **MachineEBC** - **/MACHINE:EBC**<br />-   **MachineIA64** - **/MACHINE:IA64**<br />-   **MachineMIPS** - **/MACHINE:MIPS**<br />-   **MachineMIPS16** - **/MACHINE:MIPS16**<br />-   **MachineMIPSFPU** -**/MACHINE:MIPSFPU**<br />-   **MachineMIPSFPU16** - **/MACHINE:MIPSFPU16**<br />-   **MachineSH4** - **/MACHINE:SH4**<br />-   **MachineTHUMB** - **/MACHINE:THUMB**<br />-   **MachineX64** - **/MACHINE:X 64**<br />-   **MachineX86** - **/MACHINE:X 86**<br /><br /> Další informace najdete v tématu [/MACHINE (zadat cílové platformy)](/cpp/build/reference/machine-specify-target-platform).|  
|**TrackerLogDirectory**|Volitelné **řetězec** parametr.<br /><br /> Určuje adresář protokolu sledovací modul.|  
|**TreatLibWarningAsErrors**|Volitelné **Boolean** parametr.<br /><br /> Pokud `true`, způsobí, že **LIB** úloh negeneruje výstupního souboru, pokud lib.exe vygeneruje upozornění. Pokud `false`, je generována výstupní soubor.<br /><br /> Další informace najdete v tématu **wdn** možnost v [systémem LIB](/cpp/build/reference/running-lib).|  
|**UseUnicodeResponseFiles**|Volitelné **Boolean** parametr.<br /><br /> Pokud `true`, dá pokyn systému projektu pro vygenerování souborů UNICODE odpovědi, když je vytvořený librarian. Zadejte `true` při soubory v projektu mít kódování UNICODE cesty.|  
|**Verbose**|Volitelné **Boolean** parametr.<br /><br /> Pokud `true`, zobrazí podrobnosti o průběhu relace; to zahrnuje názvy souborů .obj přidáván. Informace se odesílají do standardního výstupního a můžete přesměrovat do souboru.<br /><br /> Další informace najdete v tématu **/VERBOSE** možnost [systémem LIB](/cpp/build/reference/running-lib).|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)