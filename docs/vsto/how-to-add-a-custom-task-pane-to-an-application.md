---
title: 'Postupy: Přidání vlastního podokna úloh do aplikace'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- task panes [Office development in Visual Studio], adding to application
- custom task panes [Office development in Visual Studio], adding to application
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 88ac74d0e2c666926c5b88976146878991729628
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63427912"
---
# <a name="how-to-add-a-custom-task-pane-to-an-application"></a>Postupy: Přidání vlastního podokna úloh do aplikace
  Můžete přidat uvedených vlastního podokna úloh do aplikace pomocí doplňku VSTO. Další informace najdete v tématu [vlastní podokna úloh](../vsto/custom-task-panes.md).

 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

> [!NOTE]
> Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení integrovaného vývojového prostředí sady Visual Studio](../ide/personalizing-the-visual-studio-ide.md).

## <a name="add-a-custom-task-pane-to-an-application"></a>Přidání vlastního podokna úloh do aplikace

### <a name="to-add-a-custom-task-pane-to-an-application"></a>Přidání vlastního podokna úloh do aplikace

1. Otevřete nebo vytvořte projekt doplňku VSTO pro jednu z výše uvedených aplikací. Další informace najdete v tématu [jak: Vytvářet projekty pro Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).

2. Na **projektu** nabídky, klikněte na tlačítko **přidat uživatelský ovládací prvek**.

3. V **přidat novou položku** dialogové okno pole, změňte název nového uživatelského ovládacího prvku na **MyUserControl**a potom klikněte na tlačítko **přidat**.

     Uživatelský ovládací prvek se otevře v návrháři.

4. Přidejte jeden nebo více ovládacích prvků Windows Forms z **nástrojů** uživatelského ovládacího prvku.

5. Otevřít **ThisAddIn.cs** nebo **ThisAddIn.vb** soubor kódu.

6. Přidejte následující kód, který `ThisAddIn` třídy. Tento kód deklaruje instance `MyUserControl` a <xref:Microsoft.Office.Tools.CustomTaskPane> jako členy `ThisAddIn` třídy.

     [!code-vb[Trin_TaskPaneBasic#1](../vsto/codesnippet/VisualBasic/Trin_TaskPaneBasic/ThisAddIn.vb#1)]
     [!code-csharp[Trin_TaskPaneBasic#1](../vsto/codesnippet/CSharp/Trin_TaskPaneBasic/ThisAddIn.cs#1)]

7. Přidejte následující kód, který `ThisAddIn_Startup` obslužné rutiny události. Tento kód vytvoří novou <xref:Microsoft.Office.Tools.CustomTaskPane> tak, že přidáte `MyUserControl` objektu `CustomTaskPanes` kolekce. Kód také zobrazí v podokně úloh.

     [!code-vb[Trin_TaskPaneBasic#2](../vsto/codesnippet/VisualBasic/Trin_TaskPaneBasic/ThisAddIn.vb#2)]
     [!code-csharp[Trin_TaskPaneBasic#2](../vsto/codesnippet/CSharp/Trin_TaskPaneBasic/ThisAddIn.cs#2)]

    > [!NOTE]
    > Tento kód přidruží vlastního podokna úloh aktivního okna aplikace. U některých aplikací můžete upravit tento kód a zajistěte tak, že se zobrazí v podokně úloh s jinými dokumenty nebo položek v aplikaci. Další informace najdete v tématu [vlastní podokna úloh](../vsto/custom-task-panes.md).

## <a name="see-also"></a>Viz také:
- [Přizpůsobení uživatelského rozhraní systému Office](../vsto/office-ui-customization.md)
- [Vlastní podokna úloh](../vsto/custom-task-panes.md)
- [Návod: Automatizace aplikace z vlastního podokna úloh](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md)
