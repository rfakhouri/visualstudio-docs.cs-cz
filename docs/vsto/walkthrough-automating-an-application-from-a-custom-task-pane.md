---
title: "Návod: Automatizace aplikace z vlastního podokna úloh | Microsoft Docs"
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
- task panes [Office development in Visual Studio], PowerPoint
- PowerPoint [Office development in Visual Studio], custom task panes
- automating Office applications
- custom task panes [Office development in Visual Studio], automating applications
- custom task panes [Office development in Visual Studio], PowerPoint
- task panes [Office development in Visual Studio], automating applications
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 86f925cda43bf73354b94ecc966cdcae1a0c3ddd
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-automating-an-application-from-a-custom-task-pane"></a>Návod: Automatizace aplikace z vlastního podokna úloh
  Tento návod ukazuje postup vytvoření vlastního podokna úloh umožňuje automatizovat PowerPoint. Vlastního podokna úloh vloží data do snímku, když uživatel klikne <xref:System.Windows.Forms.MonthCalendar> ovládací prvek, který je v podokně úloh.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 I když tento návod používá PowerPoint konkrétně, platí pro všechny aplikace, které jsou uvedeny výše koncepty znázorněno pomocí průvodce.  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Návrh uživatelského rozhraní vlastního podokna úloh.  
  
-   Automatizace aplikace PowerPoint z vlastního podokna úloh.  
  
-   Zobrazení v podokně úloh v aplikaci PowerPoint.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft PowerPoint 2010 nebo [!INCLUDE[PowerPoint_15_short](../vsto/includes/powerpoint-15-short-md.md)].  
  
## <a name="creating-the-add-in-project"></a>Vytvoření projektu doplňku  
 Prvním krokem je vytvoření projektu doplňku VSTO pro PowerPoint.  
  
#### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Vytvoření projektu doplňku VSTO pro PowerPoint s názvem **MyAddIn**, a to pomocí šablony projektu doplňku PowerPoint. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]Otevře se **ThisAddIn.cs** nebo **ThisAddIn.vb** kód soubor a přidá **MyAddIn** projektu do **Průzkumníku řešení**.  
  
## <a name="designing-the-user-interface-of-the-custom-task-pane"></a>Návrh uživatelského rozhraní vlastního podokna úloh  
 Neexistuje žádné vizuálního návrháře pro vlastní podokna úloh, ale můžete navrhnout uživatelský ovládací prvek pro rozložení, které chcete. Dále v tomto návodu přidáte vlastního podokna úloh uživatelského ovládacího prvku.  
  
#### <a name="to-design-the-user-interface-of-the-custom-task-pane"></a>Návrh uživatelského rozhraní vlastního podokna úloh  
  
1.  Na **projektu** nabídky, klikněte na tlačítko **přidat uživatelský ovládací prvek**.  
  
2.  V **přidat novou položku** dialogové okno pole, změňte název uživatelského ovládacího prvku na **MyUserControl**a klikněte na tlačítko **přidat**.  
  
     Otevře se v Návrháři uživatelského ovládacího prvku.  
  
3.  Z **běžné ovládací prvky** kartě **sada nástrojů**, přetáhněte ji **MonthCalendar** ovládacího prvku do uživatelského ovládacího prvku.  
  
     Pokud **MonthCalendar** ovládací prvek je větší než návrhové ploše uživatelského ovládacího prvku, změnit velikost uživatelského ovládacího prvku přizpůsobit **MonthCalendar** ovládacího prvku.  
  
## <a name="automating-powerpoint-from-the-custom-task-pane"></a>Automatizace aplikace PowerPoint z vlastního podokna úloh  
 Účelem doplňku VSTO je uvést vybraným datem na prvním snímku aktivní prezentace. Použití <xref:System.Windows.Forms.MonthCalendar.DateChanged> události ovládacího prvku přidat vybraným datem vždy, když se změní.  
  
#### <a name="to-automate-powerpoint-from-the-custom-task-pane"></a>K automatizaci PowerPoint z vlastního podokna úloh  
  
1.  V návrháři, dvakrát klikněte <xref:System.Windows.Forms.MonthCalendar> ovládacího prvku.  
  
     **MyUserControl.cs** nebo **MyUserControl.vb** soubor otevře a obslužné rutiny události pro <xref:System.Windows.Forms.MonthCalendar.DateChanged> dojde k vytvoření události.  
  
2.  Na začátek souboru přidejte následující kód. Tento kód vytvoří aliasy pro <xref:Microsoft.Office.Core> a <xref:Microsoft.Office.Interop.PowerPoint> obory názvů.  
  
     [!code-csharp[Trin_TaskPaneMonthCalendar#1](../vsto/codesnippet/CSharp/Trin_TaskPaneMonthCalendar/MyUserControl.cs#1)]
     [!code-vb[Trin_TaskPaneMonthCalendar#1](../vsto/codesnippet/VisualBasic/Trin_TaskPaneMonthCalendar/MyUserControl.vb#1)]  
  
3.  Přidejte následující kód, který `MyUserControl` třídy. Tento kód deklaruje <xref:Microsoft.Office.Interop.PowerPoint.Shape> objektu jako člen skupiny `MyUserControl`. V tomto kroku použijete to <xref:Microsoft.Office.Interop.PowerPoint.Shape> přidat textové pole na snímek v aktivní prezentace.  
  
     [!code-csharp[Trin_TaskPaneMonthCalendar#2](../vsto/codesnippet/CSharp/Trin_TaskPaneMonthCalendar/MyUserControl.cs#2)]
     [!code-vb[Trin_TaskPaneMonthCalendar#2](../vsto/codesnippet/VisualBasic/Trin_TaskPaneMonthCalendar/MyUserControl.vb#2)]  
  
4.  Nahraďte `monthCalendar1_DateChanged` obslužné rutiny události s následujícím kódem. Tento kód přidá textové pole na první snímek aktivní prezentace a potom přidá aktuálně vybrané datum do textového pole. Tento kód používá `Globals.ThisAddIn` objekt, který má přístup k modelu objektů aplikace PowerPoint.  
  
     [!code-csharp[Trin_TaskPaneMonthCalendar#3](../vsto/codesnippet/CSharp/Trin_TaskPaneMonthCalendar/MyUserControl.cs#3)]
     [!code-vb[Trin_TaskPaneMonthCalendar#3](../vsto/codesnippet/VisualBasic/Trin_TaskPaneMonthCalendar/MyUserControl.vb#3)]  
  
5.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **MyAddIn** projektu a pak klikněte na **sestavení**. Ověřte, že sestavení projektu bez chyb.  
  
## <a name="displaying-the-custom-task-pane"></a>Zobrazení vlastního podokna úloh  
 K zobrazení vlastního podokna úloh při doplňku VSTO spuštění, přidat uživatelský ovládací prvek do podokna úloh v <xref:Microsoft.Office.Tools.AddIn.Startup> obslužné rutiny události z doplňku VSTO.  
  
#### <a name="to-display-the-custom-task-pane"></a>Chcete-li zobrazit vlastního podokna úloh  
  
1.  V **Průzkumníku řešení**, rozbalte položku **PowerPoint**.  
  
2.  Klikněte pravým tlačítkem na **ThisAddIn.cs** nebo **ThisAddIn.vb** a klikněte na tlačítko **kód zobrazení**.  
  
3.  Přidejte následující kód, který `ThisAddIn` třídy. Tento kód deklaruje instancí `MyUserControl` a <xref:Microsoft.Office.Tools.CustomTaskPane> jako členy `ThisAddIn` třídy.  
  
     [!code-vb[Trin_TaskPaneMonthCalendar#4](../vsto/codesnippet/VisualBasic/Trin_TaskPaneMonthCalendar/ThisAddIn.vb#4)]
     [!code-csharp[Trin_TaskPaneMonthCalendar#4](../vsto/codesnippet/CSharp/Trin_TaskPaneMonthCalendar/ThisAddIn.cs#4)]  
  
4.  Nahraďte `ThisAddIn_Startup` obslužné rutiny události s následujícím kódem. Tento kód vytvoří novou <xref:Microsoft.Office.Tools.CustomTaskPane> přidáním `MyUserControl` do objektu `CustomTaskPanes` kolekce. Kód zobrazí také v podokně úloh.  
  
     [!code-vb[Trin_TaskPaneMonthCalendar#5](../vsto/codesnippet/VisualBasic/Trin_TaskPaneMonthCalendar/ThisAddIn.vb#5)]
     [!code-csharp[Trin_TaskPaneMonthCalendar#5](../vsto/codesnippet/CSharp/Trin_TaskPaneMonthCalendar/ThisAddIn.cs#5)]  
  
## <a name="testing-the-add-in"></a>Testování v aplikaci  
 Po spuštění projektu PowerPoint se doplňku VSTO zobrazí vlastního podokna úloh. Klikněte <xref:System.Windows.Forms.MonthCalendar> řízení k testování kódu.  
  
#### <a name="to-test-your-vsto-add-in"></a>K testování vaší doplňku VSTO  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
2.  Potvrďte, že vlastního podokna úloh je zobrazen.  
  
3.  Klikněte na datum v <xref:System.Windows.Forms.MonthCalendar> ovládací prvek v podokně úloh.  
  
     Data budou vložena do první snímek aktivní prezentace.  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o tom, jak vytvořit vlastní podokna úloh z těchto témat:  
  
-   Vytvoření vlastního podokna úloh v doplňku VSTO pro jinou aplikaci. Další informace o aplikacích, které podporují vlastní podokna úloh najdete v tématu [vlastní podokna úloh](../vsto/custom-task-panes.md).  
  
-   Vytvoří tlačítko pásu karet, které lze použít ke skrytí nebo zobrazení vlastního podokna úloh. Další informace najdete v tématu [návod: synchronizace vlastního podokna úloh s tlačítkem pásu karet](../vsto/walkthrough-synchronizing-a-custom-task-pane-with-a-ribbon-button.md).  
  
-   Vytvoření vlastního podokna úloh pro každý e-mailová zpráva, která je otevřen v aplikaci Outlook. Další informace najdete v tématu [návod: zobrazení vlastních podoken s e-mailových zpráv v aplikaci Outlook](../vsto/walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook.md).  
  
## <a name="see-also"></a>Viz také  
 [Vlastní podokna úloh](../vsto/custom-task-panes.md)   
 [Postupy: Přidání vlastního podokna úloh do aplikace](../vsto/how-to-add-a-custom-task-pane-to-an-application.md)   
 [Návod: Synchronizace vlastního podokna úloh s tlačítkem pásu karet](../vsto/walkthrough-synchronizing-a-custom-task-pane-with-a-ribbon-button.md)   
 [Návod: Zobrazení vlastních podoken úloh s e-mailovými zprávami v aplikaci Outlook](../vsto/walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook.md)  
  
  