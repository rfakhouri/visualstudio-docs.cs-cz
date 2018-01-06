---
title: "Reference k příkazovému řádku MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, msbuild.exe
- MSBuild, command line reference
- msbuild.exe
ms.assetid: edaa65ec-ab8a-42a1-84cb-d76d5b2f4584
caps.latest.revision: "57"
author: kempb
ms.author: kempb
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 8fa07e9e489dd6334e0075da4cd8c265e71aa1db
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="msbuild-command-line-reference"></a>Referenční dokumentace pro použití nástroje MSBuild v příkazovém řádku
Při použití MSBuild.exe pro vytvoření souboru projekt nebo řešení, může obsahovat několik přepínačů zadat různé aspekty procesu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
MSBuild.exe [Switches] [ProjectFile]  
```  
  
## <a name="arguments"></a>Arguments  
  
|Argument|Popis|  
|--------------|-----------------|  
|`ProjectFile`|Sestaví cíle v souboru projektu, který určíte. Pokud nezadáte soubor projektu, vyhledá MSBuild aktuální pracovní adresář pro příponu názvu souboru, který končí na "proj" a použije tento soubor. Můžete také určit soubor řešení sady Visual Studio pro tento argument.|  
  
## <a name="switches"></a>Přepínače  
  
|přepínače|Krátký tvar|Popis|  
|------------|----------------|-----------------|  
|/help|/? nebo /h|Zobrazí informace o využití. Příkaz je příklad:<br /><br /> `msbuild.exe /?`|  
|/detailedsummary|/DS|Zobrazit podrobné informace na konci protokolu sestavení o konfiguracích, které byly vytvořeny a jak byly naplánovány na uzly.|  
|/ignoreprojectextensions:`extensions`|/ Ignorovat:`extensions`|Zadané rozšíření ignorujte při určování, které souboru projektu pro sestavení. K oddělení více rozšíření, jak ukazuje následující příklad použijte středníkem nebo čárkou:<br /><br /> `/ignoreprojectextensions:.vcproj,.sln`|  
|/maxcpucount [:`number`]|/m [:`number`]|Určuje maximální počet souběžných procesů pro použití při vytváření. Pokud nechcete zahrnout tento přepínač, výchozí hodnota je 1. Pokud zahrnete tento přepínač bez zadání hodnoty, bude MSBuild použít až počet procesorů v počítači. Další informace najdete v tématu [sestavování více projektů současně](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md).<br /><br /> Následující příklad dá pokyn MSBuild k sestavení pomocí tři procesy MSBuild, která umožňuje vytvářet ve stejnou dobu tří projektů:<br /><br /> `msbuild myproject.proj /maxcpucount:3`|  
|/noautoresponse|/noautorsp|Neobsahují žádné soubory MSBuild.rsp automaticky.|  
|/nodeReuse:`value`|/nr:`value`|Povolit nebo zakázat opakované použití nástroje MSBuild uzly. Můžete zadat následující hodnoty:<br /><br /> -   **Hodnota TRUE,**. Uzly zůstat po dokončení sestavení tak, aby následné sestavení využívat (výchozí).<br />-   **False**. Uzly nejsou zůstat po dokončení sestavení.<br /><br /> Uzel odpovídá projekt, který spouští. Pokud zahrnete **/maxcpucount** přepínače, více uzly mohou spouštět souběžně.|  
|/nologo||Nezobrazovat úvodní nápis nebo zprávu o autorských právech.|  
|<a name="preprocess"></a>/ Předběžně zpracovat [:`filepath`]|/PP [:`filepath`]|Vytvořte soubor projektu jeden, agregované podle vložené všechny soubory, které by byl importován při vytváření sestavení s jejich hranice označené. Tento přepínač můžete snadněji určit, které soubory jsou importována, kde jsou importovaných souborů a které soubory přispívají k sestavení. Pokud použijete tento přepínač, projekt není sestaven.<br /><br /> Pokud zadáte `filepath`, agregované projektový soubor je výstup do souboru. Výstup, jinak se zobrazí v okně konzoly.<br /><br /> Informace o tom, jak používat `Import` elementu, který chcete vložit soubor projektu do jiného souboru projektu, najdete v části [Import – Element (MSBuild)](../msbuild/import-element-msbuild.md) a [postupy: použití stejného cíle ve více souborech projektu](../msbuild/how-to-use-the-same-target-in-multiple-project-files.md).|  
|/Property:`name`=`value`|/ p:`name`=`value`|Nastavit nebo přepsání zadané vlastnosti úrovni projektu, kde `name` je název vlastnosti a `value` je hodnota vlastnosti. Zadejte každou vlastnost samostatně, nebo použijte středníkem nebo čárkou k oddělení více vlastností, jak ukazuje následující příklad:<br /><br /> `/property:WarningLevel=2;OutDir=bin\Debug`|  
|/ target:`targets`|/ t:`targets`|Vytvoření cíle zadaného v projektu. Zadejte každém cíli samostatně, nebo použijte středníkem nebo čárkou k oddělení více cílů, jak ukazuje následující příklad:<br /><br /> `/target:Resources;Compile`<br /><br /> Pokud zadáte pomocí tohoto přepínače veškerých cílů, běží místo veškerých cílů v `DefaultTargets` atribut v souboru projektu. Další informace najdete v tématu [cíl sestavení pořadí](../msbuild/target-build-order.md) a [postup: Určete který cíl sestavení první](../msbuild/how-to-specify-which-target-to-build-first.md).<br /><br /> Cíl je skupina úloh. Další informace najdete v tématu [cíle](../msbuild/msbuild-targets.md).|  
|/toolsversion:`version`|/TV:`version`|Určuje verzi sady nástrojů sloužící k sestavení projektu, jak ukazuje následující příklad:`/toolsversion:3.5`<br /><br /> Pomocí tohoto přepínače můžete sestavení projektu a určit, na verzi, která se liší od verze, který je uveden v [Project – Element (MSBuild)](../msbuild/project-element-msbuild.md). Další informace najdete v tématu [přepsání nastavení parametru ToolsVersion](../msbuild/overriding-toolsversion-settings.md).<br /><br /> Pro MSBuild 4.5, můžete zadat následující hodnoty pro `version`: 2.0, 3.5 nebo 4.0. Pokud zadáte 4.0, `VisualStudioVersion` sestavení vlastnost určuje, které dílčí nástrojů používat. Další informace najdete v tématu části dílčí modulové [sada nástrojů (atribut ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md).<br /><br /> Sady nástrojů se skládá z úloh, cílů a nástroje, které se používají k vytvoření aplikace. K nástrojům patří kompilátory například csc.exe a vbc.exe. Další informace o modulové najdete v tématu [sada nástrojů (atribut ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md), [standardní a vlastní konfigurace sady nástrojů](../msbuild/standard-and-custom-toolset-configurations.md), a [cílení na více verzí](../msbuild/msbuild-multitargeting-overview.md). **Poznámka:** nástrojů verze není stejná jako cílové rozhraní, což je verze rozhraní .NET Framework, na kterém byl vytvořen na projekt, aby spustit. Další informace najdete v tématu [Cílová architektura a cílová platforma](../msbuild/msbuild-target-framework-and-target-platform.md).|  
|/ validate: [`schema`]|/Val [`schema`]|Ověření souboru projektu a v případě úspěšného ověření sestavení projektu.<br /><br /> Pokud nezadáte `schema`, projekt bude ověřeno výchozí schéma.<br /><br /> Pokud zadáte `schema`, projekt bude ověřeno schéma, které zadáte.<br /><br /> Toto nastavení je příklad:`/validate:MyExtendedBuildSchema.xsd`|  
|/verbosity:`level`|/ v:`level`|Určuje množství informací, které chcete zobrazit v protokolu sestavení. Každý protokolovacího nástroje zobrazuje události podle úrovně podrobností, který nastavíte pro tohoto protokolovacího nástroje.<br /><br /> Můžete zadat těchto úrovní podrobností: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, a `diag[nostic]`.<br /><br /> Toto nastavení je příklad:`/verbosity:quiet`|  
|/Version|/ ver|Zobrazit informace o verzi. Projekt není sestaven.|  
|@`file`||Vložte přepínače příkazového řádku z textového souboru. Pokud máte více souborů, je možné určit je samostatně. Další informace najdete v tématu [soubory odezvy](../msbuild/msbuild-response-files.md).|  
  
### <a name="switches-for-loggers"></a>Přepínače protokolovacích nástrojů  
  
|přepínače|Krátký tvar|Popis|  
|------------|----------------|-----------------|  
|/consoleloggerparameters:<br /><br /> `parameters`|/CLP:`parameters`|Protokoly konzoly, která zobrazuje informace o sestavení v okně konzoly předejte parametry, které zadáte. Můžete zadat následující parametry:<br /><br /> -   **PerformanceSummary**. Zobrazit času stráveného v úkolů, cílů a projektů.<br />-   **Souhrn**. Zobrazte souhrn upozornění a chyby na konci.<br />-   **NoSummary**. Na konci nejsou zobrazit souhrn upozornění a chyby.<br />-   **ErrorsOnly**. Zobrazit pouze chyby.<br />-   **WarningsOnly**. Zobrazit pouze upozornění.<br />-   **NoItemAndPropertyList**. Nezobrazovat seznam položek a vlastnosti, které se objeví na začátku každé sestavení projektu, pokud je úroveň podrobností nastavená na `diagnostic`.<br />-   **ShowCommandLine**. Zobrazit `TaskCommandLineEvent` zprávy.<br />-   **ShowTimestamp**. Zobrazit časové razítko jako předpona k jakékoli zprávy.<br />-   **ShowEventId**. Zobrazit ID události pro každou Začínáme událostí, dokončení událostí a zprávy.<br />-   **ForceNoAlign**. Nemáte Zarovná text k velikost vyrovnávací paměti konzoly.<br />-   **DisableConsoleColor**. Použijte pro všechny zprávy protokolování výchozí barvy konzoly.<br />-   **DisableMPLogging**. Styl s více procesory protokolování výstupu zakážete při spuštění v režimu s více procesory.<br />-   **EnableMPLogging**. Styl s více procesory protokolování povolte, i v případě, že je spuštěna v režimu s více procesory. Ve výchozím nastavení zapnutý tento styl protokolování.<br />-   **Podrobností**. Přepsání **/verbosity** nastavení pro tohoto protokolovacího nástroje.<br /><br /> K oddělení více parametry, jak ukazuje následující příklad použijte středníkem nebo čárkou:<br /><br /> `/consoleloggerparameters:PerformanceSummary;NoSummary /verbosity:minimal`|  
|/distributedFileLogger|/DFL|Protokolování výstupu sestavení každého uzlu MSBuild do vlastního souboru. Počáteční umístění těchto souborů je to aktuální adresář. Ve výchozím nastavení, jsou soubory s názvem "MSBuild*NodeId*.log". Můžete použít **/fileLoggerParameters** přepínač tak, aby zadejte umístění souborů a další parametry fileLogger.<br /><br /> Pokud název souboru protokolu pomocí **/fileLoggerParameters** přepínače, distribuované protokolovacího nástroje použije název jako šablona a připojit ID uzlu tohoto názvu při vytváření souboru protokolu pro každý uzel.|  
|/distributedlogger:<br /><br /> `central logger`*<br /><br /> `forwarding logger`|/DL:`central logger`*`forwarding logger`|Protokol události z nástroje MSBuild, připojení instanci a jiné protokoly na všech uzlech. Pokud chcete zadat víc protokolovacích nástrojů, zadejte každý protokolovacího nástroje samostatně.<br /><br /> Syntaxe protokolovacího nástroje se používá k určení protokolovacího nástroje. Protokolovač syntaxe, najdete v článku **/logger** přepínač níže.<br /><br /> Následující příklady ukazují, jak pomocí tohoto přepínače:<br /><br /> `/dl:XMLLogger,MyLogger,Version=1.0.2,Culture=neutral`<br /><br /> `/dl:MyLogger,C:\My.dll*ForwardingLogger,C:\Logger.dll`|  
|/fileLogger<br /><br /> *[počet]*|/FL [`number`]|Protokolování výstupu sestavení do jednoho souboru v aktuálním adresáři. Pokud nezadáte `number`, výstupní soubor jmenuje msbuild.log. Pokud zadáte `number`, výstupní soubor jmenuje msbuild`n`.log, kde n je `number`. `Number`může být číslici od 1 do 9.<br /><br /> Můžete použít **/fileLoggerParameters** přepínače k určení umístění souboru a další parametry fileLogger.|  
|/fileloggerparameters: [číslo]<br /><br /> `parameters`|/FLP: [ `number`]`parameters`|Určuje žádné další parametry pro protokoly souborů a souborů DFS protokolovacího nástroje. Přítomnost tento přepínač vyplývá, že odpovídající /**filelogger [**`number`**]** je zadán přepínač. `Number`může být číslici od 1 do 9.<br /><br /> Můžete použít všechny parametry, které jsou uvedené pro **/consoleloggerparameters**. Můžete také použít jeden nebo více z následujících parametrů:<br /><br /> -   **Soubor protokolu**. Cesta k souboru protokolu, do které se zapisují protokolu sestavení. Protokolovač souborů DFS předpony tuto cestu do názvy její soubory protokolu.<br />-   **Připojit**. Určuje, zda v protokolu sestavení se připojí k souboru protokolu nebo přepíše. Když nastavíte přepínač, protokolu sestavení se připojuje k souboru protokolu. Pokud přepínač není přítomen, se přepíší obsah existující soubor protokolu.<br />     Pokud zahrnete připojení přepínače, bez ohledu na to, jestli je nastavená na hodnotu true nebo false, připojí se v protokolu. Pokud neuvedete přepínač připojit, v protokolu se přepíše.<br />     V takovém případě je přepsat soubor:`msbuild myfile.proj /l:FileLogger,Microsoft.Build.Engine;logfile=MyLog.log`<br />     V takovém případě je připojen soubor:`msbuild myfile.proj /l:FileLogger,Microsoft.Build.Engine;logfile=MyLog.log;append=true`<br />     V takovém případě je připojen soubor:`msbuild myfile.proj /l:FileLogger,Microsoft.Build.Engine;logfile=MyLog.log;append=false`<br />-   **Kódování**. Určuje kódování souboru (například ve formátu UTF-8, Unicode nebo ASCII).<br /><br /> Následující příklad vytvoří samostatné soubory protokolu pro chyby a varování:<br /><br /> `/flp1:logfile=errors.txt;errorsonly /flp2:logfile=warnings.txt;warningsonly`<br /><br /> Následující příklady ukazují další možnosti:<br /><br /> `/fileLoggerParameters:LogFile=MyLog.log;Append; Verbosity=diagnostic;Encoding=UTF-8`<br /><br /> `/flp:Summary;Verbosity=minimal;LogFile=msbuild.sum`<br /><br /> `/flp1:warningsonly;logfile=msbuild.wrn`<br /><br /> `/flp2:errorsonly;logfile=msbuild.err`|  
|/binaryLogger [: [LogFile =]`output.binlog`[; ProjectImports = [None, vložení, ZipFile]]]|/BL|Serializuje všechny události sestavení komprimované binární soubor. Ve výchozím nastavení soubor je v aktuálním adresáři a s názvem `msbuild.binlog`. Binární protokol je podrobný popis procesu sestavení, který můžete později se používá k rekonstrukci textové protokoly a pomocí jiných nástrojů pro analýzu. Binární protokol je obvykle 10-20 x menší než nejpodrobnější textový protokol diagnostiky úrovni, ale obsahuje další informace.<br /><br />Binární protokolovacího nástroje ve výchozím nastavení shromažďuje text zdrojové soubory projektu, včetně všech importovaných projekty a zaměřením došlo během sestavení. Volitelné `ProjectImports` přepínač ovládací prvky toto chování:<br /><br /> -   **ProjectImports = None**. Neshromažďujeme importy projektu.<br /> -   **ProjectImports = vložení**. Vložení importy projektu v souboru protokolu (výchozí).<br /> -   **ProjectImports = ZipFile**. Uložte soubory projektu do `output.projectimports.zip` kde `output` je stejný název jako název souboru binárního protokolu.<br /><br />Výchozí nastavení pro ProjectImports je vložení.<br />**Poznámka:**: protokolovacího nástroje neshromažďuje bez MSBuild zdrojové soubory, jako `.cs`, `.cpp` atd.<br />A `.binlog` soubor lze "přehrát" jej do předáním `msbuild.exe` jako argument místo projekt nebo řešení. Další protokolovacích nástrojů se zobrazí informace obsažené v souboru protokolu, jako kdyby byla děje původní sestavení. Další informace o binární protokol a jeho použití v: https://github.com/Microsoft/msbuild/wiki/Binary-Log <br /><br />**Příklady**:<br /> -   `/bl`<br /> -    `/bl:output.binlog`<br /> -   `/bl:output.binlog;ProjectImports=None`<br /> -   `/bl:output.binlog;ProjectImports=ZipFile`<br /> -   `/bl:..\..\custom.binlog`<br /> -   `/binaryLogger`|
|/Logger:<br /><br /> `logger`|l:`logger`|Určuje pro použití k protokolování událostí z nástroje MSBuild protokolovacího nástroje. Pokud chcete zadat víc protokolovacích nástrojů, zadejte každý protokolovacího nástroje samostatně.<br /><br /> Použijte následující syntaxi pro `logger`:`[``LoggerClass``,]``LoggerAssembly``[;``LoggerParameters``]`<br /><br /> Použijte následující syntaxi pro `LoggerClass`:`[``PartialOrFullNamespace``.]``LoggerClassName`<br /><br /> Nemusíte určit třídu protokolovač, pokud obsahuje přesně jeden protokolovacího nástroje sestavení.<br /><br /> Použijte následující syntaxi pro `LoggerAssembly`: `{``AssemblyName``[,``StrongName``] &#124;``AssemblyFile``}`<br /><br /> Protokolovač parametry jsou volitelné a jsou předávány protokolovacího nástroje přesně tak, jak je zadat.<br /><br /> Následující příklady používají **/logger** přepínače.<br /><br /> `/logger:XMLLogger,MyLogger,Version=1.0.2,Culture=neutral`<br /><br /> `/logger:XMLLogger,C:\Loggers\MyLogger.dll;OutputAsHTML`|  
|/noconsolelogger|/noconlog|Zakažte protokolovacího nástroje konzoly výchozí a není protokolování událostí, ke konzole.|  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří `rebuild` cíl `MyProject.proj` projektu.  
  
```  
MSBuild.exe MyProject.proj /t:rebuild  
```  
  
## <a name="example"></a>Příklad  
 MSBuild.exe můžete provádět složitější sestavení. Například můžete použít pro sestavování specifických cílů konkrétní projekty v řešení. Následující příklad znovu sestaví projekt `NotInSolutionFolder` a vyčistí projektu `InSolutionFolder`, což je v `NewFolder` složce řešení.  
  
```  
msbuild SlnFolders.sln /t:NotInSolutionfolder:Rebuild;NewFolder\InSolutionFolder:Clean  
```  
  
## <a name="see-also"></a>Viz také  
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Obecné vlastnosti projektu nástroje MSBuild](../msbuild/common-msbuild-project-properties.md)
