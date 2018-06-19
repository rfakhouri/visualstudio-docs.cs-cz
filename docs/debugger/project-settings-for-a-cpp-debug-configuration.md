---
title: Nastavení pro konfiguraci ladění jazyka C++ projektu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- VC.Project.VCDebugSettings.WebBrowser.DebuggerType
- VC.Project.IVCGPUDebugPageObject.EnvironmentMerge
- VC.Project.VCDebugSettings.SymbolPath
- VC.Project.IVCClusterDebugPageObject.ApplicationCommand
- VC.Project.IVCRemoteDebugPageObject.WorkingDirectory
- VC.Project.VCDebugSettings.DebuggerType
- VC.Project.IVCLocalDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCRemoteDebugPageObject.SQLDebugging
- VC.Project.IVCRemoteDebugPageObject.Remote
- VC.Project.IVCGPUDebugPageObject.CommandArguments
- VC.Project.VCDebugSettings.CommandArguments
- VC.Project.IVCClusterDebugPageObject.MPIRunWorkingDirectory
- VC.Project.IVCLocalDebugPageObject.SQLDebugging
- VC.Project.IVCWebSvcDebugPageObject.HttpUrl
- VC.Project.IVCLocalDebugPageObject.WorkingDirectory
- VC.Project.IVCLocalDebugPageObject.CommandArguments
- VC.Project.IVCClusterDebugPageObject.MPIRunCommand
- VC.Project.IVCGPUDebugPageObject.WorkingDirectory
- VC.Project.IVCWebSvcDebugPageObject.DebuggerType
- VC.Project.IVCRemoteDebugPageObject.CommandArguments
- VC.Project.IVCRemoteDebugPageObject.DebuggerType
- VC.Project.IVCLocalDebugPageObject.GPUBreakOnAllThreads
- VC.Project.IVCRemoteDebugPageObject.RemoteMachine
- VC.Project.IVCClusterDebugPageObject.MPIRunArguments
- VC.Project.IVCClusterDebugPageObject.MPIAcceptFilter
- VC.Project.IVCGPUDebugPageObject.RemoteConnection
- VC.Project.VCDebugSettings.PDBPath
- VC.Project.IVCRemoteDebugPageObject.DeploymentDirectory
- VC.Project.VCDebugSettings.SQLDebugging
- VC.Project.VCDebugSettings.RemoteCommand
- VC.Project.IVCClusterDebugPageObject.ShimCommand
- VC.Project.IVCLocalDebugPageObject.Command
- VC.Project.IVCRemoteDebugPageObject.GPUBreakOnAllThreads
- VC.Project.IVCLocalDebugPageObject.Attach
- VC.Project.VCDebugSettings.Command
- VC.Project.IVCRemoteDebugPageObject.GPUDebuggerTargetType
- VC.Project.IVCRemoteDebugPageObject.RemoteCommand
- VC.Project.IVCClusterDebugPageObject.ApplicationArguments
- VC.Project.IVCLocalDebugPageObject.Environment
- VC.Project.IVCGPUDebugPageObject.DeploymentDirectory
- VC.Project.IVCLocalDebugPageObject.EnvironmentMerge
- VC.Project.VCDebugSettings.Environment
- VC.Project.IVCGPUDebugPageObject.BreakpointBehavior
- VC.Project.IVCLocalDebugPageObject.DebuggerType
- VC.Project.VCDebugSettings.WebBrowser.WebBrowserDebuggerHttpUrl
- VC.Project.IVCWebSvcDebugPageObject.SQLDebugging
- VC.Project.IVCGPUDebugPageObject.AcceleratorType
- VC.Project.IVCGPUDebugPageObject.Environment
- VC.Project.VCDebugSettings.RemoteMachine
- VC.Project.IVCGPUDebugPageObject.AdditionalFilesToDeploy
- VC.Project.VCDebugSettings.WorkingDirectory
- vs.debug.builds
- VC.Project.VCDebugSettings.Attach
- VC.Project.VCDebugSettings.HttpUrl
- VC.Project.IVCClusterDebugPageObject.MPIAcceptMode
- VC.Project.IVCGPUDebugPageObject.Attach
- VC.Project.IVCRemoteDebugPageObject.AdditionalFiles
- VC.Project.IVCGPUDebugPageObject.Command
- VC.Project.VCDebugSettings.Remote
- VC.Project.IVCRemoteDebugPageObject.Attach
- VC.Project.VCDebugSettings.EnvironmentMerge
- VC.Project.IVCGPUDebugPageObject.MachineName
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- DEBUG linker option
- -PDB linker option
- -Zl compiler option [C++]
- /DEBUG linker option
- /PDBSTRIPPED linker option
- /MAPINFO linker option
- -Zd compiler option [C++]
- -DEBUG linker option
- MAPINFO linker option
- /ZI compiler option [C++]
- ZI compiler option [C++]
- Z7 compiler option [C++]
- debugging [C++], debugger settings
- project settings [Visual Studio], debug configurations
- mapfiles, project settings
- debug configurations, C++
- project settings [Visual Studio]
- /PDB linker option
- -PDBSTRIPPED linker option
- debug builds, project settings
- PDB linker option
- projects [Visual Studio], debug configurations
- project configurations, debug
- Zd compiler option [C++]
- MAP linker option
- /Z7 compiler option [C++]
- .pdb files, debug build project settings
- -MAP linker option
- -MAPINFO linker option
- /Zd compiler option [C++]
- PDBSTRIPPED linker option
- -Z7 compiler option [C++]
- pdb files, debug build project settings
- /MAP linker option
ms.assetid: 860c7f13-a108-4fe5-8fca-d235cd3ca1cb
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- cplusplus
ms.openlocfilehash: 6b323ab51f4be02faaddc1df7ab2dd6902323d63
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31479242"
---
# <a name="project-settings-for-a-c-debug-configuration"></a>Nastavení projektu pro konfiguraci ladění jazyka C++
Můžete změnit nastavení projektu pro konfiguraci ladění jazyka C nebo Visual C++ v **stránky vlastností** dialogové okno, jak je popsáno v [postupy: nastavení ladění a vydání konfigurace](../debugger/how-to-set-debug-and-release-configurations.md). Následující tabulky popisují kde najít nastavení souvisejících s ladicí program v **stránky vlastností** dialogové okno.  
  
> [!WARNING]
>  Nastavení projektu ladění na **konfigurace vlastnosti nebo ladění** kategorie pro aplikace UWP a součástí, které jsou napsané v jazyce C++ se liší. V tématu [spustit relaci ladění (jazyka Visual Basic, C#, C++ a XAML)](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md).  
  
 Zadejte které ladicí program pro použití v **ladicí program ke spuštění** pole se seznamem. Vaše volba bude mít vliv na vlastnosti, které jsou viditelné.  
  
 Nastavování vlastností ladění je automaticky zapsat a uložit do souboru "uživatelská" (. vcxproj.user) pro vaše řešení při každém uložení řešení.  
  
## <a name="configuration-properties-folder-debugging-category"></a>Konfigurace vlastností složky (kategorie ladění)  
  
|**Nastavení**|**Popis**|  
|-----------------|---------------------|  
|**Ladicí program ke spuštění**|Určuje ladicí program ke spuštění s následujícími možnostmi:<br /><br /> -   **Ladicí program místního systému Windows**<br />-   **Ladicí program vzdáleného systému Windows**<br />-   **Webové prohlížeče ladicí program**<br />-   **Ladicí program webové služby**|  
|**Příkaz** (ladicí program místního systému Windows)|Určuje příkaz pro spuštění programu, který ladíte v místním počítači.|  
|**Vzdálený příkaz** (ladicí program vzdáleného systému Windows)|Cesta pro .exe na vzdáleném počítači. Zadejte cestu, stejně, jako by ji zadat ve vzdáleném počítači.|  
|**Příkaz argumenty** (ladicí program místního systému Windows a ladicí program vzdáleného systému Windows)|-Určuje argumenty pro příkaz dříve zadaný.<br /><br /> V tomto poli můžete použít následující operátory přesměrování:<br /><br /> < `file`<br /> STDIN – čtení ze souboru.<br /><br /> > `file`<br /> Stdout zapisování do souboru.<br /><br /> >> `file`<br /> Stdout připojí k souboru.<br /><br /> 2> `file`<br /> Zapíše stderr do souboru.<br /><br /> 2>> `file`<br /> Připojí stderr do souboru.<br /><br /> 2> &1<br /> Odesílá výstup datového proudu stderr (2) na stejné umístění jako stdout (1).<br /><br /> 1> &2<br /> Odešle stdout (1) výstup do stejné umístění jako stderr (2).<br /><br /> Ve většině případů tyto operátory platí pouze pro konzolové aplikace.|  
|**Pracovní adresář**|Určuje pracovní adresář programu laděné relativní vzhledem k projektu adresáři, kde se nachází váš EXE. Pokud ji necháte prázdnou, pracovní adresář je adresář projektu. Pro vzdálené ladění adresáři projektu bude na vzdáleném serveru.|  
|**Připojte** (ladicí program místního systému Windows a ladicí program vzdáleného systému Windows)|Určuje, zda lze spustit nebo připojit k aplikaci. Výchozí nastavení je Ne.|  
|**Název vzdáleného serveru** (ladicí program vzdáleného systému Windows)|Určuje název počítače (jiné než váš), na kterém chcete ladit aplikace.<br /><br /> Makro sestavení vzdálený počítač je nastaven na hodnotu této vlastnosti; Další informace najdete v tématu [makra pro příkazy sestavení a vlastnosti](/cpp/ide/common-macros-for-build-commands-and-properties).|  
|**Připojení** (ladicí program vzdáleného systému Windows)|Umožňuje přepínat mezi typy připojení standardní a bez ověřování pro vzdálené ladění. Zadejte název vzdáleného počítače v **název vzdáleného serveru** pole. Typy připojení patří:<br /><br /> -   **Vzdálené pomocí ověřování systému Windows**<br />-   **Vzdálené bez jakéhokoli ověřování**<br /><br /> **Poznámka:** vzdáleného ladění pomocí bez ověřování může vést k vzdálenému počítači větší zranitelnosti narušení zabezpečení. Režim ověřování systému Windows je bezpečnější.<br /><br /> Další informace najdete v tématu [instalací vzdáleného ladění](../debugger/remote-debugging.md).|  
|**Adresa URL protokolu HTTP** (webové služby ladicího programu a ladicí program webové prohlížeče)|Určuje adresu URL, kde se nachází projektu, kterou ladíte.|  
|**Typ ladicí program**|Určuje typ ladicí program, který se má použít: **pouze nativní**, **spravovat pouze**, **GPU pouze**, **Mixed**, **automaticky**(výchozí), nebo **skriptu**.<br /><br /> -   **Nativní pouze** je pro nespravovaného kódu C++.<br />-   **Jenom spravované** je pro kód, který běží v rámci modul common language runtime (spravovaný kód).<br />-   **Smíšený** vyvolá ladicí programy pro spravovaných i nespravovaných kódu.<br />-   **Automatické** Určuje typ ladicí program na základě kompilátoru a EXE informace.<br />-   **Skript** vyvolá ladicí program pro skripty.<br />-   **Grafický procesor pouze** je pro C++ AMP kód, který běží na GPU zařízení nebo na umožňuje referenční dokumentace rozhraní DirectX. V tématu [ladění kódu GPU](../debugger/debugging-gpu-code.md).|  
|**Prostředí** (ladicí program místního systému Windows a ladicí program vzdáleného systému Windows)|Určuje proměnné prostředí pro aplikaci, kterou ladíte. Proměnné syntaxí standardní prostředí (například `PATH="%SystemRoot%\..."`). Tyto proměnné prostředí systému přepsat nebo jsou sloučeny s systémovém prostředí, v závislosti na **sloučení prostředí** nastavení. Když kliknete na tlačítko ve sloupci nastavení "upravit …" se zobrazí. Klikněte na tento odkaz pro úpravy proměnných prostředí.|  
|**Sloučení prostředí** (ladicí program místního systému Windows)|Určuje, zda proměnné, které jsou zadané v **prostředí** pole se sloučí s prostředím, která je definována v operačním systému. Výchozí nastavení je Ano.|  
|**Ladění SQL** (všechny kromě ladicí program clusteru MPI)|Povolí ladění na SQL procedury z vaší [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] aplikace. Výchozí nastavení je Ne.|  
|**Ladění typu akcelerátoru** (pouze GPU ladění)|Určuje GPU zařízení, které chcete používat pro ladění. Instalace ovladačů zařízení pro zařízení kompatibilní grafický procesor přidá další možnosti. Ve výchozím nastavení je "GPU - softwaru emulátor."|  
|**Grafický procesor výchozí chování zarážek** (pouze GPU ladění)|Určuje, zda má se vrhnout zarážek událostí pro každý podproces v osnově SIMD. Výchozí nastavení je pro vyvolání události zarážek pouze jednou za osnově.|  
|**Amp výchozí akcelerátoru**|Určuje výchozí AMP akcelerátor při ladění kódu GPU. Zvolte **OSNOVĚ softwaru akcelerátoru** zjistit, zda problém je způsoben hardware nebo ovladač místo kódu.|  
|**Nasazení Directory** (ladicí program vzdáleného systému Windows)|Určuje cestu na vzdáleném počítači, kde výstup projektu budou zkopírovaný před ke spuštění. Cesta může být sdílené síťové složky na vzdáleném počítači, nebo může být cesta ke složce na vzdáleném počítači. Výchozí nastavení je prázdný, což znamená, že výstup projektu není zkopírovány do sdílené síťové složky. Chcete-li povolit nasazení souborů, je nutné také vybrat **nasadit** políčko v dialogovém okně nástroje Configuration Manager. Další informace najdete v tématu [postupy: vytvoření a úprava konfigurací](../ide/how-to-create-and-edit-configurations.md).|  
|**Další soubory pro nasazení** (ladicí program vzdáleného systému Windows)|Pokud je nastavena adresáře nasazení, to je středníky oddělený seznam další soubory zkopírovat do adresáře nasazení. Výchozí nastavení je prázdný, což znamená, že žádné další soubory zkopírovaly do adresáře nasazení. Chcete-li povolit nasazení souborů, je nutné také vybrat **nasadit** políčko v dialogovém okně nástroje Configuration Manager. Další informace najdete v tématu [postupy: vytvoření a úprava konfigurací](../ide/how-to-create-and-edit-configurations.md).|  
|**Nasazení modulu Runtime knihoven Visual C++ ladění** (ladicí program vzdáleného systému Windows)|Pokud je nastavena adresáře nasazení, určuje to, zda knihovny ladění modulu runtime Visual C++ pro aktuální platformě musí by se měl zkopírovat do síťové složky. Výchozí nastavení je Ano.|  
  
## <a name="cc-folder-general-category"></a>Složka C/C++ (obecné kategorie)  
  
|Nastavení|Popis|  
|-------------|-----------------|  
|**Ladění formátu informací** ([/Z7, /Zd, Zi, /ZI](/cpp/build/reference/z7-zi-zi-debug-information-format))|Určuje typ informací ladění pro projekt.<br /><br /> Výchozí možnost (/ZI) vytvoří databázi programu (PDB) ve formátu kompatibilní upravit a pokračovat. Další informace najdete v tématu [/Z7, /Zd, / zi, /ZI (formát informace ladění)](/cpp/build/reference/z7-zi-zi-debug-information-format).|  
  
## <a name="cc-folder-optimization-category"></a>Složka C/C++ (optimalizace kategorie)  
  
|Nastavení|Popis|  
|-------------|-----------------|  
|**Optimalizace**|Určuje, zda by měl kompilátor optimalizovat kód, který vytváří. Optimalizace změní kód, který se spustí. Optimalizovaný kód už odpovídá zdrojového kódu. Proto je ladění složité.<br /><br /> Výchozí možnost (**zakázané (nebo 0d**) potlačí optimalizace. Můžete vyvíjet s optimalizací Potlačené a pak zapněte, když vytvoříte produkční verzi vašeho kódu.|  
  
## <a name="linker-folder-debugging-category"></a>Složka linkeru (ladění kategorie)  
  
|Nastavení|Popis|  
|-------------|-----------------|  
|**Generovat ladicí informace** ([/DEBUG](/cpp/build/reference/debug-generate-debug-info))|Informuje linkeru zahrnout informace o ladění, který bude mít s formátem zadaným /Z7, /Zd, Zi nebo /ZI.|  
|**Generování souboru databáze programu** ([/PDB:name](/cpp/build/reference/pdb-use-program-database))|Zadejte název souboru PDB v tomto poli. Musíte vybrat ZI nebo /Zi pro ladění formátu informací.|  
|**Odstranit privátní symboly** ([/PDBSTRIPPED:filename](/cpp/build/reference/pdbstripped-strip-private-symbols))|Zadejte název souboru PDB v tomto poli, pokud nechcete zahrnout do souboru PDB soukromých symbolů. Tato možnost vytvoří druhý soubor databáze (PDB), programu při vytvoření bitové kopie programu s žádným z kompilátoru nebo linkeru možnosti, které generují souboru PDB, jako je/Debug, /Z7, /Zd. Nebo /Zi. Tento druhý soubor PDB vynechá znaky, které byste neměli chtít dodávat zákazníkům. Další informace najdete v tématu [/PDBSTRIPPED (Odstranit privátní symboly)](/cpp/build/reference/pdbstripped-strip-private-symbols).|  
|**Generování souboru s mapováním** ([/MAP](/cpp/build/reference/map-generate-mapfile))|Informuje ke generování souboru s mapováním při propojování linkeru. Výchozí nastavení je Ne. Další informace najdete v tématu [/map (Generovat soubor mapování)](/cpp/build/reference/map-generate-mapfile).|  
|**Název souboru mapování** ([/MAP:](/cpp/build/reference/map-generate-mapfile)*název*)|Pokud si zvolíte generování souboru s mapováním, můžete v tomto poli souboru s mapováním. Další informace najdete v tématu [/map (Generovat soubor mapování)](/cpp/build/reference/map-generate-mapfile).|  
|**Mapování exportuje** ([/MAPINFO:EXPORTS](/cpp/build/reference/mapinfo-include-information-in-mapfile))|Zahrnuje exportovaných funkcí v souboru s mapováním. Výchozí nastavení je Ne. Další informace najdete v tématu [/MAPINFO (zahrnout informace do souboru mapování)](/cpp/build/reference/mapinfo-include-information-in-mapfile).|  
|**Debuggable sestavení** ([/ASSEMBLYDEBUG](/cpp/build/reference/mapinfo-include-information-in-mapfile))|Určuje nastavení pro Linkeru /ASSEMBLYDEBUG možnost. Možné hodnoty jsou následující:<br /><br /> -   **Žádný debuggable atribut vygenerované**.<br />-   **Sledování a zakázat optimalizace runtime (/ ASSEMBLYDEBUG)**. Toto je výchozí nastavení<br />-   **Žádné runtime sledování a povolit optimizations(/ASSEMBLYDEBUG:DISABLE)**.<br />-   **\<dědit z výchozích nastavení nadřazené nebo produktu project >**.<br />-Další informace najdete v tématu [/ASSEMBLYDEBUG (přidat atribut DebuggableAttribute)](/cpp/build/reference/assemblydebug-add-debuggableattribute).|  
  
 Tato nastavení ve složce vlastnosti konfigurace (ladění kategorie) můžete změnit programově pomocí rozhraní Microsoft.VisualStudio.VCProjectEngine.VCDebugSettings. Další informace naleznete v tématu <xref:Microsoft.VisualStudio.VCProjectEngine.VCDebugSettings>.

## <a name="other-project-settings"></a>Další nastavení projektu

K ladění typy projektů, jako je například statických knihoven a knihovny DLL, musí být schopen najít správný soubory projektu sady Visual Studio. Pokud zdrojový kód je k dispozici, můžete přidat statických knihoven a knihovny DLL jako samostatné projekty do stejného řešení (díky tomu easy ladění). Informace o vytváření tyto typy projektů najdete v tématu [vytváření a používání dynamického propojení knihovny (DLL)](/cpp/build/walkthrough-creating-and-using-a-dynamic-link-library-cpp) a [vytváření použití statické knihovny](/cpp/windows/walkthrough-creating-and-using-a-static-library-cpp). S zdrojový kód je k dispozici, můžete také vytvořit nový projekt Visual Studio výběrem **soubor > Nový > projekt z existujícího kódu**.

Ladění knihoven DLL, které jsou externí vzhledem k projektu, najdete v tématu [projekty ladění knihoven DLL](../debugger/debugging-dll-projects.md#vxtskdebuggingdllprojectsexternal). Pokud potřebujete ladění projektu pro vlastní knihovny DLL, ale nebudete mít přístup k projektu pro volající aplikace, najdete v článku [ladění z projektu knihovny DLL](../debugger/how-to-debug-from-a-dll-project.md).
  
## <a name="see-also"></a>Viz také  
 [Ladění nativního kódu](../debugger/debugging-native-code.md)   
 [Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)   
 [Vytváření a správa projektů Visual C++](/cpp/ide/creating-and-managing-visual-cpp-projects)   
 [/ ASSEMBLYDEBUG (přidat atribut DebuggableAttribute)](/cpp/build/reference/assemblydebug-add-debuggableattribute)   
 [Běžná makra pro příkazy a vlastnosti sestavení](/cpp/ide/common-macros-for-build-commands-and-properties)