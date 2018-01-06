---
title: "Instalace aplikace izolované prostředí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Shell [Visual Studio], deploying shell-based applications
- Visual Studio shell, deploying shell-based applications
ms.assetid: 33416226-9083-41b5-b153-10d2bf35c012
caps.latest.revision: "40"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 6672ed634ad8c8056ae372c9d1d9a3fa44b56243
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="installing-an-isolated-shell-application"></a>Instalace aplikace izolované prostředí
Instalace aplikace pro prostředí provedením následujících kroků.  
  
-   Připravte řešení.  
  
-   Vytvořte balíček Instalační služby systému Windows (MSI) pro vaši aplikaci.  
  
-   Vytvořte zaváděcího nástroje Instalační program.  
  
 Všechny ukázkový kód v tomto dokumentu pochází z [prostředí nasazení ukázkové](http://go.microsoft.com/fwlink/?LinkId=262245), kterou si můžete stáhnout z galerie kódů na webu MSDN. Ukázka zobrazuje výsledky provádění jednotlivých kroků.  
  
## <a name="prerequisites"></a>Požadavky  
 Pokud chcete provést postupy, které toto téma popisuje, musí být v počítači nainstalované následující nástroje.  
  
-   Sada SDK Visual Studia  
  
-   [Sada nástrojů XML pro instalační program systému Windows](http://go.microsoft.com/fwlink/?LinkId=82720) verze 3.6  
  
 Ukázka také vyžaduje Microsoft Visualization a modelování SDK, která vyžadují ne všechny součásti pro.  
  
## <a name="preparing-your-solution"></a>Příprava řešení  
 Ve výchozím nastavení prostředí Shell šablony sestavení VSIX balíčků, ale toto chování je určena především pro účely ladění. Když nasadíte aplikaci prostředí, je nutné použít balíčky MSI umožňuje pro přístup k registru a restartování během instalace. Příprava aplikace pro nasazení MSI, proveďte následující kroky.  
  
#### <a name="to-prepare-a-shell-application-for-msi-deployment"></a>Příprava prostředí pro aplikace pro nasazení MSI  
  
1.  Upravte každý soubor .vsixmanifest ve vašem řešení.  
  
     V `Identifier` elementu, přidejte `InstalledByMSI` elementu a `SystemComponent` elementu a nastavte jejich hodnoty na `true`.  
  
     Tyto prvky zabránit pokusu o instalaci komponenty serveru a uživatel z je odinstalujete pomocí instalačního programu VSIX **rozšíření a aktualizace** dialogové okno.  
  
2.  Pro každý projekt, který obsahuje VSIX manifest upravte úlohami sestavení do výstupního obsah do umístění, ze kterého budou instalovat vaší MSI. Zahrnout VSIX manifest ve výstupu sestavení, ale nemáte sestavení soubor VSIX.  
  
## <a name="creating-an-msi-for-your-shell"></a>Vytvoření souboru MSI pro vaše prostředí  
 K vytvoření vašeho balíčku MSI, doporučujeme použít [sada nástrojů XML pro instalační program systému Windows](http://go.microsoft.com/fwlink/?LinkId=82720) protože nabízí větší flexibilitu než standardní projektu instalace.  
  
 V souboru Product.wxs nastavte bloky detekce a rozložení součásti prostředí.  
  
 Pak vytvořte položky registru, v souboru .reg pro vaše řešení a v ApplicationRegistry.wxs.  
  
### <a name="detection-blocks"></a>Detekce bloky  
 Blok detekce se skládá z `Property` element, který určuje, aby bylo možné zjistit a `Condition` element, který určuje zprávu, která vrátí, pokud není přítomna na počítači předpokladů. Například aplikace prostředí bude vyžadovat Microsoft prostředí sady Visual Studio redistributable a detekce bloku bude připomínat následující kód.  
  
```xml  
<Property Id="ISOSHELLSFX">  
  <RegistrySearch Id="IsoShellSfx" Root="HKLM" Key="Software\Microsoft\DevDiv\vs\Servicing\\$(var.ShellVersion)\IsoShell\$(var.ProductLanguage)" Name="Install" Type="raw" />  
</Property>  
<Property Id="INTSHELLSFX">  
  <RegistrySearch Id="IntShellSfx" Root="HKLM" Key="SOFTWARE\Microsoft\DevDiv\vs\Servicing\$(var.ShellVersion)\devenv\$(var.ProductLanguage)" Name="Install" Type="raw" />  
</Property>  
  
<Condition Message="This application requires $(var.IsoShellName).  Please install $(var.IsoShellName) then run this installer again.">  
  <![CDATA[Installed OR ISOSHELLSFX]]>  
</Condition>  
<Condition Message="This application requires $(var.IntShellName).  Please install $(var.IntShellName) then run this installer again.">  
  <![CDATA[Installed OR INTSHELLSFX]]>  
</Condition>  
  
```  
  
### <a name="layout-of-shell-components"></a>Rozložení součástí prostředí  
 Je nutné přidat elementy k identifikaci cílové adresářovou strukturu a součástí k instalaci.  
  
##### <a name="to-set-the-layout-of-shell-components"></a>Chcete-li nastavit rozložení součásti prostředí  
  
1.  Vytvořit hierarchii `Directory` prvky představující všechny adresáře vytvořit v systému souborů na cílovém počítači, jak ukazuje následující příklad.  
  
    ```xml  
    <Directory Id="TARGETDIR" Name="SourceDir">  
      <Directory Id="ProgramFilesFolder">  
        <Directory Id="CompanyDirectory" Name="$(var.CompanyName)">  
          <Directory Id="INSTALLDIR" Name="$(var.FullProductName)">  
            <Directory Id="ExtensionsFolder" Name="Extensions" />  
            <Directory Id="Folder1033" Name="1033" />  
          </Directory>  
        </Directory>  
      </Directory>  
      <Directory Id="ProgramMenuFolder">  
        <Directory Id="ApplicationProgramsFolder" Name="$(var.FullProductName)"/>  
      </Directory>  
    </Directory>  
    ```  
  
     Tyto adresáře jsou označovány pomocí `Id` Pokud jsou zadány soubory, které musí být nainstalován.  
  
2.  Určete součásti, které prostředí a aplikace prostředí vyžadují, jak ukazuje následující příklad.  
  
    > [!NOTE]
    >  Některé prvky mohou odkazovat na definice v ostatních WXS souborů.  
  
    ```xml  
    <Feature Id="ProductFeature" Title="$(var.ShortProductName)Shell" Level="1">  
      <ComponentGroupRef Id="ApplicationGroup" />  
      <ComponentGroupRef Id="HelpAboutPackage" />  
      <ComponentRef Id="GeneralProfile" />  
      <ComponentGroupRef Id="EditorAdornment"/>        
      <ComponentGroupRef Id="SlideShowDesignerGroup"/>  
  
      <!-- Note: The following ComponentGroupRef is required to pull in generated authoring from project references. -->  
      <ComponentGroupRef Id="Product.Generated" />  
    </Feature>  
    ```  
  
    1.  `ComponentRef` Element odkazuje na jiný soubor WXS, který identifikuje soubory, které aktuální součást vyžaduje. Například GeneralProfile má následující definice v HelpAbout.wxs.  
  
        ```xml  
        <Fragment Id="FragmentProfiles">  
          <DirectoryRef Id="INSTALLDIR">  
            <Directory Id="ProfilesFolder" Name="Profiles">  
              <Component Id='GeneralProfile' Guid='*'>  
                <File Id='GeneralProfile' Name='General.vssettings' DiskId='1' Source='$(var.BuildOutputDir)Profiles\General.vssettings' KeyPath='yes' />  
              </Component>  
            </Directory>  
          </DirectoryRef>  
        </Fragment>  
        ```  
  
         `DirectoryRef` Element určuje, kde se tyto soubory přejděte v počítači uživatele. `Directory` Element určuje, že bude nainstalována do podadresář a každý `File` element reprezentuje soubor, který je integrovaný nebo která existuje v rámci řešení a identifikuje, které tento soubor lze nalézt vytvoření souboru MSI.  
  
    2.  `ComponentGroupRef` Element odkazuje na skupinu další součásti (nebo součásti a součásti skupiny). Například `ComponentGroupRef` pod ApplicationGroup je definován následujícím způsobem v Application.wxs.  
  
        ```xml  
        <ComponentGroup Id="ApplicationGroup">  
          <ComponentGroupRef Id="DebuggerProxy" />  
          <ComponentRef Id="MasterPkgDef" />  
          <ComponentRef Id="SplashResource" />  
          <ComponentRef Id="IconResource" />  
          <ComponentRef Id="WinPrfResource" />  
          <ComponentRef Id="AppExe" />  
          <ComponentRef Id="AppConfig" />  
          <ComponentRef Id="AppPkgDef" />  
          <ComponentRef Id="AppPkgDefUndef" />  
          <ComponentRef Id="$(var.ShortProductName)UI1033" />  
          <ComponentRef Id="ApplicationShortcut"/>  
          <ComponentRef Id="ApplicationRegistry"/>  
        </ComponentGroup>  
        ```  
  
    > [!NOTE]
    >  Vyžaduje se závislostí pro aplikace, prostředí Shell (Izolovaná): DebuggerProxy, MasterPkgDef, prostředky (zejména soubor .winprf), aplikace a PkgDefs.  
  
### <a name="registry-entries"></a>Položky registru  
 Šablona projektu prostředí (Izolovaná) zahrnuje *ProjectName*soubor .reg pro klíče registru sloučit na instalaci. Tyto položky registru musí být součástí souboru MSI pro instalaci a čištění účely. Musíte taky vytvořit odpovídající registru bloky v ApplicationRegistry.wxs.  
  
##### <a name="to-integrate-registry-entries-into-the-msi"></a>K integraci položky registru do MSI  
  
1.  V **vlastního nastavení prostředí** složku, otevřete *ProjectName*. reg.  
  
2.  Nahraďte všechny výskyty $RootFolder$ token s cestou cílový instalační adresář.  
  
3.  Přidáte žádné další položky registru, které vaše aplikace vyžaduje.  
  
4.  Otevřete ApplicationRegistry.wxs.  
  
5.  Pro každou položku registru v *ProjectName*.reg, přidejte blok odpovídající registru jako následující příklady zobrazují.  
  
    |*Název projektu*.reg|ApplicationRegisty.wxs|  
    |-----------------------|----------------------------|  
    |[HKEY_CLASSES_ROOT\CLSID\\{bb431796-a179-4df7-b65d-c0df6bda7cc6}]<br /><br /> @= "PhotoStudio DTE objekt"|\<RegistryKey Id = 'DteClsidRegKey' kořenové = 'HKCR' Key = "$(var. DteClsidRegKey), akce = 'createAndRemoveOnUninstall' ><br /><br /> \<Hodnota RegistryValue typ = 'řetězec' Name =' @' Hodnota =' $(var. Objekt ShortProductName) DTE "/ ><br /><br /> \</ RegistryKey >|  
    |[HKEY_CLASSES_ROOT\CLSID\\\LocalServer32 {bb431796-a179-4df7-b65d-c0df6bda7cc6}]<br /><br /> @= "$RootFolder$\PhotoStudio.exe"|\<RegistryKey Id = 'DteLocSrv32RegKey' kořenové = 'HKCR' Key = "$(var. \LocalServer32 DteClsidRegKey), akce = 'createAndRemoveOnUninstall' ><br /><br /> \<Hodnota RegistryValue typ = 'řetězec' Name =' @' Hodnota = "[INSTALLDIR] $(var. .Exe ShortProductName) "/ ><br /><br /> \</ RegistryKey >|  
  
     V tomto příkladu Var.DteClsidRegKey přeloží na klíč registru v horním řádku. Var.ShortProductName přeloží na `PhotoStudio`.  
  
## <a name="creating-a-setup-bootstrapper"></a>Vytváření instalační program zaváděcího nástroje  
 Vaše dokončené MSI se nainstaluje jenom v případě, že všechny součásti jsou nainstalovány nejdřív. K usnadnění činnost koncového uživatele, vytvořte instalační program, který shromáždí a nainstaluje všechny požadované součásti před instalací aplikace. Chcete-li zajistit úspěšnou instalaci, proveďte tyto akce:  
  
-   Vynuťte instalaci správcem.  
  
-   Zjistí, zda je nainstalována prostředí sady Visual Studio (Izolovaná).  
  
-   Spusťte jeden nebo oba prostředí instalační programy v pořadí.  
  
-   Zpracujte požadavky na restartování.  
  
-   Spuštění vaší MSI.  
  
### <a name="enforcing-installation-by-administrator"></a>Vynucování instalace správce  
 Tento postup je nutný pro povolení Instalační program přístup k požadované adresáře například \Program Files\\.  
  
##### <a name="to-enforce-installation-by-administrator"></a>K vynucení instalace správce  
  
1.  Otevřete místní nabídku pro projekt instalace a potom zvolte **vlastnosti**.  
  
2.  V části **konfigurační soubor vlastnosti/Linkeru/Manifest**, nastavte **úroveň spuštění nástroje Řízení uživatelských účtů** k **requireAdministrator**.  
  
     Tato vlastnost převádí atribut, který vyžaduje program, který chcete spustit jako správce do vloženého souboru manifestu.  
  
### <a name="detecting-shell-installations"></a>Zjišťování prostředí instalací  
 Pokud chcete zjistit, jestli se musí nainstalovat prostředí sady Visual Studio (Izolovaná), nejprve určete, zda je již nainstalována kontrolou hodnotu registru HKLM\Software\Microsoft\DevDiv\vs\Servicing\ShellVersion\isoshell\LCID\Install.  
  
> [!NOTE]
>  Tyto hodnoty jsou také číst bloku detekce prostředí v Product.wxs.  
  
 HKLM\Software\Microsoft\AppEnv\14.0\ShellFolder Určuje umístění, kde byla nainstalována prostředí sady Visual Studio, a můžete zkontrolovat, že soubory.  
  
 Příklad detekce instalace prostředí, najdete v článku `GetProductDirFromReg` funkce Utilities.cpp v ukázce prostředí nasazení.  
  
 Pokud jeden nebo oba Visual Studio prostředí shell, která vyžaduje váš balíček není nainstalován v počítači, musíte je přidat do seznamu součástí k instalaci. Příklad, naleznete v části `ComponentsPage::OnInitDialog` funkce ComponentsPage.cpp v ukázce prostředí nasazení.  
  
### <a name="running-the-shell-installers"></a>Spuštění prostředí instalační programy  
 Pokud chcete spustit prostředí instalační programy, volání redistributables prostředí sady Visual Studio pomocí správné argumenty příkazového řádku. Minimálně je nutné použít argumenty příkazového řádku **/norestart /q** a sledovat návratový kód, chcete-li zjistit, co by mělo být provedeno další. Následující příklad spustí prostředí (Izolovaná) redistributable.  
  
```  
dwResult = ExecCmd("Vs_IsoShell.exe /norestart /q", TRUE);  
```  
  
### <a name="running-the-shell-language-pack-installers"></a>Spuštění instalační programy prostředí Language Pack  
 Pokud místo toho zjistíte, že byl nainstalován prostředí nebo prostředí shell a potřebovat pouze jazyk pack, jak ukazuje následující příklad můžete nainstalovat jazykové sady.  
  
```  
dwResult = ExecCmd("Vs_IsoShellLP.exe /norestart /q", TRUE);  
  
```  
  
### <a name="deciphering-return-values"></a>Úmysly nemůže dešifrovat návratové hodnoty  
 U některých operačních systémů v prostředí Visual Studio (Izolovaná) instalaci bude vyžadovat restartování. Tuto podmínku lze určit podle návratový kód volání `ExecCmd`.  
  
|Návratová hodnota|Popis|  
|------------------|-----------------|  
|ERROR_SUCCESS|Instalace byla dokončena. Nyní můžete nainstalovat aplikaci.|  
|ERROR_SUCCESS_REBOOT_REQUIRED|Instalace byla dokončena. Po restartování počítače, může nainstalovat aplikaci.|  
|3015|Probíhá instalace. Chcete-li pokračovat v instalaci je nutné restartovat počítač.|  
  
### <a name="handling-restarts"></a>Zpracování restartování  
 Pokud jste spustili instalační program prostředí pomocí **/norestart** argument, jste zadali, že by restartujte počítač nebo požádat o restartování počítače. Však může být vyžadován restart a ujistěte se, že instalačním programem vaší bude pokračovat po restartování počítače.  
  
 Chcete-li správně zpracovat restartování, ujistěte se, že pouze jeden instalační program je nastaven na obnovení a správně zpracovat proces obnovení.  
  
 Pokud je vrácen ERROR_SUCCESS_REBOOT_REQUIRED nebo 3015, kódu nutné restartovat počítač, než bude instalace pokračovat.  
  
 Pro zpracování restartování, proveďte tyto akce:  
  
-   Nastavení registru a obnovit instalaci při spuštění systému Windows.  
  
-   Proveďte dvojité restartování zaváděcí nástroj.  
  
-   Odstraňte klíč ResumeData prostředí Instalační služby.  
  
-   Restartování systému Windows.  
  
-   Obnovení cesty spustit soubor MSI.  
  
### <a name="setting-the-registry-to-resume-setup-when-windows-starts"></a>Nastavení registru na pokračovat v instalaci při spuštění systému Windows  
 Klíč registru HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\RunOnce\ provede při spuštění systému s oprávněními pro správu a pak je vymazat. HKEY_CURRENT_USER obsahuje podobné klíč, ale běží jako normální uživatelské a není vhodná pro instalace. Instalace může pokračovat v RunOnce klíč, který volá instalačním programem vaší umístěním řetězcovou hodnotu. Doporučujeme však volat instalační program pomocí **/restart** nebo podobný parametr upozornit aplikaci, která je obnovení místo spuštění. Můžete použít také parametry, které určují, kde se v procesu instalace, který je obzvláště užitečná v instalacích, které mohou vyžadovat více restartování.  
  
 Následující příklad ukazuje hodnoty klíče registru RunOnce pro pokračování instalace.  
  
 `"c:\MyAppInstaller.exe /restart /SomeOtherDataFlag"`  
  
### <a name="installing-double-restart-of-bootstrapper"></a>Instalace dvojité restartování zaváděcího nástroje  
 Pokud se instalační program používá přímo z RunOnce, nebude možné úplné načtení plochy. Chcete-li k dispozici úplné uživatelské rozhraní, musíte vytvořit jiné spuštění instalačního programu a ukončení RunOnce instance.  
  
 Instalační program je třeba spustit znovu, aby získal správná oprávnění, a je třeba mu dostatek informací, které potřebujete vědět, kde jste zastavili před restartováním počítače, jak ukazuje následující příklad.  
  
```  
if (_cmdLineInfo.IsRestart())  
{  
    TCHAR path[MAX_PATH]={0};  
    GetModuleFileName(NULL, path, MAX_PATH * sizeof(TCHAR));      
    ShellExecute( NULL, _T( "open" ), path, _T("/install"), 0, SW_SHOWNORMAL );  
}  
  
```  
  
### <a name="deleting-the-shell-installer-resumedata-key"></a>Odstranění klíče ResumeData instalační program prostředí  
 Instalační program prostředí nastaví klíč registru HKLM\Software\Microsoft\VisualStudio\14.0\Setup\ResumeData s daty v instalaci pokračovat po restartování. Vzhledem k tomu obnovuje vaší aplikace, není prostředí instalační program, odstraňte tento klíč registru, jak ukazuje následující příklad.  
  
```  
CString resumeSetupPath(MAKEINTRESOURCE("SOFTWARE\\Microsoft\\VisualStudio\\14.0\\Setup\\ResumeData"));  
RegDeleteKey(HKEY_LOCAL_MACHINE, resumeSetupPath);  
```  
  
### <a name="restarting-windows"></a>Restartování systému Windows  
 Jakmile nastavíte požadované klíče registru, můžete restartovat Windows. Následující příklad vyvolá příkazy restartování pro různé operační systémy Windows.  
  
```  
OSVERSIONINFO ov;  
HANDLE htoken ;  
//Ask for the SE_SHUTDOWN_NAME token as this is needed by the thread calling for a system shutdown.  
if (OpenProcessToken(GetCurrentProcess(), TOKEN_ADJUST_PRIVILEGES | TOKEN_QUERY, &htoken))  
{  
    LUID luid ;  
    LookupPrivilegeValue(NULL, SE_SHUTDOWN_NAME, &luid) ;  
    TOKEN_PRIVILEGES    privs ;  
    privs.Privileges[0].Luid = luid ;  
    privs.PrivilegeCount = 1 ;  
    privs.Privileges[0].Attributes = SE_PRIVILEGE_ENABLED ;  
    AdjustTokenPrivileges(htoken, FALSE, &privs, 0, (PTOKEN_PRIVILEGES) NULL, 0) ;  
}   
  
//Use InitiateSystemShutdownEx to avoid unexpected restart message box  
try  
{              
    if ( (ov.dwMajorVersion > 5) || ( (ov.dwMajorVersion == 5) && (ov.dwMinorVersion  > 0) ))  
    {  
        bExitWindows = InitiateSystemShutdownEx(0, _T(""), 0, TRUE, TRUE, REASON_PLANNED_FLAG);  
    }  
    else  
    {  
#pragma prefast(suppress:380,"ignore warning about legacy api")  
        bExitWindows = InitiateSystemShutdown(0, _T(""), 0, TRUE, TRUE);  
    }  
}  
catch(...)  
{  
    //advapi32.dll call not available! Will not restart!  
}  
  
```  
  
### <a name="resetting-the-start-path-of-msi"></a>Resetování počáteční cestu MSI  
 Před restartováním aktuální adresář je umístění instalačního programu, ale po restartování, bude umístění adresáře system32. Instalační program by se obnovit aktuální adresář před každou volání MSI jak ukazuje následující příklad.  
  
```  
CString GetSetupPath()  
{  
    TCHAR file[MAX_PATH];  
    GetModuleFileName(NULL, file, MAX_PATH * sizeof(TCHAR));  
    CString path(file);  
    int fpos = path.ReverseFind('\\');  
    if (fpos != -1)  
    {  
        path = path.Left(fpos + 1);  
    }  
  
    return path;  
}  
  
```  
  
### <a name="running-the-application-msi"></a>Spuštění aplikace Instalační služby MSI  
 Po návratu ERROR_SUCCESS instalační program prostředí sady Visual Studio můžete spustit soubor MSI pro vaši aplikaci. Vzhledem k tomu, že instalační program poskytuje uživatelské rozhraní, spusťte vaší MSI v tichém režimu (**/q**) a s protokolováním (**/L**), jak ukazuje následující příklad.  
  
```cpp  
TCHAR temp[MAX_PATH];  
GetTempPath(MAX_PATH, temp);  
  
CString boutiqueInstallCmd, msi, log;  
CString cmdLine(MAKEINTRESOURCE("msiexec /q /I %s /L*vx %s REBOOT=ReallySuppress"));  
CString name(MAKEINTRESOURCE("PhotoStudioIntShell.msi"));  
log.Format(_T("\"%s%s.log\""), temp, name);  
msi.Format(_T("\"%s%s\""), GetSetupPath(), name);  
boutiqueInstallCmd.Format(cmdLine, msi, log);  
  
//TODO: You can use MSI API to gather and present install progress feedback from your MSI.  
dwResult = ExecCmd(boutiqueInstallCmd, FALSE);  
```  
  
## <a name="see-also"></a>Viz také  
 [Návod: Vytvoření základní aplikace izolovaného prostředí](walkthrough-creating-a-basic-isolated-shell-application.md)