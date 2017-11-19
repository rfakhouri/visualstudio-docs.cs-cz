---
title: "Návod: Vytvoření sady SDK, pomocí C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36ea793b-3832-41a1-b906-69e680ad5e1d
caps.latest.revision: "32"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: bc30e3236f81f558f3794bb459f6da3edbdaa63d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-creating-an-sdk-using-c"></a>Návod: Vytvoření sady SDK, pomocí C++
Tento návod ukazuje, jak vytvořit nativní C++ matematické knihovnu SDK, balíčku sady SDK jako Visual Studio rozšíření (VSIX) a pak ji použít k vytvoření aplikace. Průvodce je rozdělené do těchto kroků:  
  
-   [Chcete-li vytvořit nativní a prostředí Windows Runtime knihoven](../extensibility/walkthrough-creating-an-sdk-using-cpp.md#createClassLibrary)  
  
-   [Vytvoření projektu rozšíření NativeMathVSIX](../extensibility/walkthrough-creating-an-sdk-using-cpp.md#createVSIX)  
  
-   [K vytvoření ukázkové aplikace, která používá knihovnu tříd](../extensibility/walkthrough-creating-an-sdk-using-cpp.md#createSample)  
  
## <a name="prerequisites"></a>Požadavky  
 Chcete-li provést tento postup, je nutné nainstalovat sadu Visual Studio SDK. Další informace najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
##  <a name="createClassLibrary"></a>Chcete-li vytvořit nativní a prostředí Windows Runtime knihoven  
  
1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
2.  V seznamu šablon, rozbalte položku **Visual C++**, **Windows Store**a pak vyberte **knihovny DLL (aplikace pro Windows Store)** šablony. V **název** zadejte `NativeMath`a potom zvolte **OK** tlačítko.  
  
3.  Aktualizujte NativeMath.h tak, aby odpovídala následující kód.  
  
     [!code-cpp[CreatingAnSDKUsingCpp#1](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_1.h)]  
  
4.  Aktualizace NativeMath.cpp tak, aby odpovídaly tento kód:  
  
     [!code-cpp[CreatingAnSDKUsingCpp#2](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_2.cpp)]  
  
5.  V **Průzkumníku řešení**, otevřete místní nabídku pro **řešení 'NativeMath'**a potom zvolte **přidat**, **nový projekt**.  
  
6.  V seznamu šablon, rozbalte položku **Visual C++**a pak vyberte **komponenty prostředí Windows Runtime** šablony. V **název** zadejte `NativeMathWRT`a potom zvolte **OK** tlačítko.  
  
7.  Aktualizace Class1.h tak, aby odpovídaly tento kód:  
  
     [!code-cpp[CreatingAnSDKUsingCpp#3](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_3.h)]  
  
8.  Aktualizace Class1.cpp tak, aby odpovídaly tento kód:  
  
     [!code-cpp[CreatingAnSDKUsingCpp#4](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_4.cpp)]  
  
9. Na řádku nabídek zvolte **sestavení**, **sestavit řešení**.  
  
##  <a name="createVSIX"></a>Vytvoření projektu rozšíření NativeMathVSIX  
  
1.  V **Průzkumníku řešení**, otevřete místní nabídku pro **řešení 'NativeMath'**a potom zvolte **přidat**, **nový projekt**.  
  
2.  V seznamu šablon, rozbalte položku **Visual C#**, **rozšiřitelnost**a potom vyberte **balíčku VSIX**. V **název** zadejte **NativeMathVSIX**a potom zvolte **OK** tlačítko.  
  
3.  Jakmile se zobrazí návrháře manifestu VSIX, zavřete ji.  
  
4.  V **Průzkumníku řešení**, otevřete místní nabídku pro **source.extension.vsixmanifest**a potom zvolte **kód zobrazení**.  
  
5.  Použijte následující kód XML nahradit existující soubor XML.  
  
    [!code-xml[CreatingAnSDKUsingCpp#6](../extensibility/codesnippet/XML/walkthrough-creating-an-sdk-using-cpp_6.xml)]

6.  V **Průzkumníku řešení**, otevřete místní nabídku pro **NativeMathVSIX** projektu a potom vyberte **přidat**, **novou položku**.  
  
7.  V seznamu **Visual C# položky**, rozbalte položku **Data**a potom vyberte **souboru XML**. V **název** zadejte `SDKManifest.xml`a potom zvolte **OK** tlačítko.  
  
8.  Pomocí této XML nahraďte obsah souboru:  
  
     [!code-xml[CreatingAnSDKUsingCpp#5](../extensibility/codesnippet/XML/walkthrough-creating-an-sdk-using-cpp_5.xml)]  
  
9. V **Průzkumníku řešení**v **NativeMathVSIX** projektu, vytvořte tato struktura složek:  
  
    ```  
  
    \DesignTime  
          \CommonConfiguration  
                \Neutral  
                      \Include  
          \Debug  
                \x86  
    \Redist  
          \Debug  
                \x86  
    \References  
          \CommonConfiguration  
                \Neutral  
    ```  
  
10. V **Průzkumníku řešení**, otevřete místní nabídku pro **řešení 'NativeMath'**a potom zvolte **otevřete složky v Průzkumníku souborů**.  
  
11. V **Průzkumníka souborů**, zkopírujte \NativeMath\NativeMath.h a potom v **Průzkumníku řešení**v **NativeMathVSIX** projektu, vložte jej v \DesignTime\ Složka CommonConfiguration\Neutral\Include\.  
  
     \Debug\NativeMath\NativeMath.lib zkopírujte a vložte jej do složky \DesignTime\Debug\x86\.  
  
     \Debug\NativeMath\NativeMath.dll zkopírujte a vložte ho ve složce \Redist\Debug\x86\.  
  
     DebugNativeMathWRTNativeMathWRT.dll zkopírujte a vložte ho ve složce RedistDebugx86.  
  
     DebugNativeMathWRTNativeMathWRT.winmd zkopírujte a vložte ho ve složce ReferencesCommonConfigurationNeutral.  
  
     DebugNativeMathWRTNativeMathWRT.pri zkopírujte a vložte ho ve složce ReferencesCommonConfigurationNeutral.  
  
12. Ve složce \DesignTime\Debug\x86\ vytvořte textový soubor s názvem NativeMathSDK.props a potom v ní vložte následující obsah:  
  
    [!code-xml[CreatingAnSDKUsingCpp#7](../extensibility/codesnippet/XML/walkthrough-creating-an-sdk-using-cpp_7.xml)]  
  
13. Na řádku nabídek zvolte **zobrazení**, **ostatní okna**, **vlastnosti – okno** (klávesové: Zvolte klávesy F4).  
  
14. V **Průzkumníku řešení**, vyberte **NativeMathWRT.winmd** souboru. V **vlastnosti** změňte **akce sestavení** vlastnost **obsahu**a poté změňte **zahrnout do VSIX** vlastnost  **Hodnota TRUE,**.  
  
     Tento postup opakujte pro **SimpleMath.pri** souboru.  
  
     Tento postup opakujte pro **NativeMath.Lib** souboru.  
  
     Tento postup opakujte pro **NativeMathSDK.props** souboru.  
  
15. V **Průzkumníku řešení**, vyberte **NativeMath.h** souboru. V **vlastnosti** změňte **zahrnout do VSIX** vlastnost **True**.  
  
     Tento postup opakujte pro **NativeMath.dll** souboru.  
  
     Tento postup opakujte pro **NativeMathWRT.dll** souboru.  
  
     Tento postup opakujte pro **SDKManifest.xml** souboru.  
  
16. Na řádku nabídek zvolte **sestavení**, **sestavit řešení**.  
  
17. V **Průzkumníku řešení**, otevřete místní nabídku pro **NativeMathVSIX** projektu a potom vyberte **otevřete složky v Průzkumníku souborů**.  
  
18. V **Průzkumníka souborů**, přejděte do složky \bin\Debug\ a pak spusťte NativeMathVSIX.vsix zahájíte instalaci.  
  
19. Vyberte **nainstalovat** tlačítko, počkejte na dokončení instalace a potom restartujte Visual Studio.  
  
##  <a name="createSample"></a>K vytvoření ukázkové aplikace, která používá knihovnu tříd  
  
1.  Na řádku nabídek zvolte **soubor**, **nový**, **projektu**.  
  
2.  V seznamu šablon, rozbalte položku **Visual C++**, **Windows Store**a potom vyberte **prázdnou aplikaci**. V **název** zadejte **NativeMathSDKSample**a potom zvolte **OK** tlačítko.  
  
3.  V **Průzkumníku řešení**, otevřete místní nabídku pro **NativeMathSDKSample** projektu a potom vyberte **přidat**, **odkaz**.  
  
4.  Na **společných vlastností**, **Framework a odkazy na** stránka vlastností v seznamu odkazové typy, rozbalte **Windows**a potom vyberte **rozšíření** . V podokně podrobností vyberte **nativní SDK matematické** rozšíření a potom zvolte **přidat nový odkaz** tlačítko.  
  
5.  V **přidat odkaz na** dialogové okno, vyberte **nativní SDK matematické** zaškrtněte políčko a potom vyberte **OK** tlačítko.  
  
6.  Zobrazení vlastností projektu NativeMathSDKSample.  
  
     Vlastnosti, které jste definovali v NativeMathSDK.props byly použity při přidání odkazu. Můžete to ověřit tak, že prověří **adresáře VC ++** vlastnost projektu **vlastnosti konfigurace**.  
  
7.  V **Průzkumníku**, otevřete MainPage.xaml a poté použít k nahrazení jeho obsah následujícím XAML:  
  
     [!code-xml[CreatingAnSDKUsingCppDemoApp#1](../extensibility/codesnippet/Xaml/walkthrough-creating-an-sdk-using-cpp_8.xaml)]  
  
8.  Aktualizace Mainpage.xaml.h tak, aby odpovídaly tento kód:  
  
     [!code-cpp[CreatingAnSDKUsingCppDemoApp#2](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_9.h)]  
  
9. Aktualizace MainPage.xaml.cpp tak, aby odpovídaly tento kód:  
  
     [!code-cpp[CreatingAnSDKUsingCppDemoApp#3](../extensibility/codesnippet/CPP/walkthrough-creating-an-sdk-using-cpp_10.cpp)]  
  
10. Zvolte klávesy F5 a spusťte aplikaci.  
  
11. V aplikaci zadejte jakékoli dvě čísla, vyberte operaci a potom zvolte  **=**  tlačítko.  
  
     Se zobrazí správný výsledek.  
  
 Tento návod vám ukázal, jak vytvořit a použít rozšíření sady SDK pro volání do [!INCLUDE[wrt](../extensibility/includes/wrt_md.md)] knihovny a jinou hodnotu než[!INCLUDE[wrt](../extensibility/includes/wrt_md.md)] knihovny.  
  
## <a name="next-steps"></a>Další kroky  
  
## <a name="see-also"></a>Viz také  
 [Návod: Vytvoření sady SDK, pomocí jazyka C# nebo Visual Basic](../extensibility/walkthrough-creating-an-sdk-using-csharp-or-visual-basic.md)   
 [Vytváření Software Development Kit](../extensibility/creating-a-software-development-kit.md)