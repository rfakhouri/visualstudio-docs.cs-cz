---
title: "Návod: Přizpůsobení textového zobrazení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], new - customizing the view
ms.assetid: 32d32ac8-22ff-4de7-af69-bd46ec4ad9bf
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: ecbf5e3bed5ba506278f00b2b5b0b76f8f02850a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-customizing-the-text-view"></a>Návod: Přizpůsobení zobrazení textu
Textového zobrazení můžete přizpůsobit úpravou některý z následujících vlastností v jeho mapy editor formátu:  
  
-   Okraj indikátoru  
  
-   Vsuvka pro vložení  
  
-   Přepsat pomocí kurzoru  
  
-   Vybraný text  
  
-   Neaktivní vybraný text (který je vybraný text, který ztratil fokus)  
  
-   Viditelné prázdné znaky  
  
## <a name="prerequisites"></a>Požadavky  
 Od sady Visual Studio 2015 se neinstalovat sadu Visual Studio SDK z webu Stažení softwaru. Je zahrnuta jako volitelná funkce v instalačním programu sady Visual Studio. VS SDK můžete také nainstalovat později. Další informace najdete v tématu [instalace sady Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="creating-a-mef-project"></a>Vytvoření projektu MEF  
  
1.  Vytvoření projektu C# VSIX. (V **nový projekt** dialogovém okně, vyberte **Visual C# nebo rozšíření**, pak **projektu VSIX**.) Název řešení `ViewPropertyTest`.  
  
2.  Do projektu přidejte šablony položky třídění Editor. Další informace najdete v tématu [vytváření rozšíření pomocí šablony položky Editor](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
3.  Odstraňte existující soubory třídy.  
  
## <a name="defining-the-content-type"></a>Definování typu obsahu  
  
1.  Přidejte soubor třídy a pojmenujte ji `ViewPropertyModifier`.  
  
2.  Přidejte následující `using` direktivy:  
  
     [!code-csharp[VSSDKViewPropertyTest#1](../extensibility/codesnippet/CSharp/walkthrough-customizing-the-text-view_1.cs)]
     [!code-vb[VSSDKViewPropertyTest#1](../extensibility/codesnippet/VisualBasic/walkthrough-customizing-the-text-view_1.vb)]  
  
3.  Deklarace třídy s názvem `TestViewCreationListener` který dědí z <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener>. Exportujte tuto třídu s následujícími atributy:  
  
    -   <xref:Microsoft.VisualStudio.Utilities.ContentTypeAttribute>Chcete-li určit typ obsahu, pro kterou platí tato naslouchací proces.  
  
    -   <xref:Microsoft.VisualStudio.Text.Editor.TextViewRoleAttribute>Chcete-li určit roli této naslouchacího procesu.  
  
     [!code-csharp[VSSDKViewPropertyTest#2](../extensibility/codesnippet/CSharp/walkthrough-customizing-the-text-view_2.cs)]
     [!code-vb[VSSDKViewPropertyTest#2](../extensibility/codesnippet/VisualBasic/walkthrough-customizing-the-text-view_2.vb)]  
  
4.  V této třídě importovat <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMapService>.  
  
     [!code-csharp[VSSDKViewPropertyTest#3](../extensibility/codesnippet/CSharp/walkthrough-customizing-the-text-view_3.cs)]
     [!code-vb[VSSDKViewPropertyTest#3](../extensibility/codesnippet/VisualBasic/walkthrough-customizing-the-text-view_3.vb)]  
  
## <a name="changing-the-view-properties"></a>Změna vlastností zobrazení  
  
1.  Implementace <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextViewCreationListener.TextViewCreated%2A> metoda tak, aby se při otevření zobrazení změní zobrazit vlastnosti. K provedení změn, nejprve najít <xref:System.Windows.ResourceDictionary> odpovídající aspektů zobrazení, které chcete najít. Potom změnit odpovídající vlastnost ve slovníku prostředků a nastavte vlastnosti. Batch volání <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMap.SetProperties%2A> metoda voláním <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMap.BeginBatchUpdate%2A> metoda před nastavením vlastnosti a potom <xref:Microsoft.VisualStudio.Text.Classification.IEditorFormatMap.EndBatchUpdate%2A> po nastavení vlastností.  
  
     [!code-csharp[VSSDKViewPropertyTest#4](../extensibility/codesnippet/CSharp/walkthrough-customizing-the-text-view_4.cs)]
     [!code-vb[VSSDKViewPropertyTest#4](../extensibility/codesnippet/VisualBasic/walkthrough-customizing-the-text-view_4.vb)]  
  
## <a name="building-and-testing-the-code"></a>Vytváření a testování kódu  
  
1.  Sestavte řešení.  
  
     Když spustíte tohoto projektu v ladicím programu, je vytvořena instance druhou instanci sady Visual Studio.  
  
2.  Vytvoření textového souboru a zadejte text.  
  
    -   Vsuvka pro vložení by měl být purpurová a přepsat pomocí kurzoru by měla být tyrkysová.  
  
    -   Okraj ukazatele (nalevo od textového zobrazení) by měla být light zelená.  
  
3.  Vyberte text, který jste právě zadali. Barva vybraný text by měl být light růžový.  
  
4.  Po výběru text klikněte kamkoli mimo okno text. Barva vybraný text by měl být tmavorůžová.  
  
5.  Zapněte viditelné prázdný znak. (Na **upravit** nabídky, přejděte na příkaz **Upřesnit** a pak klikněte na **zobrazení mezer**). Zadejte text, některé karty. Má být zobrazena Red šipek, které představují karty.  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřovací body služeb jazyka a editoru](../extensibility/language-service-and-editor-extension-points.md)