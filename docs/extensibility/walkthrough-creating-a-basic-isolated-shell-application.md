---
redirect_url: shell/walkthrough-creating-a-basic-isolated-shell-application
title: "Návod: Vytvoření základního izolované aplikace prostředí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio shell, walkthroughs
- Shell [Visual Studio], walkthroughs
- walkthroughs [Visual Studio], isolated shell-based application
ms.assetid: 8b12e223-aae3-4c23-813d-ede1125f5f69
caps.latest.revision: "54"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c4df0d9f772d92ac7f1f106b9befc0a8a2f89a22
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-creating-a-basic-isolated-shell-application"></a>Návod: Vytvoření základní izolované prostředí aplikace
Tento návod ukazuje, jak vytvořit řešení s izolované prostředí, přizpůsobit panel nástrojů nápovědy o a vytvořte instalační program, který nainstaluje izolované prostředí.  
  
## <a name="prerequisites"></a>Požadavky  
 Chcete-li provést tento postup, je nutné nainstalovat sadu Visual Studio SDK. Další informace najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md). Pokud chcete nasadit izolované prostředí, musíte taky použít redistribuovatelného balíčku Visual Studio Shell (Izolovaná).  
  
## <a name="creating-an-isolated-shell-solution"></a>Vytváření řešení s izolované prostředí  
 V této části ukazuje, jak používat Visual Studio Shell izolované šablona projektu pro vytvoření řešení izolované prostředí. Řešení obsahuje následující projekty:  
  
-   *Název řešení SolutionName*. AboutBoxPackage projektu, který umožňuje přizpůsobení vzhledu nápovědy/o pole.  
  
-   ShellExtensionsVSIX projektu, který obsahuje soubor source.extension.vsixmanifest, který definuje různé součásti aplikace izolované prostředí.  
  
-   *Název řešení SolutionName* projektu, který vytvoří spustitelný soubor, který volá aplikaci izolované prostředí. Tento projekt obsahuje složce vlastního nastavení prostředí, která umožňuje přizpůsobit vzhled a chování aplikace izolované prostředí.  
  
-   *Název řešení SolutionName* uživatelského rozhraní projektu, který vytváří satelitní sestavení, které definuje lokalizovatelný řetězce a příkazy nabídky aktivní.  
  
#### <a name="to-create-a-basic-isolated-shell-solution"></a>Chcete-li vytvořit řešení základní izolované prostředí  
  
1.  Otevřete Visual Studio a vytvořte nový projekt.  
  
2.  V **nový projekt** okně rozbalte **jiné typy projektů** a potom **rozšiřitelnost**. Vyberte **Visual Studio Shell izolované** šablona projektu.  
  
3.  Název projektu `MyVSShellStub` a zadejte umístění. Ujistěte se, že **vytvořit adresář pro řešení** je zaškrtnuté políčko a potom klikněte na **OK**.  
  
     Nové řešení se zobrazí v **Průzkumníku řešení**.  
  
4.  Sestavte řešení a spusťte ladění aplikace izolované prostředí.  
  
     Zobrazí se prostředí sady Visual Studio izolované. Načte záhlaví **MyVSShellStub**. Ikonu záhlaví se generují z \MyVSShellStub\Resource Files\ApplicationIcon.ico.  
  
## <a name="customizing-the-application-name-and-icon"></a>Přizpůsobení ikona a název aplikace  
 Můžete pro vytvoření firemní identity aplikace pomocí názvu vaší společnosti a jeho loga v záhlaví. Následující kroky ukazují, jak změnit název a ikona, která se zobrazí v záhlaví vlastní aplikace změnou definiční soubor balíčku, MyVSShellStub.Application.pkgdef.  
  
#### <a name="to-customize-the-application-name-and-icon"></a>Chcete-li přizpůsobit název aplikace a ikona  
  
1.  V projektu MyVSShellStub otevřete \Shell Customization\MyVSShellStub.Application.pkgdef.  
  
2.  Změna `AppName` hodnotu elementu **"AppName" = "Editor Hudba Fabrikam"**  
  
3.  Chcete-li změnit ikona aplikace, zkopírujte do adresáře \MyVSShellStub\MyVSShellStub\MyVSShellStub\ vlastní ikonu. Přejmenujte existující soubor ApplicationIcon.ico ApplicationIcon1.ico. Přejmenujte ApplicationIcon.ico nový soubor.  
  
4.  Sestavte řešení a spuštění ladění. Izolované prostředí IDE se zobrazí. Záhlaví má váš nový Ikona vedle slova **Fabrikam Hudba Editor**.  
  
## <a name="customizing-the-default-web-browser-home-page"></a>Přizpůsobení výchozí webový prohlížeč domovské stránky  
 V této části ukazuje, jak změnit výchozí domovské stránce **webový prohlížeč** okno změnou definiční soubor balíčku.  
  
#### <a name="to-customize-the-default-web-browser-home-page"></a>Chcete-li přizpůsobit výchozí webový prohlížeč domovskou stránku  
  
1.  V souboru MyVSShellStub.Application.pkgdef změnit `DefaultHomePage` element hodnotu "http://www.microsoft.com".  
  
2.  Znovu sestavte projekt MyVSShellStub.  
  
3.  Sestavte řešení a spuštění ladění.  
  
4.  V **zobrazení nebo ostatní okna**, klikněte na tlačítko **webový prohlížeč**. **Webový prohlížeč** okně se zobrazí na domovskou stránku Microsoft Corporation.  
  
## <a name="removing-the-print-command"></a>Odebrání příkaz pro tisk  
 Soubor .vsct v projektu izolované prostředí uživatelského rozhraní obsahuje sadu deklarací ve tvaru `<Define name=No_` *Element*`>`, kde *Element* je jedním z nabídky standardní sady Visual Studio a příkazy.  
  
 Pokud je prohlášení uncommented, že nabídky nebo příkazu je vyloučen z izolované prostředí. Naopak pokud je označené jako komentář deklaraci, nabídky nebo příkazu je součástí izolované prostředí.  
  
 V následujících krocích Odkomentujte tiskové příkaz v souboru .vsct.  
  
#### <a name="to-remove-the-print-command"></a>Chcete-li odebrat příkaz pro tisk  
  
1.  Ověřte, zda **tiskových** příkazu se zobrazí na **souboru** nabídky v izolované prostředí aplikace.  
  
2.  V projektu MyVSShellStubUI otevřete \Resource Files\MyVSShellStubUI.vsct pro úpravy.  
  
3.  Zrušením komentáře u tohoto řádku:  
  
    ```  
    <!-- <Define name="No_PrintChildrenCommand"/> -->  
    ```  
  
4.  Odebere příkaz pro tisk.  
  
5.  Spusťte ladění aplikace izolované prostředí. Ověřte, zda **souboru / Print** příkaz je pryč.  
  
## <a name="removing-features-from-the-isolated-shell"></a>Izolované prostředí odebráním funkcí  
 Můžete odebrat některé balíčky, které jsou načteny pomocí sady Visual Studio úpravou souboru .pkgundef, pokud nechcete tyto funkce v aplikaci vlastní izolované prostředí. Zadejte balíček v jednom z podklíčů klíče registru \Packages $RootKey$.  
  
> [!NOTE]
>  Funkce identifikátory GUID Visual Studio, najdete v tématu [identifikátory GUID nástroje Visual Studio funkce balíčků](../extensibility/package-guids-of-visual-studio-features.md).  
  
 Následující postup ukazuje, jak odebrat XML editor z izolované prostředí.  
  
#### <a name="to-remove-the-xml-editor"></a>Chcete-li odebrat editor souborů XML  
  
1.  Otevřete soubor MyVSShellStub.pkgundef ve složce vlastního nastavení prostředí MyVSShellStub projektu.  
  
2.  Zrušte komentář u následujícího řádku:  
  
     [$RootKey$ \Packages\\{87569308-4813-40a0-9cd0-d7a30838ca3f}]  
  
3.  Znovu sestavte řešení a spuštění ladění izolované prostředí. Otevřete soubor XML, například \MyVSShellStub\MyVSShellStub\MyVSShellStubUI\MyVSShellStubUI.vsct. Ověřte, že nejsou obarvené klíčová slova XML v souboru a že zadáním příkazu "<" na řádek nelze vyvolat popisy tlačítek XML.  
  
## <a name="customizing-the-helpabout-box"></a>Přizpůsobení Nápověda/o pole  
 Můžete přizpůsobit v nápovědě nebo o pole, který je vytvořen jako součást šablona projektu izolované prostředí.  
  
#### <a name="to-customize-the-company-name"></a>Chcete-li přizpůsobit název společnosti  
  
1.  Název společnosti, informace o autorských právech, verze produktu a popis produktu se nacházejí v projektu MyVSShellStub.AboutBoxPackage v souboru \Properties\AssemblyInfo.cs. Umožňuje otevřete tento soubor.  
  
2.  Změna `AssemblyCompany` hodnotu **Fabrikam**, `AssemblyProduct` a `AssemblyTitle` hodnoty k **Fabrikam Hudba Editor**a `AssemblyCopyright` hodnotu **Copyright © Společnost Fabrikam 2015**:  
  
    ```  
    [assembly: AssemblyTitle("Fabrikam Music Editor")]  
    [assembly: AssemblyDescription("")]  
    [assembly: AssemblyConfiguration("")]  
    [assembly: AssemblyCompany("Fabrikam")]  
    [assembly: AssemblyProduct("Fabrikam Music Editor")]  
    [assembly: AssemblyCopyright("Copyright © Fabrikam 2015")] [assembly: AssemblyCompany("Fabrikam")]  
    [assembly: AssemblyProduct("Fabrikam Music Editor ")]  
    [assembly: AssemblyCopyright("Copyright © Fabrikam 2015")]  
    ```  
  
3.  Chcete-li přidat popis produktu, změňte `AssemblyDescription` hodnotu **popis Fabrikam Hudba editoru.**:  
  
    ```  
    [assembly: AssemblyDescription("The description of Fabrikam Music editor.")]  
    ```  
  
4.  Spuštění ladění a otevřete v izolované prostředí aplikace **Nápověda / o** pole. Měli byste vidět změněné řetězce. Nadpis nápovědy/o pole je stejný jako `AssemblyTitle` hodnota v AssemblyInfo.cs.  
  
5.  Vlastnosti **Nápověda/o** pole se nacházejí v souboru MyVSShellStub.AboutBoxPackage\AboutBox.xaml. Chcete-li změnit šířku nápovědy/o pole, přejděte na `AboutDialogStyle` blokovat a nastavte `Width` vlastnost na 200:  
  
    ```  
    <Style x:Key="AboutDialogStyle" TargetType="Window">  
        <Setter Property="Height" Value="Auto" />  
        <Setter Property="Width" Value="200" />  
        <Setter Property="ShowInTaskbar" Value="False" />  
        <Setter Property="ResizeMode" Value="NoResize" />  
        <Setter Property="WindowStyle" Value="SingleBorderWindow" />  
        <Setter Property="SizeToContent" Value="Height" />  
    </Style>  
    ```  
  
6.  Znovu sestavte řešení a spuštění ladění izolované prostředí. Nápověda/o pole by měl být přibližně čtvereček.  
  
## <a name="before-you-deploy-the-isolated-shell-application"></a>Před nasazením aplikace izolované prostředí  
 Izolované prostředí aplikace lze nainstalovat na libovolném počítači, který má redistribuovatelného balíčku Visual Studio Shell (Izolovaná). Další informace o redistribuovatelného balíčku najdete v tématu [Visual Studio Extensibility stáhne](http://go.microsoft.com/fwlink/?LinkID=119298) webu.  
  
## <a name="deploying-the-isolated-shell-application"></a>Nasazení aplikace izolované prostředí  
 Nasazení aplikace izolované prostředí k cílovému počítači tak, že vytvoříte projekt instalace. Je nutné zadat tyto věci:  
  
-   Rozložení složek a souborů na cílovém počítači.  
  
-   Spuštění podmínky, které zaručit, že rozhraní .NET Framework a sady Visual Studio shell runtime jsou nainstalované v cílovém počítači.  
  
 V následujícím postupu musíte nainstalovat InstallShield Limited Edition na váš počítač.  
  
#### <a name="to-create-the-setup-project"></a>Chcete-li vytvořit projekt instalace  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel řešení a pak klikněte na tlačítko **přidat nový projekt**.  
  
2.  V **nový projekt** dialogové okno, rozbalte seznam **jiné typy projektů** a pak vyberte **instalace a nasazení**. Vyberte šablonu InstallShield. Název nového projektu `MySetup` a pak klikněte na **OK**.  
  
3.  Pokud InstallShield Limited Edition je již nainstalován, pokračujte k dalšímu kroku.  
  
     Pokud ještě není nainstalovaný InstallShield Limited Edition, zobrazí se stránka Stažení InstallShield. Postupujte podle pokynů ke stažení a instalaci produktu, výběr verzi InstallShield, který je kompatibilní s vaší verzí sady Visual Studio. Musíte se rozhodnout, jestli se pro registraci vaší instalace InstallShield nebo ho používat jako zkušební verzi. Po dokončení instalace, musíte restartovat Visual Studio.  
  
    > [!IMPORTANT]
    >  Před vytvořením projektu InstallShield, je nutné spustit Visual Studio jako správce. Pokud to neuděláte, bude dojde k chybě při sestavování projektu.  
  
 Další kroky ukazují, jak nakonfigurovat nastavení projektu.  
  
> [!IMPORTANT]
>  Ujistěte se, že, který jste vytvořili konfigurace verze projektu izolované prostředí alespoň jednou před konfigurací projektu instalace.  
  
#### <a name="to-configure-the-setup-project"></a>Ke konfiguraci projektu instalace  
  
1.  V **Průzkumníku řešení**v části **MySetup** projektu, zvolte **projektu pomocníka**. V řadě dolní **projektu pomocníka** okně zvolte **informace o aplikaci**. Zadejte **Fabrikam** jako název vaší společnosti a **Fabrikam Hudba Editor** jako název aplikace. Zvolte tlačítko Vpřed v pravém dolním rohu **projektu pomocníka**.  
  
2.  Vyberte **Ano** pod **nevyžaduje vaše aplikace k instalaci na počítači veškerý software?** a pak vyberte **úplné balíček rozhraní Microsoft .NET Framework 4.5**.  
  
3.  Vyberte **soubory aplikace** tlačítko v dolní části okna a ujistěte se, že **Fabrikam Hudba Editor** je vybrána složka.  
  
4.  Vyberte **přidat soubory** tlačítko. V **přidat soubory** dialogové okno pole, přidejte následující soubory z **MyVSShellStub\Release** složky:  
  
    1.  MyVSShellStub.exe.config  
  
    2.  DebuggerProxy.dll  
  
    3.  DebuggerProxy.dll.manifest  
  
    4.  MyVSShellStub.pkgdef  
  
    5.  MyVSShellStub.pkgundef  
  
    6.  MyVSShellStub.winprf  
  
    7.  Splash.bmp  
  
5.  Klikněte na tlačítko **přidejte výstupy projektu** tlačítko a přidejte **MyVSShellStub/primární výstup**. Click **OK**.  
  
6.  V levém podokně v části **cílový počítač**, klikněte pravým tlačítkem myši **Fabrikam Hudba Editor [INSTALLDIR]** uzlu a přidejte **novou složku** s názvem **rozšíření** .  
  
7.  Klikněte pravým tlačítkem myši **rozšíření** uzlu v levém podokně a přidejte novou složku s názvem **aplikace**.  
  
8.  Vyberte **aplikace** složky a klikněte na tlačítko **přidejte výstupy projektu** tlačítko a potom vyberte primární výstup z MyVSShellStub.AboutBoxPackage projektu.  
  
9. Klikněte **přidat soubory** tlačítko a ve složce \MyVSShellStub\Release\Extensions\Application\ přidejte následující soubory:  
  
    -   MyVSShellStub.AboutBoxPackage.pkgdef  
  
    -   MyVSShellStub.Application.pkgdef  
  
10. Klikněte pravým tlačítkem myši **Fabrikam Hudba Editor [INSTALLDIR]** uzlu v levém podokně a přidejte novou složku s názvem **1033**.  
  
11. Vyberte složku, 1033 a klikněte **přidejte výstupy projektu** tlačítko a vyberte primární výstup z MyVSShellStubUI projektu.  
  
12. Přesunout do **aplikačních zkratek** okno.  
  
13. Klikněte na tlačítko **nový** k vytvoření zástupce a vyberte **[ProgramFilesFolder] \Fabrikam\Fabrikam Music Editor\MyVSShellStub.Primary Output**.  
  
14. Přesunout do **instalace rozhovoru** podokně.  
  
15. Nastavit všechny položky na **ne**.  
  
16. V **Průzkumníku řešení**, otevřete v projektu MySetup **definovat nastavení požadavků a akce \ požadavky**. **Požadavky** otevře se okno.  
  
17. Klikněte pravým tlačítkem na **požadavky na systém softwaru** a vyberte **vytvořit novou podmínku spuštění**. **Průvodce vyhledávání systému** se zobrazí.  
  
18. V **co chcete najít?** podokně vyberte **položky registru** v rozevíracím seznamu a klikněte na **Další**.  
  
19. V **jak chcete vyhledejte ho?** podokně, vyberte **HKEY_LOCAL_MACHINE** jako kořenový klíč registru. Zadejte **SOFTWARE\Wow6432Node\Microsoft\DevDiv\vs\Servicing\14.0\isoshell** pro 64bitové systémy nebo **SOFTWARE\Microsoft\DevDiv\vs\Servicing\14.0\isoshell** pro 32bitové systémy a zadejte  **Nainstalujte** jako hodnotu registru. Klikněte na tlačítko **Další**.  
  
20. V **co chcete použít hodnotu?** podokně zadejte **vyžaduje Visual Studio 2015 izolované prostředí Redistributable k instalaci tohoto produktu.** Zobrazovaný text a klikněte na **Dokončit**.  
  
21. Znovu sestavte řešení izolované prostředí a vytvořte tak projekt Instalační program.  
  
     Soubor setup.exe najdete v následující složce:  
  
     \MyVSShellStub\MySetup\MySetup\Express\SingleImage\DiskImages\DISK1  
  
## <a name="testing-the-installation-program"></a>Testování instalačního programu  
 Chcete-li otestovat nastavení, zkopírujte soubor setup.exe do jiného počítače a spuštění spustitelného souboru Instalační program. Nyní byste měli mít ke spuštění aplikace izolované prostředí.