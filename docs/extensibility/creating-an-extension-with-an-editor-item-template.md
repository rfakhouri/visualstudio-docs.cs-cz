---
title: "Vytváření rozšíření pomocí šablony položky Editor | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], new - extensions
ms.assetid: fa3b993b-ab95-47fa-a38b-b788f3a5b2d8
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: fb66dfffaf8fa8339ce9060c912dc358fb454a7e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="creating-an-extension-with-an-editor-item-template"></a>Vytváření rozšíření pomocí šablony položky editoru
Můžete vytvořit šablony položek, které jsou zahrnuté v sadě Visual Studio SDK k vytvoření základní editor rozšíření, které přidat třídění, vylepšení a okraje do editoru. Šablony položek editor jsou k dispozici pro projekty Visual C# nebo Visual Basic VSIX.  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-classifier-extension"></a>Vytváření rozšíření pro třídění  
 Šablony položky Editor třídění vytvoří klasifikátoru editor, který barvy odpovídající text (v takovém případě vše) v jakékoli textového souboru.  
  
1.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** nebo **jazyka Visual Basic** a pak klikněte na **rozšiřitelnost**. V **šablony** podokně, vyberte **projektu VSIX**. V **název** zadejte `TestClassifier`. Click **OK**.  
  
2.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat / novou položku**. Přejděte k Visual C# **rozšiřitelnost** uzel a vyberte možnost **Editor třídění**. Ponechte výchozí název souboru (EditorClassifier1.cs).  
  
3.  Existují tři soubory kódu, následujícím způsobem:  
  
    -   Obsahuje EditorClassifier1.cs `EditorClassifier1` třídy.  
  
    -   Obsahuje EditorClassifier1ClassificationDefinition.cs `OEditorClassifier1ClassificationDefinition` třídy.  
  
    -   Obsahuje EditorClassifier1Format.cs `EditorClassifier1Format` třídy.  
  
    -   Obsahuje EditorClassifier1Provider.cs `EditorClassifier1Provider` třídy.  
  
4.  Sestavte projekt a spusťte ladění. Zobrazí se experimentální instanci sady Visual Studio.  
  
     Pokud otevřete textový soubor, veškerého textu jsou podtržené proti fialové pozadí.  
  
## <a name="creating-a-text-relative-adornment-extension"></a>Vytváření rozšíření pro Text relativní dalších úprav  
 Šablona dalších úprav editoru textu vytvoří text relativní dalších úprav, která upraví všechny instance textu znaku "a" pomocí pole, který má červeného obrysu a modré pozadí. Je relativní textové protože pole vždy překryvy "a" znaky, i když jsou přesunout nebo naformátována.  
  
1.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** nebo **jazyka Visual Basic** a pak klikněte na **rozšiřitelnost**. V **šablony** podokně, vyberte **projektu VSIX**. V **název** zadejte `TestAdornment`. Click **OK**.  
  
2.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat / novou položku**. Přejděte k Visual C# **rozšiřitelnost** uzel a vyberte možnost **dalších úprav editoru textu**. Ponechte výchozí název souboru (TextAdornment1.cs/vb).  
  
3.  Existují dva soubory kódu, následujícím způsobem:  
  
    -   Obsahuje TextAdornment1.cs `TextAdornment1` třídy.  
  
    -   obsahuje extAdornment1TextViewCreationListener.cs `TextAdornment1TextViewCreationListener` třídy.  
  
4.  Sestavte projekt a spusťte ladění. Zobrazí se experimentální instanci. Pokud otevřete textový soubor, jsou uvedeny všechny 'a' znaky v textu v červená modrá pozadí.  
  
## <a name="creating-a-viewport-relative-adornment-extension"></a>Vytváření rozšíření pro relativní k zobrazení dalších úprav  
 Editor zobrazení dalších úprav šablona vytvoří relativní k zobrazení dalších úprav, který přidá fialové pole, která má red osnovy a pravém horním rohu zobrazení.  
  
> [!NOTE]
>  *Zobrazení* je oblast textového zobrazení, která je aktuálně zobrazený.  
  
#### <a name="to-create-a-viewport-adornment-extension-by-using-the-editor-viewport-adornment-template"></a>Chcete-li vytvořit příponu dalších úprav zobrazení pomocí dalších úprav editoru zobrazení šablony  
  
1.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** nebo **jazyka Visual Basic** a pak klikněte na **rozšiřitelnost**. V **šablony** podokně, vyberte **projektu VSIX**. V **název** zadejte `ViewportAdornment`. Click **OK**.  
  
2.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat / novou položku**. Přejděte k Visual C# **rozšiřitelnost** uzel a vyberte možnost **dalších úprav editoru zobrazení**. Ponechte výchozí název souboru (ViewportAdornment1.cs/vb).  
  
3.  Existují dva soubory kódu, následujícím způsobem:  
  
    -   Obsahuje ViewportAdornment1.cs `ViewportAdornment1` třídy.  
  
    -   Obsahuje ViewportAdornment1TextViewCreationListener.cs `ViewportAdornment1TextViewCreationListener` – třída  
  
4.  Sestavte projekt a spusťte ladění. Zobrazí se experimentální instanci. Pokud vytvoříte nový textový soubor, fialové pole, který má červeného obrysu se zobrazí v pravém horním rohu zobrazení.  
  
## <a name="creating-a-margin-extension"></a>Vytváření rozšíření pro rozpětí  
 Okraj editoru šablona vytváří zelená okraj, který se zobrazí spolu s slova "Hello, world!" pod vodorovný posuvník.  
  
#### <a name="to-create-a-margin-extension-by-using-the-editor-margin-template"></a>Chcete-li vytvořit okraj rozšíření pomocí šablony okraj editoru  
  
1.  V **nový projekt** dialogové okno, rozbalte seznam **Visual C#** nebo **jazyka Visual Basic** a pak klikněte na **rozšiřitelnost**. V **šablony** podokně, vyberte **projektu VSIX**. V **název** zadejte `MarginExtension`. Click **OK**.  
  
2.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **přidat / novou položku**. Přejděte k Visual C# **rozšiřitelnost** uzel a vyberte možnost **dalších úprav editoru zobrazení**. Ponechte výchozí název souboru (EditorMargin1.cs/vb).  
  
3.  Existují dva soubory kódu, následujícím způsobem:  
  
    -   Obsahuje EditorMargin1.cs `EditorMargin1` třídy.  
  
    -   Obsahuje EditorMargin1Factory.cs `EditorMargin1Factory` třídy.  
  
4.  Tento projekt sestavit a spustit ladění. Zobrazí se experimentální instanci. Pokud otevřete textový soubor, zobrazí se zelený okraj, který má slova "Hello EditorMargin1" pod vodorovný posuvník.  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřovací body služeb jazyka a editoru](../extensibility/language-service-and-editor-extension-points.md)