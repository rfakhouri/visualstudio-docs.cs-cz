---
title: 'Návod: Synchronizace vlastního podokna úloh s tlačítkem pásu karet | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- custom task panes [Office development in Visual Studio], showing and hiding
- showing custom task panes
- Ribbon [Office development in Visual Studio], custom task panes
- toggle buttons [Office development in Visual Studio]
- custom task panes [Office development in Visual Studio], synchronizing with Ribbon button
- user interfaces [Office development in Visual Studio], custom task panes
- synchronization [Office development in Visual Studio], custom task panes
- task panes [Office development in Visual Studio], showing and hiding
- custom task panes [Office development in Visual Studio], creating
- hiding custom task panes
- task panes [Office development in Visual Studio], creating
- task panes [Office development in Visual Studio], synchronizing with Ribbon button
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: ff3252a1ae234615cc4d4ed83a07d98a15092bee
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-synchronizing-a-custom-task-pane-with-a-ribbon-button"></a>Návod: Synchronizace vlastního podokna úloh s tlačítkem na pásu karet
  Tento návod ukazuje postup vytvoření vlastního podokna úloh, uživatelé mohou zobrazit nebo skrýt kliknutím na tlačítko přepnutí na pásu karet. Vždy byste měli vytvořit prvek uživatelského rozhraní (UI), jako je tlačítko, které mohou uživatelé kliknout a zobrazit nebo skrýt vlastního podokna úloh, protože aplikace Microsoft Office neposkytují výchozí způsob, jak uživatelům zobrazit nebo skrýt vlastní podokna úloh.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 I když tento návod používá Excel konkrétně, platí pro všechny aplikace, které jsou uvedeny výše koncepty znázorněno pomocí průvodce.  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Návrh uživatelského rozhraní vlastního podokna úloh.  
  
-   Přidání přepínací tlačítko pásu karet.  
  
-   Přepínací tlačítko synchronizace s vlastního podokna úloh.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Aplikace Microsoft Excel nebo Microsoft [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)].  
  
## <a name="creating-the-add-in-project"></a>Vytvoření projektu doplňku  
 V tomto kroku vytvoříte projektu doplňku VSTO pro Excel.  
  
#### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Vytvoření projektu doplněk aplikace Excel s názvem **SynchronizeTaskPaneAndRibbon**, pomocí šablony projektu doplněk aplikace Excel. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Otevře se **ThisAddIn.cs** nebo **ThisAddIn.vb** kód soubor a přidá **SynchronizeTaskPaneAndRibbon** projektu do **Průzkumníku řešení**.  
  
## <a name="adding-a-toggle-button-to-the-ribbon"></a>Přidání přepínače na pásu karet  
 Jedním z pokynů pro návrh aplikace Office je, že uživatelé by měli mít vždy řízení aplikace Office uživatelského rozhraní. Pokud chcete povolit uživatelům řídit vlastního podokna úloh, můžete přidat přepínací tlačítko pásu karet, který zobrazí a skryje do podokna úloh. Chcete-li vytvořit přepínací tlačítko, přidejte **pásu karet (vizuálního návrháře)** položku do projektu. Návrháře umožňuje přidat a umístěte ovládací prvky, nastavení vlastností ovládacího prvku a zpracování události ovládacího prvku. Další informace najdete v tématu [Návrhář pásu karet](../vsto/ribbon-designer.md).  
  
#### <a name="to-add-a-toggle-button-to-the-ribbon"></a>Chcete-li přidat přepínač na pásu karet  
  
1.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  
  
2.  V **přidat novou položku** dialogové okno, vyberte **pásu karet (vizuálního návrháře)**.  
  
3.  Změňte název nové pásu karet na **ManageTaskPaneRibbon**a klikněte na tlačítko **přidat**.  
  
     **ManageTaskPaneRibbon.cs** nebo **ManageTaskPaneRibbon.vb** soubor se otevře v Návrháři pásu karet a zobrazí se výchozí kartě a skupiny.  
  
4.  V Návrháři pásu karet klikněte na tlačítko **group1**.  
  
5.  V **vlastnosti** nastavte **popisek** vlastnost **podokně Správce úloh**.  
  
6.  Z **ovládacích prvků pásu karet Office** kartě **sada nástrojů**, přetáhněte **přepínací tlačítko** na **podokně Správce úloh** skupiny.  
  
7.  Klikněte na tlačítko **toggleButton1**.  
  
8.  V **vlastnosti** nastavte **popisek** vlastnost **zobrazit podokno úloha**.  
  
## <a name="designing-the-user-interface-of-the-custom-task-pane"></a>Návrh uživatelského rozhraní vlastního podokna úloh  
 Neexistuje žádné vizuálního návrháře pro vlastní podokna úloh, ale můžete navrhnout uživatelský ovládací prvek pro rozložení, které chcete. Dále v tomto návodu přidáte vlastního podokna úloh uživatelského ovládacího prvku.  
  
#### <a name="to-design-the-user-interface-of-the-custom-task-pane"></a>Návrh uživatelského rozhraní vlastního podokna úloh  
  
1.  Na **projektu** nabídky, klikněte na tlačítko **přidat uživatelský ovládací prvek**.  
  
2.  V **přidat novou položku** dialogové okno pole, změňte název uživatelského ovládacího prvku na **TaskPaneControl**a klikněte na tlačítko **přidat**.  
  
     Otevře se v Návrháři uživatelského ovládacího prvku.  
  
3.  Z **běžné ovládací prvky** kartě **sada nástrojů**, přetáhněte **TextBox** ovládacího prvku do uživatelského ovládacího prvku.  
  
## <a name="creating-the-custom-task-pane"></a>Vytvoření vlastního podokna úloh  
 Vytvoření vlastního podokna úloh při doplňku VSTO spustí, přidat uživatelský ovládací prvek do podokna úloh v <xref:Microsoft.Office.Tools.AddIn.Startup> obslužné rutiny události z doplňku VSTO. Ve výchozím nastavení nebudou viditelné vlastního podokna úloh. Dále v tomto návodu přidáte kód, který bude zobrazení nebo skrytí podokna úloh, když uživatel klikne přepínací tlačítko, které jste přidali na pásu karet.  
  
#### <a name="to-create-the-custom-task-pane"></a>Vytvoření vlastního podokna úloh  
  
1.  V **Průzkumníku řešení**, rozbalte položku **Excel**.  
  
2.  Klikněte pravým tlačítkem na **ThisAddIn.cs** nebo **ThisAddIn.vb** a klikněte na tlačítko **kód zobrazení**.  
  
3.  Přidejte následující kód, který `ThisAddIn` třídy. Tento kód deklaruje instanci `TaskPaneControl` jako člen skupiny `ThisAddIn`.  
  
     [!code-csharp[Trin_TaskPaneRibbonSynchronize#1](../vsto/codesnippet/CSharp/Trin_TaskPaneRibbonSynchronize/ThisAddIn.cs#1)]
     [!code-vb[Trin_TaskPaneRibbonSynchronize#1](../vsto/codesnippet/VisualBasic/Trin_TaskPaneRibbonSynchronize/ThisAddIn.vb#1)]  
  
4.  Nahraďte `ThisAddIn_Startup` obslužné rutiny události s následujícím kódem. Tento kód přidá `TaskPaneControl` do objektu `CustomTaskPanes` pole, ale nezobrazí vlastního podokna úloh (ve výchozím nastavení, <xref:Microsoft.Office.Tools.CustomTaskPane.Visible%2A> vlastnost <xref:Microsoft.Office.Tools.CustomTaskPane> třída je **false**). Kód jazyka Visual C# také připojí obslužnou rutinu události a <xref:Microsoft.Office.Tools.CustomTaskPane.VisibleChanged> událostí.  
  
     [!code-csharp[Trin_TaskPaneRibbonSynchronize#2](../vsto/codesnippet/CSharp/Trin_TaskPaneRibbonSynchronize/ThisAddIn.cs#2)]
     [!code-vb[Trin_TaskPaneRibbonSynchronize#2](../vsto/codesnippet/VisualBasic/Trin_TaskPaneRibbonSynchronize/ThisAddIn.vb#2)]  
  
5.  Přidejte následující metodu do `ThisAddIn` třídy. Tato metoda zpracovává <xref:Microsoft.Office.Tools.CustomTaskPane.VisibleChanged> událostí. Když uživatel nezavře do podokna úloh kliknutím **Zavřít** tlačítko (X), tato metoda aktualizace stavu přepínač na pásu karet.  
  
     [!code-csharp[Trin_TaskPaneRibbonSynchronize#3](../vsto/codesnippet/CSharp/Trin_TaskPaneRibbonSynchronize/ThisAddIn.cs#3)]
     [!code-vb[Trin_TaskPaneRibbonSynchronize#3](../vsto/codesnippet/VisualBasic/Trin_TaskPaneRibbonSynchronize/ThisAddIn.vb#3)]  
  
6.  Přidejte následující vlastnosti, která má `ThisAddIn` třídy. Tato vlastnost zpřístupní privátní `myCustomTaskPane1` objekt, který má jiné třídy. Dále v tomto návodu přidáte kód, který `MyRibbon` třídu, která používá tuto vlastnost.  
  
     [!code-csharp[Trin_TaskPaneRibbonSynchronize#4](../vsto/codesnippet/CSharp/Trin_TaskPaneRibbonSynchronize/ThisAddIn.cs#4)]
     [!code-vb[Trin_TaskPaneRibbonSynchronize#4](../vsto/codesnippet/VisualBasic/Trin_TaskPaneRibbonSynchronize/ThisAddIn.vb#4)]  
  
## <a name="hiding-and-showing-the-custom-task-pane-by-using-the-toggle-button"></a>Skrytí a zobrazení vlastního podokna úloh s použitím přepínací tlačítko  
 Posledním krokem je přidání kód, který zobrazí nebo skryje vlastního podokna úloh, když uživatel klikne na tlačítko přepnutí na pásu karet.  
  
#### <a name="to-display-and-hide-the-custom-task-pane-by-using-the-toggle-button"></a>K zobrazení a skrytí vlastního podokna úloh s použitím přepínací tlačítko  
  
1.  V Návrháři pásu karet klikněte dvakrát na **zobrazit podokno úloha** přepínací tlačítko.  
  
     Visual Studio automaticky vygeneruje obslužné rutiny události s názvem `toggleButton1_Click`, která zpracovává <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton.Click> událostí přepínací tlačítko. Visual Studio se rovněž otevře **MyRibbon.cs** nebo **MyRibbon.vb** souboru v editoru kódu.  
  
2.  Nahraďte `toggleButton1_Click` obslužné rutiny události s následujícím kódem. Když uživatel klikne na tlačítko přepnutí, tento kód zobrazí nebo skryje vlastního podokna úloh, v závislosti na tom, jestli je přepínací tlačítko stisknutí nebo nebyla stisknuta klávesa.  
  
     [!code-vb[Trin_TaskPaneRibbonSynchronize#5](../vsto/codesnippet/VisualBasic/Trin_TaskPaneRibbonSynchronize/ManageTaskPaneRibbon.vb#5)]
     [!code-csharp[Trin_TaskPaneRibbonSynchronize#5](../vsto/codesnippet/CSharp/Trin_TaskPaneRibbonSynchronize/ManageTaskPaneRibbon.cs#5)]  
  
## <a name="testing-the-add-in"></a>Testování v aplikaci  
 Při spuštění projektu aplikace Excel se spustí bez zobrazení vlastního podokna úloh. Klikněte na tlačítko přepnutí na pásu karet k testování kódu.  
  
#### <a name="to-test-your-vsto-add-in"></a>K testování vaší doplňku VSTO  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
     Potvrďte, že aplikace Excel se otevře a **doplňky** karta se zobrazí na pásu karet.  
  
2.  Klikněte **doplňky** na pásu karet.  
  
3.  V **podokně Správce úloh** klikněte na možnost **zobrazit podokno úloha** přepínací tlačítko.  
  
     Ověřte, zda je do podokna úloh můžete případně zobrazí a skryté po kliknutí na tlačítko přepínací tlačítko.  
  
4.  Pokud je zobrazen v podokně úloh, klikněte na tlačítko **Zavřít** tlačítko (X) v dolním podokně úloh.  
  
     Ověřte, že přepínací tlačítko pravděpodobně nebyla stisknuta.  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o tom, jak vytvořit vlastní podokna úloh z těchto témat:  
  
-   Vytvoření vlastního podokna úloh v doplňku VSTO pro jinou aplikaci. Další informace o aplikacích, které podporují vlastní podokna úloh najdete v tématu [vlastní podokna úloh](../vsto/custom-task-panes.md).  
  
-   Automatizace aplikace z vlastního podokna úloh. Další informace najdete v tématu [návod: automatizace aplikace z vlastního podokna úloh](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md).  
  
-   Vytvoření vlastního podokna úloh pro každý e-mailová zpráva, která je otevřen v aplikaci Outlook. Další informace najdete v tématu [návod: zobrazení vlastních podoken s e-mailových zpráv v aplikaci Outlook](../vsto/walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook.md).  
  
## <a name="see-also"></a>Viz také  
 [Vlastní podokna úloh](../vsto/custom-task-panes.md)   
 [Postupy: Přidání vlastního podokna úloh do aplikace](../vsto/how-to-add-a-custom-task-pane-to-an-application.md)   
 [Návod: Automatizace aplikace z vlastního podokna úloh](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md)   
 [Návod: Zobrazení vlastních podoken úloh s e-mailových zpráv v aplikaci Outlook](../vsto/walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook.md)   
 [Přehled pásu karet](../vsto/ribbon-overview.md)  
  
  