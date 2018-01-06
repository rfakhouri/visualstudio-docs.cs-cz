---
title: "Návod: Vytvoření sady SDK, pomocí jazyka C# nebo Visual Basic | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef96a249-5eef-402a-a8d5-d74cb49239bd
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a8b0b8452fb20b9b6da4e8ad58c221010f23c9ed
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-an-sdk-using-c-or-visual-basic"></a>Návod: Vytvoření sady SDK, pomocí jazyka C# nebo Visual Basic
V tomto návodu dozvíte, jak vytvořit jednoduché SDK knihovny Math pomocí Visual C# a pak balíček sady SDK jako Visual Studio rozšíření (VSIX). Budete proveďte následující postupy:  
  
-   [Chcete-li vytvořit komponentu SimpleMath Windows Runtime](../extensibility/walkthrough-creating-an-sdk-using-csharp-or-visual-basic.md#createClassLibrary)  
  
-   [Vytvoření projektu rozšíření SimpleMathVSIX](../extensibility/walkthrough-creating-an-sdk-using-csharp-or-visual-basic.md#createVSIX)  
  
-   [K vytvoření ukázkové aplikace, která používá knihovnu tříd](../extensibility/walkthrough-creating-an-sdk-using-csharp-or-visual-basic.md#createSample)  
  
## <a name="prerequisites"></a>Požadavky  
 Chcete-li provést tento postup, je nutné nainstalovat sadu Visual Studio SDK. Další informace najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
##  <a name="createClassLibrary"></a>Chcete-li vytvořit komponentu SimpleMath Windows Runtime  
  
1.  Na řádku nabídek zvolte **soubor**, **nový**, **nový projekt**.  
  
2.  V seznamu šablon, rozbalte položku **Visual C#** nebo **jazyka Visual Basic**, vyberte **Windows Store** uzel a potom vyberte **komponentyprostředíWindowsRuntime** šablony.  
  
3.  V **název** zadejte **SimpleMath**a potom zvolte **OK** tlačítko.  
  
4.  V **Průzkumníku řešení**, otevřete místní nabídku pro **SimpleMath** uzel projektu a potom zvolte **vlastnosti**.  
  
5.  Přejmenování **Class1.cs** k **Arithmetic.cs** a aktualizovat ji tak, aby odpovídala následující kód:  
  
     [!code-csharp[CreatingAnSDKUsingWinRT#3](../extensibility/codesnippet/CSharp/walkthrough-creating-an-sdk-using-csharp-or-visual-basic_1.cs)]
     [!code-vb[CreatingAnSDKUsingWinRT#3](../extensibility/codesnippet/VisualBasic/walkthrough-creating-an-sdk-using-csharp-or-visual-basic_1.vb)]  
  
6.  V **Průzkumníku řešení**, otevřete místní nabídku pro **řešení 'SimpleMath'** uzel a potom zvolte **nástroje Configuration Manager**.  
  
     **Nástroje Configuration Manager** otevře se dialogové okno.  
  
7.  V **aktivní konfigurace řešení** vyberte **verze**.  
  
8.  V **konfigurace** sloupce, ověřte, že **SimpleMath** řádek je nastaven na **verze**a potom zvolte **Zavřít** tlačítko tak, aby přijímal změníte.  
  
    > [!IMPORTANT]
    >  Sada SDK pro komponentu SimpleMath obsahuje pouze jednu konfiguraci. Tato konfigurace musí být sestavení pro vydání, nebo aplikace, které používají součást nebude předat certifikační pro[!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)].  
  
9. V **Průzkumníku řešení**, otevřete místní nabídku pro **SimpleMath** uzel projektu a potom zvolte **sestavení**.  
  
##  <a name="createVSIX"></a>Vytvoření projektu rozšíření SimpleMathVSIX  
  
1.  V místní nabídce pro **řešení 'SimpleMath'** uzlu, zvolte **přidat**, **nový projekt**.  
  
2.  V seznamu šablon, rozbalte položku **Visual C#** nebo **jazyka Visual Basic**, vyberte **rozšiřitelnost** uzel a potom zvolte **projektu VSIX** Šablona.  
  
3.  V **název** zadejte **SimpleMathVSIX**a potom zvolte **OK** tlačítko.  
  
4.  V **Průzkumníku řešení**, vyberte **source.extension.vsixmanifest** položky.  
  
5.  Na řádku nabídek zvolte **zobrazení**, **kód**.  
  
6.  Následující kód XML nahraďte existující soubor XML:  
  
     [!code-xml[CreatingAnSDKUsingWinRT#1](../extensibility/codesnippet/XML/walkthrough-creating-an-sdk-using-csharp-or-visual-basic_2.xml)]
  
7.  V **Průzkumníku řešení**, vyberte **SimpleMathVSIX** projektu.  
  
8.  Na řádku nabídek zvolte **projektu**, **přidat novou položku**.  
  
9. V seznamu **společné položky**, rozbalte položku **Data**a potom zvolte **souboru XML**.  
  
10. V **název** zadejte `SDKManifest.xml`a potom zvolte **přidat** tlačítko.  
  
11. V **Průzkumníku řešení**, otevřete místní nabídku pro `SDKManifest.xml`, zvolte **vlastnosti**a poté změňte hodnotu **zahrnout do VSIX** vlastnost **True**.  
  
12. Nahraďte obsah souboru následující kód XML:  

    **C#**
    ```xml
    <FileList
      DisplayName="WinRT Math Library (CS)"
      MinVSVersion="11.0"
      TargetFramework=".NETCore,version=v4.5"
      AppliesTo="WindowsAppContainer"
      SupportsMultipleVersions="Error"
      MoreInfo="http://www.msdn.microsoft.com/">
    </FileList>
    ```

    **Visual Basic**
    ```xml
    <FileList
      DisplayName="WinRT Math Library (VB)"
      MinVSVersion="11.0"
      TargetFramework=".NETCore,version=v4.5"
      AppliesTo="WindowsAppContainer"
      SupportsMultipleVersions="Error"
      MoreInfo="http://www.msdn.microsoft.com/">
    </FileList>
    ```  
  
13. V **Průzkumníku řešení**, otevřete místní nabídku pro **SimpleMathVSIX** projektu, zvolte **přidat**a potom zvolte **novou složku**.  
  
14. Přejmenujte složku na `references`.  
  
15. Otevřete místní nabídku pro **odkazy** složky, vyberte **přidat**a potom zvolte **novou složku**.  
  
16. Přejmenujte podsložce k `commonconfiguration`, vytvořit podsložky v něm a název podsložky `neutral`.  
  
17. Opakujte předchozí čtyři kroky, tentokrát přejmenování složce první `redist`.  
  
     Projekt teď obsahuje následující strukturu složek:  
  
    ```
    references\commonconfiguration\neutral  
    redist\commonconfiguration\neutral  
    ```  
  
18. V **Průzkumníku řešení**, otevřete místní nabídku pro **SimpleMath** projektu a potom vyberte **otevřete složky v Průzkumníku souborů**.  
  
19. V **Průzkumníka souborů**, přejděte do složky bin\Release, otevřete místní nabídku pro soubor SimpleMath.winmd a zvolte **kopie**.  
  
20. V **Průzkumníku řešení**, vložte jej do složky references\commonconfiguration\neutral v **SimpleMathVSIX** projektu.  
  
21. Opakujte předchozí krok, vkládání SimpleMath.pri soubor do složky redist\commonconfiguration\neutral v **SimpleMathVSIX** projektu.  
  
22. V **Průzkumníku řešení**, zvolte **SimpleMath.winmd**.  
  
23. Na řádku nabídek zvolte **zobrazení**, **vlastnosti** (klávesové: Zvolte klávesy F4).  
  
24. V **vlastnosti** změňte **akce sestavení** vlastnost **obsahu**a poté změňte **zahrnout do VSIX** vlastnost  **Hodnota TRUE,**.  
  
25. V **Průzkumníku řešení**, tento postup opakujte pro **SimpleMath.pri**.  
  
26. V **Průzkumníku řešení**, vyberte **SimpleMathVSIX** projektu.  
  
27. Na řádku nabídek zvolte **sestavení**, **sestavení SimpleMathVSIX**.  
  
28. V **Průzkumníku řešení**, otevřete místní nabídku pro **SimpleMathVSIX** projektu a potom vyberte **otevřete složky v Průzkumníku souborů**.  
  
29. V **Průzkumníka souborů**, přejděte do složky \bin\Release a pak spusťte SimpleMathVSIX.vsix k její instalaci.  
  
30. Vyberte **nainstalovat** tlačítko, počkejte na dokončení instalace a potom restartujte Visual Studio.  
  
##  <a name="createSample"></a>K vytvoření ukázkové aplikace, která používá knihovnu tříd  
  
1.  Na řádku nabídek zvolte **soubor**, **nový**, **nový projekt**.  
  
2.  V seznamu šablon, rozbalte položku **Visual C#** nebo **jazyka Visual Basic**a potom zvolte **Windows Store** uzlu.  
  
3.  Vyberte **prázdnou aplikaci** šablony, název projektu **ArithmeticUI**a potom zvolte **OK** tlačítko.  
  
4.  V **Průzkumníku řešení**, otevřete místní nabídku pro **ArithmeticUI** projektu a potom vyberte **přidat**, **odkaz**.  
  
5.  V seznamu odkazové typy rozbalte **Windows**a potom zvolte **rozšíření**.  
  
6.  V podokně podrobností vyberte **jednoduché matematické SDK** rozšíření.  
  
     Zobrazí se další informace o vaší SDK. Můžete **více informací** odkazu k otevření http://www.msdn.microsoft.com, jako jste zadali v souboru SDKManifest.xml dříve v tomto návodu.  
  
7.  V **správce odkazů** dialogové okno, vyberte **jednoduché matematické SDK** zaškrtněte políčko a potom vyberte **OK** tlačítko.  
  
8.  Na řádku nabídek zvolte **zobrazení**, **Prohlížeč objektů**.  
  
9. V **Procházet** vyberte **jednoduché matematické**.  
  
     Nyní můžete zkoumat, co je v sadě SDK.  
  
10. V **Průzkumníku**, otevřete MainPage.xaml a nahraďte jeho obsah následujícím XAML:  

    **C#**
    ```xml
    <Page
        x:Class="WinRTMathTestCS.MainPage"
        IsTabStop="False"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:WinRTMathTestCS"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        mc:Ignorable="d">

        <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">
            <TextBox x:Name="_firstNumber" HorizontalAlignment="Left" Margin="414,370,0,0" TextWrapping="Wrap" Text="First Number" VerticalAlignment="Top" Height="32" Width="135" TextAlignment="Center"/>
            <TextBox x:Name="_secondNumber" HorizontalAlignment="Left" Margin="613,370,0,0" TextWrapping="Wrap" Text="Second Number" VerticalAlignment="Top" Height="32" Width="135" TextAlignment="Center"/>
            <Button Content="+" HorizontalAlignment="Left" Margin="557,301,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="-" HorizontalAlignment="Left" Margin="557,345,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="*" HorizontalAlignment="Left" Margin="557,389,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="/" HorizontalAlignment="Left" Margin="557,433,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="=" HorizontalAlignment="Left" Margin="755,367,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnResultsClick"/>
            <TextBox x:Name="_result" HorizontalAlignment="Left" Margin="809,370,0,0" TextWrapping="Wrap" Text="Result" VerticalAlignment="Top" Height="32" Width="163" TextAlignment="Center" IsReadOnly="True"/>
        </Grid>
    </Page>
    ```
    
    **Visual Basic**
    ```xml
    <Page
        x:Class="WinRTMathTest.MainPage"
        IsTabStop="False"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:local="using:WinRTMathTest"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        mc:Ignorable="d">

        <Grid Background="{StaticResource ApplicationPageBackgroundThemeBrush}">
            <TextBox x:Name="_firstNumber" HorizontalAlignment="Left" Margin="414,370,0,0" TextWrapping="Wrap" Text="First Number" VerticalAlignment="Top" Height="32" Width="135" TextAlignment="Center"/>
            <TextBox x:Name="_secondNumber" HorizontalAlignment="Left" Margin="613,370,0,0" TextWrapping="Wrap" Text="Second Number" VerticalAlignment="Top" Height="32" Width="135" TextAlignment="Center"/>
            <Button Content="+" HorizontalAlignment="Left" Margin="557,301,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="-" HorizontalAlignment="Left" Margin="557,345,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="*" HorizontalAlignment="Left" Margin="557,389,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="/" HorizontalAlignment="Left" Margin="557,433,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnOperatorClick"/>
            <Button Content="=" HorizontalAlignment="Left" Margin="755,367,0,0" VerticalAlignment="Top" Height="39" Width="49" Click="OnResultsClick"/>
            <TextBox x:Name="_result" HorizontalAlignment="Left" Margin="809,370,0,0" TextWrapping="Wrap" Text="Result" VerticalAlignment="Top" Height="32" Width="163" TextAlignment="Center" IsReadOnly="True"/>
        </Grid>
    </Page>
    ```
  
11. Aktualizace MainPage.xaml.cs tak, aby odpovídala následující kód:  
  
     [!code-csharp[CreatingAnSDKUsingWinRTDemoApp#2](../extensibility/codesnippet/CSharp/walkthrough-creating-an-sdk-using-csharp-or-visual-basic_5.cs)]
     [!code-vb[CreatingAnSDKUsingWinRTDemoApp#2](../extensibility/codesnippet/VisualBasic/walkthrough-creating-an-sdk-using-csharp-or-visual-basic_5.vb)]  
  
12. Zvolte klávesy F5 a spusťte aplikaci.  
  
13. V aplikaci zadejte jakékoli dvě čísla, zvolte operace a pak  **=**  tlačítko.  
  
     Se zobrazí správný výsledek.  
  
 Úspěšně jste vytvořili a použít rozšíření sady SDK.  
  
## <a name="see-also"></a>Viz také  
 [Návod: Vytvoření sady SDK, pomocí C++](../extensibility/walkthrough-creating-an-sdk-using-cpp.md)   
 [Návod: Vytvoření sady SDK, pomocí jazyka JavaScript](http://msdn.microsoft.com/en-us/6195ff56-4a27-45fc-bd29-4b0451225f4b)   
 [Vytvoření sady SDK (Software Development Kit)](../extensibility/creating-a-software-development-kit.md)