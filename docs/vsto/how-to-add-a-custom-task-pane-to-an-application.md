---
title: "Postupy: Přidání vlastního podokna úloh do aplikace | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- task panes [Office development in Visual Studio], adding to application
- custom task panes [Office development in Visual Studio], adding to application
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 9e4e5d03dd08e4a7e8631db65c74b843720d037d
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-add-a-custom-task-pane-to-an-application"></a>Postupy: Přidání vlastního podokna úloh do aplikace
  Můžete přidat vlastního podokna úloh do aplikace uvedené výše pomocí doplňku VSTO. Další informace najdete v tématu [vlastní podokna úloh](../vsto/custom-task-panes.md).  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="adding-a-custom-task-pane-to-an-application"></a>Přidání vlastního podokna úloh do aplikace  
  
#### <a name="to-add-a-custom-task-pane-to-an-application"></a>Přidání vlastního podokna úloh do aplikace  
  
1.  Otevřete nebo vytvoření projektu doplňku VSTO pro jednu z aplikací uvedených výše. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **přidat uživatelský ovládací prvek**.  
  
3.  V **přidat novou položku** dialogové okno pole, změňte název nového uživatelského ovládacího prvku na **MyUserControl**a potom klikněte na **přidat**.  
  
     Otevře se v Návrháři uživatelského ovládacího prvku.  
  
4.  Přidejte jeden nebo více ovládacích prvků Windows Forms z **sada nástrojů** do uživatelského ovládacího prvku.  
  
5.  Otevřete **ThisAddIn.cs** nebo **ThisAddIn.vb** souboru kódu.  
  
6.  Přidejte následující kód, který `ThisAddIn` třídy. Tento kód deklaruje instancí `MyUserControl` a <xref:Microsoft.Office.Tools.CustomTaskPane> jako členy `ThisAddIn` třídy.  
  
     [!code-vb[Trin_TaskPaneBasic#1](../vsto/codesnippet/VisualBasic/Trin_TaskPaneBasic/ThisAddIn.vb#1)]
     [!code-csharp[Trin_TaskPaneBasic#1](../vsto/codesnippet/CSharp/Trin_TaskPaneBasic/ThisAddIn.cs#1)]  
  
7.  Přidejte následující kód, který `ThisAddIn_Startup` obslužné rutiny události. Tento kód vytvoří novou <xref:Microsoft.Office.Tools.CustomTaskPane> přidáním `MyUserControl` do objektu `CustomTaskPanes` kolekce. Kód zobrazí také v podokně úloh.  
  
     [!code-vb[Trin_TaskPaneBasic#2](../vsto/codesnippet/VisualBasic/Trin_TaskPaneBasic/ThisAddIn.vb#2)]
     [!code-csharp[Trin_TaskPaneBasic#2](../vsto/codesnippet/CSharp/Trin_TaskPaneBasic/ThisAddIn.cs#2)]  
  
    > [!NOTE]  
    >  Tento kód přidruží vlastního podokna úloh aktivního okna aplikace. Některé aplikace můžete upravit tento kód zajistit, aby se do podokna úloh s jinými dokumenty nebo položky v aplikaci. Další informace najdete v tématu [vlastní podokna úloh](../vsto/custom-task-panes.md).  
  
## <a name="see-also"></a>Viz také  
 [Přizpůsobení uživatelského rozhraní sady Office](../vsto/office-ui-customization.md)   
 [Vlastní podokna úloh](../vsto/custom-task-panes.md)   
 [Návod: Automatizace aplikace z vlastního podokna úloh](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md)  
  
  