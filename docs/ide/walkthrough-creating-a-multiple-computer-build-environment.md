---
title: "Návod: Vytváření více počítačů sestavení prostředí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSBuild, building on multiple computers
- build environment, MSBuild
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 65b4394b0f06dbcf995e8924833870a455bba348
ms.sourcegitcommit: 36ab8429333b31f03992a9fe8fc669db8e09c968
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2018
---
# <a name="walkthrough-creating-a-multiple-computer-build-environment"></a>Postup: Vytvoření prostředí pro sestavení s použitím více počítačů

Můžete vytvořit prostředí sestavení v rámci vaší organizace instalace sady Visual Studio na hostitelském počítači a potom kopírování různých souborů a nastavení k jinému počítači tak, aby se mohl účastnit sestavení. Nemáte k instalaci sady Visual Studio v jiném počítači.

Tento dokument neuděluje práva k distribuci softwaru externě nebo poskytovat prostředí sestavení třetím stranám.

> Právní omezení<br /><br /> Tento dokument je poskytován na "jako-je" základ. Když jsme testovali podle kroků uvedených, Nedokážeme podrobně testování každých konfigurace. Pokusíme se s dalšími informacemi, které se naučili zachovat aktuální dokument. Informace a názory vyjádřené v tomto dokumentu včetně adres URL a dalších odkazů na internetové weby mohou změnit bez předchozího upozornění. Společnost Microsoft neposkytuje žádné záruky, vyjádřené nebo předpokládané, s ohledem na informacích uvedených v tomto poli. Můžete na sebe rizika spojená s jejím používáním.<br /><br /> Tento dokument neposkytuje jste žádná zákonná práva duševního vlastnictví produktů společnosti Microsoft. Můžete kopírovat a tento dokument použít pro interní referenční účely.<br /><br /> Nemáte žádnou povinnost poskytnout Microsoft jakékoli návrhy, komentáře nebo jinou zpětnou ("názory"), vztahující se k tomuto dokumentu. Odpojit poskytování zpětné vazby však lze v Products společnosti Microsoft a související specifikace nebo jiné dokumentace (dále souhrnně nazývané "Offerings Microsoft"), který pak vycházejí další třetí strany pro vývoj vlastních produkty. Podle toho, pokud poskytnete Microsoft Feedback na libovolnou verzi systému tento dokument nebo Offerings Microsoft na které se vztahují, souhlasíte: (a) společnosti Microsoft může volně používat, reprodukujte, licence, distribuci a jinak obchodně využívat vaši zpětnou vazbu v jakékoli aplikaci Microsoft Nabídka; (b) můžete také udělit třetím stranám bezplatně pouze ta patentová práva nutná pro povolení jiné produkty nebo rozhraní s konkrétní části Microsoft Product, které obsahují vaše zpětná vazba. a (c) vám nebude dát společnosti Microsoft zpětnou (i), ke které máte důvod se domnívat, podléhá všechny deklarace identity patentová, autorským či jiné duševní vlastnictví nebo práva jakékoli třetí strany; nebo subjektu (ii) s licenčními podmínkami, které hledat tak, aby vyžadovala zařadit všechny Microsoft Offering nebo odvozené od těchto zpětnou vazbu nebo jiné duševní vlastnictví společnosti Microsoft na licencovanou nebo jinak sdílet s jakékoli třetí strany.

Tento návod byl ověřen vůči následující operační systémy, spuštěním nástroje MSBuild v příkazovém řádku a pomocí Team Foundation Build.

- Windows 8 (x86 a x64)
- Windows 7 Ultimate
- Windows Server 2008 R2 Standard

 Po dokončení kroků v tomto návodu, můžete vytvořit tyto typy aplikací v prostředí více počítačů:

- C++ desktopové aplikace, které používají Windows 8 SDK
- Visual Basic a C# desktopové aplikace, které cílí na rozhraní .NET Framework 4.5

 Více počítačů prostředí nelze použít k vytvoření tyto typy aplikací:

- Aplikace UWP. Pro vývoj aplikací UWP, je nutné nainstalovat Visual Studio v počítači sestavení.
- Desktopové aplikace, které cílí na rozhraní .NET Framework 4 nebo dřívější. Pokud chcete vytvořit tyto typy aplikací, musíte nainstalovat Visual Studio nebo referenční sestavení rozhraní .NET a nástroje (ze sady Windows SDK 7.1) v počítači sestavení.

 Tento názorný postup je rozdělené do těchto částí:

- [Instalace softwaru v počítačích](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#InstallingSoftware)

- [Kopírování souborů z hostitelského počítače k počítači sestavení](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#CopyingFiles)

- [Vytváření nastavení registru](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#CreatingRegistry)

- [Nastavení proměnných prostředí v počítači sestavení](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#SettingEnvVariables)

- [Instalace nástroje MSBuild sestavení do globální mezipaměti sestavení (GAC) v počítači sestavení](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#InstallingMSBuildToGAC)

- [Vytváření projektů](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#BuildingProjects)

- [Vytváření prostředí pro sestavení tak, aby je bylo možné zkontrolovat do správy zdrojového kódu](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#CreatingForSourceControl)

## <a name="prerequisites"></a>Požadavky

- Visual Studio se zatížením vývoj aplikací .NET, který je nainstalovaný.

## <a name="InstallingSoftware">Instalace softwaru v počítačích</a>

Nejprve nastavte hostitelský počítač a potom nastavte počítač se sestavení.

Instalace sady Visual Studio na hostitelském počítači, vytvoříte, souborů a nastavení, které bude zkopírujte do počítače, sestavení později. Instalací sady Visual Studio x86 nebo x64 počítač, ale architektuře počítače sestavení musí odpovídat architektuře hostitelského počítače.

1. Na hostitelském počítači nainstalujte Visual Studio.

2. Na počítači, sestavení nainstalujte rozhraní .NET Framework 4.5. Pokud chcete ověřit, zda je nainstalován, ujistěte se, že hodnotu registru klíče HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full@Version začíná "4,5".

## <a name="CopyingFiles">Kopírování souborů z hostitelského počítače k počítači sestavení</a>

Tato část obsahuje kopírování konkrétních souborů, kompilátory, nástroje pro sestavení, MSBuild prostředky a nastavení registru z hostitelského počítače k počítači sestavení. Tyto pokyny předpokládají, že jste nainstalovali Visual Studio ve výchozím umístění na hostitelském počítači; Pokud jste nainstalovali v jiném umístění, upravte kroky odpovídajícím způsobem.

- Na x86 počítači, výchozí umístění je C:\Program Files\Microsoft Visual Studio 11.0\
- Na x64 počítači, výchozí umístění je C:\Program Files (x86) \Microsoft Visual Studio 11.0\

Všimněte si, že název složky, Program Files závisí na operační systém, který je nainstalován. Na x86 počítače, název je \Program Files\\; na x64 počítače, název je \Program Files (x86)\\. Bez ohledu na architekturu systému označuje tento návod ke složce Program Files jako % ProgramFiles %.

> [!NOTE]
> V počítači, sestavení všechny relevantní soubory musí být na stejné jednotce; písmeno jednotky pro ni však může být jiná než písmeno jednotky pro Visual Studio je nainstalován na hostitelském počítači. V každém případě musíte vzít v úvahu pro umístění souborů při vytváření položky registru, jak je popsáno dále v tomto dokumentu.

#### <a name="to-copy-the-windows-sdk-files-to-the-build-computer"></a>Kopírování souborů Windows SDK k sestavení počítači

1. Pokud máte pouze systému Windows SDK pro Windows 8 nainstalovaný, zkopírujte do počítače, sestavení těchto složkách rekurzivně od hostitelského počítače:

    - %ProgramFiles%\Windows Kits\8.0\bin\

    - %ProgramFiles%\Windows Kits\8.0\Catalogs\

    - %ProgramFiles%\Windows Kits\8.0\DesignTime\

    - %ProgramFiles%\Windows Kits\8.0\include\

    - %ProgramFiles%\Windows Kits\8.0\Lib\

    - %ProgramFiles%\Windows Kits\8.0\Redist\

    - %ProgramFiles%\Windows Kits\8.0\References\

     Pokud máte také tyto další sady Windows 8...

    - Microsoft Windows Assessment and Deployment Kit

    - Microsoft Windows Driver Kit

    - Microsoft Windows Hardware Certification Kit

     .. ty mohou být nainstalovány soubory do složky Kits\8.0\ %ProgramFiles%\Windows, které jsou uvedené v předchozím kroku, a jejich licenční podmínky nemusí povolovat práva sestavení serveru pro tyto soubory. Zkontrolujte licenční podmínky pro všechny nainstalované sady Windows k ověřte, zda soubory mohou být zkopírovány do počítače sestavení. Pokud s licenčními podmínkami Nepovolit sestavení serveru práva, odeberte soubory z počítače sestavení.

2. Zkopírujte následující rekurzivní složky z hostitelského počítače do počítače, sestavení:

    - %ProgramFiles%\Microsoft SDKs\Windows\v8.0A\bin\NETFX 4.0 Tools\

    - %ProgramFiles%\Common Files\Merge Modules\

    - %ProgramFiles%\Microsoft Visual Studio 11.0\VC\

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\Tools\ProjectComponents\

    - %ProgramFiles%\MSBuild\Microsoft.Cpp\v4.0\V110\

    - %ProgramFiles%\Reference Assemblies\Microsoft\Framework\\.NETCore\v4.5\

    - %ProgramFiles%\Reference Assemblies\Microsoft\Framework\\.NETFramework\v4.5\

3. Zkopírujte tyto soubory do počítače sestavení z hostitelského počítače:

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\IDE\msobj110.dll

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\IDE\mspdb110.dll

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\IDE\mspdbcore.dll

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\IDE\mspdbsrv.exe

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\IDE\msvcdis110.dll

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\Tools\makehm.exe

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\Tools\VCVarsQueryRegistry.bat

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\Tools\vsvars32.bat

4. Pouze v případě, že spustíte výstupy sestavení v počítači sestavení se vyžadují následující modulu runtime knihoven Visual C++ – například jako součást automatizované testování. Soubory jsou obvykle umístěny v jejích podsložkách 11.0\VC\redist\x86\ %ProgramFiles%\Microsoft Visual Studio nebo %ProgramFiles%\Microsoft Visual Studio 11.0\VC\redist\x64\ složku, v závislosti na architektuře systému. Na x86 systémy, kopie x86 binární soubory do složky \Windows\System32\. Na x64 systémy, kopie x86 binární soubory do složky Windows\SysWOW64\ a x64 binární soubory do složky Windows\System32\.

    - \Microsoft.VC110.ATL\atl110.dll

    - \Microsoft.VC110.CRT\msvcp110.dll

    - \Microsoft.VC110.CRT\msvcr110.dll

    - \Microsoft.VC110.CXXAMP\vcamp110.dll

    - \Microsoft.VC110.MFC\mfc110.dll

    - \Microsoft.VC110.MFC\mfc110u.dll

    - \Microsoft.VC110.MFC\mfcm110.dll

    - \Microsoft.VC110.MFC\mfcm110u.dll

    - \Microsoft.VC110.MFCLOC\mfc110chs.dll

    - \Microsoft.VC110.MFCLOC\mfc110cht.dll

    - \Microsoft.VC110.MFCLOC\mfc110deu.dll

    - \Microsoft.VC110.MFCLOC\mfc110enu.dll

    - \Microsoft.VC110.MFCLOC\mfc110esn.dll

    - \Microsoft.VC110.MFCLOC\mfc110fra.dll

    - \Microsoft.VC110.MFCLOC\mfc110ita.dll

    - \Microsoft.VC110.MFCLOC\mfc110jpn.dll

    - \Microsoft.VC110.MFCLOC\mfc110kor.dll

    - \Microsoft.VC110.MFCLOC\mfc110rus.dll

    - \Microsoft.VC110.OPENMP\vcomp110.dll

5. Zkopírujte následující soubory ze složky \Debug_NonRedist\x86\ nebo \Debug_NonRedist\x64\ do počítače sestavení, jak je popsáno v [Příprava testovací počítač k spustit spustitelný soubor ladění](/cpp/ide/preparing-a-test-machine-to-run-a-debug-executable). Žádné další soubory mohou být zkopírovány.

    - \Microsoft.VC110.DebugCRT\msvcp110d.dll

    - \Microsoft.VC110.DebugCRT\msvcr110d.dll

    - \Microsoft.VC110.DebugCXXAMP\vcamp110d.dll

    - \Microsoft.VC110.DebugMFC\mfc110d.dll

    - \Microsoft.VC110.DebugMFC\mfc110ud.dll

    - \Microsoft.VC110.DebugMFC\mfcm110d.dll

    - \Microsoft.VC110.DebugMFC\mfcm110ud.dll

    - \Microsoft.VC110.DebugOpenMP\vcomp110d.dll

##  <a name="CreatingRegistry">Vytváření nastavení registru</a>
 Je nutné vytvořit položky registru můžete nakonfigurovat nastavení pro MSBuild.

#### <a name="to-create-registry-settings"></a>Chcete-li vytvořit nastavení registru

1. Identifikujte nadřazenou složku pro položky registru. Všechny položky registru se vytvořil v rámci stejné nadřazený klíč. Na x86 počítač, nadřazený klíč je HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. Na x64 počítač nadřazený klíč je HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\. Bez ohledu na architekturu systému tento postup odkazuje na nadřazený klíč jako RegistryRoot %.

    > [!NOTE]
    > Pokud architektura hostitelský počítač se liší od počítače sestavení, ujistěte se, zda je pomocí klíče příslušné nadřazené na každém počítači. To je obzvláště důležité, pokud jste automatizaci procesu exportu.
    >
    > Pokud používáte jiné písmeno jednotky v počítači sestavení než ten, který používáte v hostitelském počítači, ujistěte se také, chcete-li změnit hodnoty položek registru tak, aby odpovídaly.

2. Vytvořte následující položky registru v počítači sestavení. Všechny tyto položky jsou řetězce (typ == "REG_SZ" v registru). Nastavte hodnoty těchto položek stejné jako hodnoty položek porovnatelný z hlediska na hostitelském počítači.

    - %RegistryRoot%\\.NETFramework\v4.0.30319\AssemblyFoldersEx\VCMSBuild Public Assemblies@(Default)

    - %RegistryRoot%\Microsoft SDKs\Windows\v8.0@InstallationFolder

    - %RegistryRoot%\Microsoft SDKs\Windows\v8.0A@InstallationFolder

    - %RegistryRoot%\Microsoft SDKs\Windows\v8.0A\WinSDK-NetFx40Tools@InstallationFolder

    - %RegistryRoot%\Microsoft SDKs\Windows\v8.0A\WinSDK-NetFx40Tools-x86@InstallationFolder

    - % RegistryRoot %\VisualStudio\11.0@Source adresáře

    - %RegistryRoot%\VisualStudio\11.0\Setup\VC@ProductDir

    - %RegistryRoot%\VisualStudio\SxS\VC7@FrameworkDir32

    - %RegistryRoot%\VisualStudio\SxS\VC7@FrameworkDir64

    - %RegistryRoot%\VisualStudio\SxS\VC7@FrameworkVer32

    - %RegistryRoot%\VisualStudio\SxS\VC7@FrameworkVer64

    - %RegistryRoot%\VisualStudio\SxS\VC7@11.0

    - %RegistryRoot%\VisualStudio\SxS\VS7@11.0

    - %RegistryRoot%\Windows Kits\Installed Roots@KitsRoot

    - %RegistryRoot%\MSBuild\ToolsVersions\4.0\11.0@VCTargetsPath

    - %RegistryRoot%\MSBuild\ToolsVersions\4.0\11.0@VCTargetsPath10

    - %RegistryRoot%\MSBuild\ToolsVersions\4.0\11.0@VCTargetsPath11

     Na x64 sestavení počítače, také vytvořit následující položku registru a odkazovat na hostitelském počítači a zjistěte, jak ji nastavit.

    - %RegistryRoot%\Microsoft SDKs\Windows\v8.0A\WinSDK-NetFx40Tools-x64@InstallationFolder

     Pokud je počítač sestavení x64 a chcete použít 64bitovou verzi nástroje MSBuild, nebo pokud používáte službu sestavení sady Team Foundation Server na x64 počítače, musíte vytvořit následující položky registru v nativní 64bitové verze registru. Odkazovat na hostitelském počítači a zjistěte, jak nastavit tyto položky.

    - HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\11.0\Setup\VS@ProductDir

    - HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSBuild\ToolsVersions\4.0\11.0@VCTargetsPath

    - HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSBuild\ToolsVersions\4.0\11.0@VCTargetsPath10

    - HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSBuild\ToolsVersions\4.0\11.0@VCTargetsPath11

## <a name="SettingEnvVariables">Nastavení proměnných prostředí v počítači sestavení</a>

Použití nástroje MSBuild v počítači sestavení, je nutné nastavit proměnné prostředí PATH. Můžete nastavit proměnné vcvarsall.bat, nebo můžete ručně nakonfigurovat.

### <a name="to-use-vcvarsallbat-to-set-environment-variables"></a>Nastavení proměnných prostředí pomocí vcvarsall.bat

- Otevřete okno příkazového řádku na počítači sestavení a spuštění 11.0\VC\vcvarsall.bat % Program Files%\Microsoft Visual Studio. Argument příkazového řádku můžete použít k určení sady nástrojů, které chcete použít – x86, nativní x64 nebo x64 mezi kompilátoru. Pokud nezadáte argument příkazového řádku, x86 nástrojů se používá.

     Tato tabulka popisuje podporované argumenty pro vcvarsall.bat:

    |Vcvarsall.bat argument|Kompilátoru|Architektura počítačových sestavení|Vytvoření výstupní architektura|
    |----------------------------|--------------|---------------------------------|-------------------------------|
    |x86 (výchozí)|Nativní 32-bit|x86, x64|x86|
    |x86_amd64|x64 mezi|x86, x64|x64|
    |amd64|x64 nativní|x64|x64|

     Pokud vcvarsall.bat úspěšném spuštění – to znamená, se nezobrazí žádná zpráva o chybě – můžete přeskočit na další krok a pokračujte v [MSBuild instalace sestavení do globální mezipaměti sestavení (GAC) v počítači sestavení](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#InstallingMSBuildToGAC) část v tomto dokumentu .

### <a name="to-manually-set-environment-variables"></a>Chcete-li ručně nastavit proměnné prostředí

1. Jak ručně nakonfigurovat prostředí příkazového řádku, přidáte tuto cestu do proměnné prostředí PATH:

    - % Program Files%\Microsoft Visual Studio 11.0\Common7\IDE

2. Volitelně můžete také přidat následující cesty do proměnné PATH, aby bylo snazší pomocí nástroje MSBuild můžete vytvářet řešení.

     Pokud chcete použít nativní MSBuild 32-bit, přidejte tyto cesty do proměnné PATH:

    - %Program Files%\Microsoft SDKs\Windows\v8.0A\bin\NETFX 4.0 Tools

    - %windir%\Microsoft.NET\Framework\v4.0.30319

     Pokud chcete použít nativní MSBuild 64-bit, přidejte tyto cesty do proměnné PATH:

    - %Program Files%\Microsoft SDKs\Windows\v8.0A\bin\NETFX 4.0 Tools\x64

    - %windir%\Microsoft.NET\Framework64\v4.0.30319

## <a name="InstallingMSBuildToGAC">Instalace nástroje MSBuild sestavení do globální mezipaměti sestavení (GAC) v počítači sestavení</a>

MSBuild vyžaduje některá další sestavení, které se nainstalují do mezipaměti GAC v počítači sestavení.

1. Zkopírujte následující sestavení z hostitelského počítače do počítače, sestavení. Vzhledem k tomu, že se nainstalují do mezipaměti GAC, nezávisle na tom, kde je umístěna v počítači sestavení.

    - %ProgramFiles%\MSBuild\Microsoft.Cpp\v4.0\v110\Microsoft.Build.CPPTasks.Common.v110.dll

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\IDE\CommonExtensions\Microsoft\VC\Project\Microsoft.VisualStudio.Project.VisualC.VCProjectEngine.dll

    - %ProgramFiles%\Microsoft Visual Studio 11.0\Common7\IDE\PublicAssemblies\Microsoft.VisualStudio.VCProjectEngine.dll

2. Instalace sestavení do mezipaměti GAC, vyhledejte v počítači sestavení gacutil.exe – obvykle je v nástrojích 4.0 SDKs\Windows\v8.0A\bin\NETFX %ProgramFiles%\Microsoft\\. Pokud tuto složku nelze najít, opakujte kroky v [kopírování souborů z hostitelského počítače k počítači sestavení](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#CopyingFiles) části tohoto názorného postupu.

     Otevřete okno příkazového řádku, který má práva správce a spusťte tento příkaz pro každý soubor:

     **gacutil -i \<file>**

    > [!NOTE]
    > Restartování může být nutný pro sestavení se plně nainstalovat do mezipaměti GAC.

## <a name="BuildingProjects">Vytváření projektů</a>

Team Foundation Build můžete použít k vytvoření [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] projekty a řešení nebo můžete vytvořit je na příkazovém řádku. Pokud používáte Team Foundation Build k sestavení projektů, vyvolá MSBuild spustitelného souboru, která odpovídá architektuře systému. Na příkazovém řádku můžete použít MSBuild 32bitové nebo 64bitové MSBuild a architektura nástroje MSBuild můžete vybrat nastavením proměnné prostředí PATH nebo přímo vyvoláním nástroje MSBuild specifické pro architekturu spustitelný soubor.

Pokud chcete používat msbuild.exe na příkazovém řádku, spusťte následující příkaz, ve kterém *solution.sln* je zástupný symbol pro název vašeho řešení.

**msbuild** *solution.sln*

Další informace o tom, jak pomocí nástroje MSBuild v příkazovém řádku najdete v tématu [Reference k příkazovému řádku](../msbuild/msbuild-command-line-reference.md).

> [!NOTE]
> K vytvoření [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] projekty, je nutné použít sada nástrojů platformy "v110". Pokud chcete upravit [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] soubory projektu, sada nástrojů platformy můžete nastavit pomocí tento argument příkazového řádku:
>
> **msbuild** *solution.sln* **/p:PlatformToolset=v110**

## <a name="CreatingForSourceControl">Vytváření prostředí pro sestavení tak, aby je bylo možné zkontrolovat do správy zdrojového kódu</a>

Můžete vytvořit prostředí sestavení, které můžou být nasazené do různých počítačů a nevyžaduje GAC'ing soubory nebo změny nastavení registru. Následující kroky jsou pouze jeden způsob, jak dosáhnout. Přizpůsobíte postup jedinečných charakteristik prostředí sestavení.

> [!NOTE]
> Je nutné zakázat přírůstkové sestavování tak, aby tracker.exe nezpůsobí výjimku chybu během sestavení. Přírůstkové sestavování zakázat, nastavte tento parametr sestavení:
>
> **msbuild** *solution.sln* **/p:TrackFileAccess=false**

1. Vytvořte adresář "Skladu" na hostitelském počítači.

     Tyto kroky odkazují na adresář jako skladu %.

2. Kopírování adresářů a souborů, jak je popsáno v [kopírování souborů z hostitelského počítače k počítači sestavení](../ide/walkthrough-creating-a-multiple-computer-build-environment.md#CopyingFiles) části tohoto názorného postupu, s výjimkou vložit v adresáři % skladu %, kterou jste právě vytvořili. Například zkopírovat z %ProgramFiles%\Windows Kits\8.0\bin\ do %Depot%\Windows Kits\8.0\bin\\.

3. Když jsou soubory vložili ve skladu %, proveďte tyto změny:

    - V % Depot%\MSBuild\Microsoft.Cpp\v4.0\v110\Microsoft.CPP.Targets \Microsoft.Cpp.InvalidPlatforms.targets\\, \Microsoft.cppbuild.targets\\a \Microsoft.CppCommon.targets\\, změňte všechny instance z

         AssemblyName="Microsoft.Build.CppTasks.Common.v110, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"

         až

         AssemblyFile="$(VCTargetsPath11)Microsoft.Build.CppTasks.Common.v110.dll".

         Bývalé pojmenování spoléhá na sestavení se GAC'ed.

    - % Skladu % \MSBuild\Microsoft.Cpp\v4.0\v110\Microsoft.CPPClean.Targets změňte všechny instance řetězce

         AssemblyName="Microsoft.Build.CppTasks.Common.v110, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a"

         až

         AssemblyFile="$(VCTargetsPath11)Microsoft.Build.CppTasks.Common.v110.dll".

4. Vytvořte soubor PROPS – například Partner.AutoImports.props—and umístí jej v kořenové složce, která obsahuje vaše projekty. Tento soubor se používá k nastavení proměnných, které jsou používány MSBuild k vyhledání různých prostředků. Pokud proměnné nejsou nastaveny podle tohoto souboru, nastavení ostatní soubory props a .TARGETS – soubory, které jsou závislé na hodnoty registru. Protože jsme se nastavení hodnoty registru, tyto proměnné by být prázdné a sestavení skončí s chybou. Místo toho přidejte to Partner.AutoImports.props:

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <!-- This file must be imported by all project files at the top of the project file. -->
    <Project ToolsVersion="4.0"
    xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    <PropertyGroup>
    <VCTargetsPath>$(DepotRoot)MSBuild\Microsoft.Cpp\v4.0\v110\</VCTargetsPath>
    <VCTargetsPath11>$(DepotRoot)MSBuild\Microsoft.Cpp\v4.0\v110\</VCTargetsPath11>
    <MSBuildExtensionsPath>$(DepotRoot)MSBuild</MSBuildExtensionsPath>
    <MSBuildExtensionsPath32>$(DepotRoot)MSBuild</MSBuildExtensionsPath32>
    <VCInstallDir_110>$(DepotRoot)Microsoft Visual Studio 11.0\VC\</VCInstallDir_110>
    <VCInstallDir>$(VCInstallDir_110)</VCInstallDir>
    <WindowsKitRoot>$(DepotRoot)Windows Kits\</WindowsKitRoot>
    <WindowsSDK80Path>$(WindowsKitRoot)</WindowsSDK80Path>
    <WindowsSdkDir_80>$(WindowsKitRoot)8.0\</WindowsSdkDir_80>
    <WindowsSdkDir>$(WindowsSDKDir_80)</WindowsSdkDir>
    <WindowsSdkDir_80A>$(DepotRoot)Microsoft SDKs\Windows\v8.0A\</WindowsSdkDir_80A>
    </PropertyGroup>
    </Project>
    ```

5. V každé z soubory projektu, přidejte následující řádek v horní části, po `<Project Default Targets...>` řádku.

    ```xml
    <Import Project="$([MSBuild]::GetDirectoryNameOfFileAbove($(MSBuildThisFileDirectory), Partner.AutoImports.props))\Partner.AutoImports.props"/>
    ```

6. Změna příkazového řádku prostředí následujícím způsobem:

    - Nastavit skladu =*umístění adresáře skladu, který jste vytvořili v kroku 1*

    - Cesta sady = % path %; *umístění nástroje MSBuild v počítači*; %D epot%\Windows\System32;%D epot%\Windows\SysWOW64;%D 11.0\Common7\IDE\ epot%\Microsoft sady Visual Studio

         O nativní 64bitové verze sestavení, přejděte na 64-bit MSBuild.

## <a name="see-also"></a>Viz také

[Příprava testovacího počítače ke spuštění ladicího spustitelného souboru](/cpp/ide/preparing-a-test-machine-to-run-a-debug-executable)  
[Referenční dokumentace k příkazovému řádku](../msbuild/msbuild-command-line-reference.md)