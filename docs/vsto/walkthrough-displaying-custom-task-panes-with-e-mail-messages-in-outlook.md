---
title: "Návod: Zobrazení vlastních podoken úloh s e-mailových zpráv v aplikaci Outlook | Microsoft Docs"
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
- Outlook [Office development in Visual Studio], custom task panes
- task panes [Office development in Visual Studio], displaying with e-mail messages
- displaying custom task panes in e-mail
- e-mail [Office development in Visual Studio], custom task panes displayed in
- custom task panes [Office development in Visual Studio], displaying with e-mail messages
ms.assetid: 04943967-a7ef-4876-9584-84ada427e3f3
caps.latest.revision: "59"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: c96744b433f4ad481e500420ffeab8caad3772c1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-displaying-custom-task-panes-with-e-mail-messages-in-outlook"></a>Návod: Zobrazení vlastních podoken úloh s e-mailovými zprávami v aplikaci Outlook
  Tento návod ukazuje, jak zobrazit jedinečný instanci vlastního podokna úloh s každou e-mailová zpráva, která je vytvořit nebo otevřít. Uživatele můžete zobrazit nebo skrýt podokno úloh pomocí tlačítka na pásu karet každou e-mailové zprávy.  
  
 [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]  
  
 Pokud chcete zobrazit vlastního podokna úloh s více nástroj Inspector nebo Průzkumníka windows, musíte vytvořit instanci vlastního podokna úloh pro každý okno, které je otevřen. Další informace o chování vlastních podoken úloh v aplikaci Outlook windows najdete v tématu [vlastní podokna úloh](../vsto/custom-task-panes.md).  
  
> [!NOTE]  
>  Tento názorný postup uvede kód doplňku VSTO v malých částech, aby bylo snazší a proberte logiku za kód.  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Návrh uživatelského rozhraní (UI) z vlastního podokna úloh.  
  
-   Vytvoření vlastní uživatelské rozhraní pásu karet.  
  
-   Zobrazení vlastní uživatelské rozhraní pásu karet s e-mailových zpráv.  
  
-   Vytvoření třídy pro správu Inspector windows a vlastních podoken úloh.  
  
-   Inicializace a Uklízení prostředky využívané třídou doplňku VSTO.  
  
-   Přepínací tlačítko pásu karet synchronizace s vlastního podokna úloh.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Microsoft [!INCLUDE[Outlook_15_short](../vsto/includes/outlook-15-short-md.md)] nebo aplikace Microsoft Outlook 2010.  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak provést i pomocí podokna úloh v aplikaci Outlook?](http://go.microsoft.com/fwlink/?LinkID=130309).  
  
## <a name="creating-the-project"></a>Vytvoření projektu  
 Vlastní podokna úloh jsou implementované v doplňcích VSTO. Začněte vytvořením projektu doplňku VSTO pro Outlook.  
  
#### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Vytvoření **doplněk aplikace Outlook** projektu s názvem **OutlookMailItemTaskPane**. Použití **doplněk aplikace Outlook** šablona projektu. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]Otevře se **ThisAddIn.cs** nebo **ThisAddIn.vb** kód soubor a přidá **OutlookMailItemTaskPane** projektu do **Průzkumníku řešení**.  
  
## <a name="designing-the-user-interface-of-the-custom-task-pane"></a>Návrh uživatelského rozhraní vlastního podokna úloh  
 Neexistuje žádné vizuálního návrháře pro vlastní podokna úloh, ale můžete navrhnout uživatelského ovládacího prvku pomocí uživatelského rozhraní mají. V podokně úloh v této doplňku VSTO má jednoduchého uživatelského rozhraní, která obsahuje <xref:System.Windows.Forms.TextBox> ovládacího prvku. Dále v tomto návodu přidáte vlastního podokna úloh uživatelského ovládacího prvku.  
  
#### <a name="to-design-the-user-interface-of-the-custom-task-pane"></a>Návrh uživatelského rozhraní vlastního podokna úloh  
  
1.  V **Průzkumníku řešení**, klikněte **OutlookMailItemTaskPane** projektu.  
  
2.  Na **projektu** nabídky, klikněte na tlačítko **přidat uživatelský ovládací prvek**.  
  
3.  V **přidat novou položku** dialogové okno pole, změňte název uživatelského ovládacího prvku na **TaskPaneControl**a potom klikněte na **přidat**.  
  
     Otevře se v Návrháři uživatelského ovládacího prvku.  
  
4.  Z **běžné ovládací prvky** kartě **sada nástrojů**, přetáhněte **TextBox** ovládacího prvku do uživatelského ovládacího prvku.  
  
## <a name="designing-the-user-interface-of-the-ribbon"></a>Návrh uživatelského rozhraní na pásu karet  
 Jedním z cílů pro tento doplněk VSTO bývá umožnit uživateli způsob, jak skrytí nebo zobrazení podokna vlastní úloh na pásu karet každou e-mailové zprávy. Pokud chcete zadat uživatelské rozhraní, vytvořte vlastní uživatelské rozhraní pásu karet, které zobrazí přepínací tlačítko, které mohou uživatelé kliknout a zobrazit nebo skrýt podokno úloh.  
  
#### <a name="to-create-a-custom-ribbon-ui"></a>Chcete-li vytvořit vlastní uživatelské rozhraní pásu karet  
  
1.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  
  
2.  V **přidat novou položku** dialogové okno, vyberte **pásu karet (vizuálního návrháře)**.  
  
3.  Změňte název nové pásu karet na **ManageTaskPaneRibbon**a klikněte na tlačítko **přidat**.  
  
     **ManageTaskPaneRibbon.cs** nebo **ManageTaskPaneRibbon.vb** soubor se otevře v Návrháři pásu karet a zobrazí se výchozí kartě a skupiny.  
  
4.  V Návrháři pásu karet klikněte na tlačítko **group1**.  
  
5.  V **vlastnosti** nastavte **popisek** vlastnost **podokně Správce úloh**.  
  
6.  Z **ovládacích prvků pásu karet Office** kartě **sada nástrojů**, přetáhněte ji na ovládací přepínací tlačítko **podokně Správce úloh** skupiny.  
  
7.  Klikněte na tlačítko **toggleButton1**.  
  
8.  V **vlastnosti** nastavte **popisek** vlastnost **zobrazit podokno úloha**.  
  
## <a name="display-the-custom-ribbon-user-interface-with-e-mail-messages"></a>Zobrazit uživatelské rozhraní vlastní pás karet s e-mailových zpráv  
 Vlastního podokna úloh, které vytvoříte v tomto návodu je určena pro zobrazí pouze s Inspector windows, které obsahují e-mailových zpráv. Proto nastavte vlastnosti, které chcete zobrazit vlastní uživatelské rozhraní pásu karet pouze s těmito windows.  
  
#### <a name="to-display-the-custom-ribbon-ui-with-e-mail-messages"></a>Zobrazit vlastní uživatelské rozhraní pásu karet s e-mailových zpráv  
  
1.  V Návrháři pásu karet klikněte **ManageTaskPaneRibbon** pásu karet.  
  
2.  V **vlastnosti** klikněte rozevíracího seznamu vedle **RibbonType**a vyberte **Microsoft.Outlook.Mail.Compose** a  **Microsoft.Outlook.Mail.Read**.  
  
## <a name="creating-a-class-to-manage-inspector-windows-and-custom-task-panes"></a>Vytvoření třídy pro správu Inspector Windows a vlastních podoken úloh  
 Existuje několik případů, kdy doplňku VSTO musí identifikovat které vlastního podokna úloh je přidružen konkrétní e-mailová zpráva. Tyto případy patří:  
  
-   Když uživatel nezavře e-mailové zprávy. V takovém případě doplňku VSTO musíte odebrat odpovídající vlastního podokna úloh k zajištění, že jsou správně vyčistit prostředky využívané třídou doplňku VSTO.  
  
-   Když uživatel nezavře vlastního podokna úloh. V takovém případě doplňku VSTO musí aktualizovat stav přepínací tlačítko na pásu karet e-mailové zprávy.  
  
-   Když uživatel klikne na tlačítko přepnutí na pásu karet. V takovém případě doplňku VSTO musí skrytí nebo zobrazení podokna úloh.  
  
 Pokud chcete povolit doplňku VSTO ke sledování které vlastního podokna úloh souvisí s každou otevřete e-mailová zpráva, vytvořte vlastní třídu, která zabalí dvojici <xref:Microsoft.Office.Interop.Outlook.Inspector> a <xref:Microsoft.Office.Tools.CustomTaskPane> objekty. Tato třída se vytvoří nový objekt podokně vlastní úlohu pro každou e-mailovou zprávu a odstraní vlastního podokna úloh, při zavření odpovídající e-mailová zpráva.  
  
#### <a name="to-create-a-class-to-manage-inspector-windows-and-custom-task-panes"></a>Pro vytvoření třídy pro správu Inspector windows a vlastních podoken úloh  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **ThisAddIn.cs** nebo **ThisAddIn.vb** souboru a potom klikněte na **kód zobrazení**.  
  
2.  Na začátek souboru přidejte následující příkazy.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#2](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#2)]
     [!code-vb[Trin_OutlookMailItemTaskPane#2](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#2)]  
  
3.  Přidejte následující kód, který **ThisAddIn.cs** nebo **ThisAddIn.vb** souboru mimo `ThisAddIn` – třída (pro Visual C# přidejte tento kód do `OutlookMailItemTaskPane` oboru názvů). `InspectorWrapper` Třída spravuje pár <xref:Microsoft.Office.Interop.Outlook.Inspector> a <xref:Microsoft.Office.Tools.CustomTaskPane> objekty. Dokončí definici této třídy v následujících krocích.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#3](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#3)]
     [!code-vb[Trin_OutlookMailItemTaskPane#3](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#3)]  
  
4.  Přidejte následující konstruktor za kód, který jste přidali v předchozím kroku. Tento konstruktor vytvoří a inicializuje nový vlastního podokna úloh přidružený <xref:Microsoft.Office.Interop.Outlook.Inspector> objekt, který se předává v. V jazyce C#, konstruktoru také připojí obslužné rutiny událostí k <xref:Microsoft.Office.Interop.Outlook.InspectorEvents_Event.Close> události <xref:Microsoft.Office.Interop.Outlook.Inspector> objekt a <xref:Microsoft.Office.Tools.CustomTaskPane.VisibleChanged> události <xref:Microsoft.Office.Tools.CustomTaskPane> objektu.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#4](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#4)]
     [!code-vb[Trin_OutlookMailItemTaskPane#4](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#4)]  
  
5.  Přidejte následující metodu za kód, který jste přidali v předchozím kroku. Tato metoda je obslužné rutiny události pro <xref:Microsoft.Office.Tools.CustomTaskPane.VisibleChanged> události <xref:Microsoft.Office.Tools.CustomTaskPane> objekt, který je součástí `InspectorWrapper` třídy. Tento kód aktualizuje stav přepínací tlačítko vždy, když uživatel otevře nebo zavře vlastního podokna úloh.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#5](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#5)]
     [!code-vb[Trin_OutlookMailItemTaskPane#5](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#5)]  
  
6.  Přidejte následující metodu za kód, který jste přidali v předchozím kroku. Tato metoda je obslužné rutiny události pro <xref:Microsoft.Office.Interop.Outlook.InspectorEvents_Event.Close> události <xref:Microsoft.Office.Interop.Outlook.Inspector> objekt, který obsahuje aktuální e-mailová zpráva. Obslužné rutiny události uvolní prostředky při zavření e-mailová zpráva. Obslužné rutiny události také odebere aktuální vlastního podokna úloh z `CustomTaskPanes` kolekce. To pomáhá zabránit více instancí vlastního podokna úloh po otevření další e-mailová zpráva.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#6](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#6)]
     [!code-vb[Trin_OutlookMailItemTaskPane#6](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#6)]  
  
7.  Přidejte následující kód za kód, který jste přidali v předchozím kroku. Dále v tomto návodu budete volat tuto vlastnost z metody v Uživatelském rozhraní pásu karet vlastní zobrazení nebo skrytí vlastního podokna úloh.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#7](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#7)]
     [!code-vb[Trin_OutlookMailItemTaskPane#7](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#7)]  
  
## <a name="initializing-and-cleaning-up-resources-used-by-the-add-in"></a>Inicializace a Uklízení prostředky používané v aplikaci  
 Přidejte kód, který `ThisAddIn` tříd k chybě při inicializaci doplňku VSTO, když je načten a vyčistěte prostředky využívané třídou doplňku VSTO v případě, že je odpojen. Nastavením obslužné rutiny události pro inicializaci doplňku VSTO <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> událostí a pomocí předání této obslužné rutiny události všechny existující e-mailových zpráv. Když doplňku VSTO je odpojen, odpojte obslužné rutiny události a vyčistit objekty používané doplňku VSTO.  
  
#### <a name="to-initialize-and-clean-up-resources-used-by-the-vsto-add-in"></a>K inicializaci a vyčistit prostředky využívané třídou doplňku VSTO  
  
1.  V **ThisAddIn.cs** nebo **ThisAddIn.vb** souboru, vyhledejte definice `ThisAddIn` třídy.  
  
2.  Přidejte následující deklarace k `ThisAddIn` třídy:  
  
    -   `inspectorWrappersValue` Pole obsahuje všechny <xref:Microsoft.Office.Interop.Outlook.Inspector> a `InspectorWrapper` objekty, které jsou spravovány nástrojem doplňku VSTO.  
  
    -   `inspectors` Pole udržuje odkaz na kolekci systému windows, nástroj Inspector v aktuální instanci aplikace Outlook. Tento odkaz brání uvolnění paměti, která obsahuje obslužné rutiny události pro uvolňování paměti <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> událost, která bude deklarovat v dalším kroku.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#8](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#8)]
     [!code-vb[Trin_OutlookMailItemTaskPane#8](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#8)]  
  
3.  Nahraďte `ThisAddIn_Startup` metoda následujícím kódem. Připojí obslužné rutiny události pro tento kód <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> událostí a předává všechny existující <xref:Microsoft.Office.Interop.Outlook.Inspector> objekt obslužné rutiny události. Pokud uživatel načítá doplňku VSTO po Outlook je již spuštěna, doplňku VSTO používá tyto informace k vytvoření vlastních podoken úloh pro všechny e-mailových zpráv, které už jsou otevřená.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#9](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#9)]
     [!code-vb[Trin_OutlookMailItemTaskPane#9](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#9)]  
  
4.  Nahraďte `ThisAddIn_ShutDown` metoda následujícím kódem. Tento kód odpojí <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> obslužné rutiny události a vyčistí objekty používané doplňku VSTO.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#10](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#10)]
     [!code-vb[Trin_OutlookMailItemTaskPane#10](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#10)]  
  
5.  Přidejte následující <xref:Microsoft.Office.Interop.Outlook.InspectorsEvents_Event.NewInspector> obslužná rutina události `ThisAddIn` třídy. Pokud nový <xref:Microsoft.Office.Interop.Outlook.Inspector> obsahuje e-mailové zprávy, metoda vytvoří instanci novou `InspectorWrapper` objekt, který chcete spravovat vztah mezi e-mailovou zprávu a odpovídající podokna úloh.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#11](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#11)]
     [!code-vb[Trin_OutlookMailItemTaskPane#11](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#11)]  
  
6.  Přidejte následující vlastnosti, která má `ThisAddIn` třídy. Tato vlastnost zpřístupní privátní `inspectorWrappersValue` pole kódu mimo `ThisAddIn` třídy.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#12](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ThisAddIn.cs#12)]
     [!code-vb[Trin_OutlookMailItemTaskPane#12](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ThisAddIn.vb#12)]  
  
## <a name="checkpoint"></a>Kontrolní bod  
 Sestavení projektu zajistit, že se zkompiluje bez chyb.  
  
#### <a name="to-build-your-project"></a>K sestavení projektu  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem myši **OutlookMailItemTaskPane** projektu a pak klikněte na **sestavení**. Ověřte, že projekt zkompiluje bez chyb.  
  
## <a name="synchronizing-the-ribbon-toggle-button-with-the-custom-task-pane"></a>Synchronizace přepínací tlačítko pásu karet s vlastního podokna úloh  
 Přepínací tlačítko se zobrazí na stisknuto, když se zobrazuje podokno úloha a bude zobrazen nesmí být stisknuto při do podokna úloh je skryté. Chcete-li stav tlačítko synchronizovat s vlastního podokna úloh, změňte <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton.Click> obslužné rutiny události přepínací tlačítko.  
  
#### <a name="to-synchronize-the-custom-task-pane-with-the-toggle-button"></a>Synchronizace vlastního podokna úloh s přepínací tlačítko  
  
1.  V Návrháři pásu karet klikněte dvakrát na **zobrazit podokno úloha** přepínací tlačítko.  
  
     Visual Studio automaticky vygeneruje obslužné rutiny události s názvem `toggleButton1_Click`, která zpracovává <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton.Click> událostí přepínací tlačítko. Visual Studio se rovněž otevře **ManageTaskPaneRibbon.cs** nebo **ManageTaskPaneRibbon.vb** souboru v editoru kódu.  
  
2.  Přidejte následující příkazy do horní části **ManageTaskPaneRibbon.cs** nebo **ManageTaskPaneRibbon.vb** souboru.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#14](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ManageTaskPaneRibbon.cs#14)]
     [!code-vb[Trin_OutlookMailItemTaskPane#14](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ManageTaskPaneRibbon.vb#14)]  
  
3.  Nahraďte `toggleButton1_Click` obslužné rutiny události s následujícím kódem. Když uživatel klikne na tlačítko přepnutí, tato metoda skryje nebo zobrazí v podokně vlastní úlohu, která souvisí s aktuální okno Inspector.  
  
     [!code-csharp[Trin_OutlookMailItemTaskPane#15](../vsto/codesnippet/CSharp/Trin_OutlookMailItemTaskPane/ManageTaskPaneRibbon.cs#15)]
     [!code-vb[Trin_OutlookMailItemTaskPane#15](../vsto/codesnippet/VisualBasic/Trin_OutlookMailItemTaskPane/ManageTaskPaneRibbon.vb#15)]  
  
## <a name="testing-the-project"></a>Testování projektu  
 Při spuštění ladění projekt se otevře aplikace Outlook a že je načtený doplňku VSTO. Doplňku VSTO zobrazí jedinečný instanci vlastního podokna úloh s každou e-mailová zpráva, která je otevřená. Vytvořte několik nových e-mailových zpráv k testování kódu.  
  
#### <a name="to-test-the-vsto-add-in"></a>K testování doplňku VSTO  
  
1.  Stiskněte klávesu F5.  
  
2.  V aplikaci Outlook, klikněte na tlačítko **nový** vytvořit novou e-mailová zpráva.  
  
3.  Na pásu karet e-mailové zprávy, klikněte na tlačítko **doplňky** a pak klikněte **zobrazit podokno úloha** tlačítko.  
  
     Ověřte, že podokna úloh s názvem **Moje podokna úloh** se zobrazí s e-mailová zpráva.  
  
4.  V podokně úloh zadejte **první podokna úloh** v textovém poli.  
  
5.  Zavřete podokno úlohy.  
  
     Ověřte, že stav **zobrazit podokno úloha** tlačítko změní tak, aby ho už stisknutí.  
  
6.  Klikněte **zobrazit podokno úloha** tlačítko znovu.  
  
     Ověřte, že do podokna úloh otevře a textového pole stále obsahuje řetězec **první podokna úloh**.  
  
7.  V aplikaci Outlook, klikněte na tlačítko **nový** vytvoření druhého e-mailu.  
  
8.  Na pásu karet e-mailové zprávy, klikněte na tlačítko **doplňky** a pak klikněte **zobrazit podokno úloha** tlačítko.  
  
     Ověřte, že podokna úloh s názvem **Moje podokna úloh** se zobrazí s e-mailovou zprávu a textového pole v tomto podokně úkolu je prázdný.  
  
9. V podokně úloh zadejte **druhý podokna úloh** v textovém poli.  
  
10. Změňte fokus na první e-mailová zpráva.  
  
     Ověřte, že stále zobrazuje v podokně úloh, která souvisí s touto e-mailovou zprávou **první podokna úloh** v textovém poli.  
  
 Doplněk VSTO také zpracovává více pokročilé scénáře, které můžete vyzkoušet. Například můžete otestovat chování při prohlížení e-mailů pomocí **další položky** a **předchozí položce** tlačítka. Můžete také otestovat chování při uvolnění doplňku VSTO, otevřete několik e-mailové zprávy a potom ho znovu načtěte doplňku VSTO.  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o tom, jak vytvořit vlastní podokna úloh z těchto témat:  
  
-   Vytvoření vlastního podokna úloh v doplňku VSTO pro jinou aplikaci. Další informace o aplikacích, které podporují vlastní podokna úloh najdete v tématu [vlastní podokna úloh](../vsto/custom-task-panes.md).  
  
-   Aplikace Microsoft Office automatizovat pomocí vlastního podokna úloh. Další informace najdete v tématu [návod: automatizace aplikace z vlastního podokna úloh](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md).  
  
-   Vytvořte tlačítko pásu karet v aplikaci Excel, který slouží ke skrytí nebo zobrazení vlastního podokna úloh. Další informace najdete v tématu [návod: synchronizace vlastního podokna úloh s tlačítkem pásu karet](../vsto/walkthrough-synchronizing-a-custom-task-pane-with-a-ribbon-button.md).  
  
## <a name="see-also"></a>Viz také  
 [Vlastní podokna úloh](../vsto/custom-task-panes.md)   
 [Postupy: Přidání vlastního podokna úloh do aplikace](../vsto/how-to-add-a-custom-task-pane-to-an-application.md)   
 [Návod: Automatizace aplikace z vlastního podokna úloh](../vsto/walkthrough-automating-an-application-from-a-custom-task-pane.md)   
 [Návod: Synchronizace vlastního podokna úloh s tlačítkem pásu karet](../vsto/walkthrough-synchronizing-a-custom-task-pane-with-a-ribbon-button.md)   
 [Přehled pásu karet](../vsto/ribbon-overview.md)   
 [Přehled modelu objektů aplikace Outlook](../vsto/outlook-object-model-overview.md)   
 [Přístup k pásu karet za běhu](../vsto/accessing-the-ribbon-at-run-time.md)  
  
  