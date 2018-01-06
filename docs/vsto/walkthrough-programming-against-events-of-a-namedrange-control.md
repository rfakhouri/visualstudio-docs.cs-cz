---
title: "Návod: Programové ošetření událostí ovládacího prvku NamedRange | Microsoft Docs"
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
- ranges, programming against events
- worksheets, changing cell values
- NamedRange control, events
- worksheets, events
- worksheets, automating
ms.assetid: b69676f9-23b2-4ed6-83ab-8868c3f10948
caps.latest.revision: "57"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 46e83b8450a441eb7bc405c855271e315edb2e3c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-programming-against-events-of-a-namedrange-control"></a>Návod: Programové ošetření událostí ovládacího prvku NamedRange
  Tento návod ukazuje, jak přidat <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku na listu aplikace Microsoft Office Excel a program před jeho události za použití pomocí nástroje pro vývoj pro Office v sadě Visual Studio.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 Během tohoto návodu se dozvíte, jak:  
  
-   Přidat <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku do listu.  
  
-   Program proti <xref:Microsoft.Office.Tools.Excel.NamedRange> řídit události.  
  
-   Testování projektu.  
  
> [!NOTE]  
>  Váš počítač může v následujících pokynech zobrazovat odlišné názvy nebo umístění některých prvků uživatelského rozhraní sady Visual Studio. Tyto prvky jsou určeny edicí sady Visual Studio a použitým nastavením. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)]nebo [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
## <a name="creating-the-project"></a>Vytvoření projektu  
 V tomto kroku vytvoříte projekt sešitu aplikace Excel pomocí sady Visual Studio.  
  
#### <a name="to-create-a-new-project"></a>Chcete-li vytvořit nový projekt  
  
1.  Vytvoření projektu sešitu aplikace Excel s názvem **Moje rozsah událostí s názvem**. Ujistěte se, že **vytvoříte nový textový dokument** je vybrána. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio otevře nové sešitu aplikace Excel v návrháři a přidá **Moje rozsah událostí s názvem** projektu do **Průzkumníku řešení**.  
  
## <a name="adding-text-and-named-ranges-to-the-worksheet"></a>Přidávání textu a pojmenované oblasti na listu  
 Protože hostitelské ovládací prvky jsou rozšířených objektů Office, můžete je přidat do dokumentu stejným způsobem by přidejte nativní objekt. Například můžete přidat aplikace Excel <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku do listu otevřením **vložit** nabídky, přejdete na příkaz **název**a výběr **definovat**. Můžete také přidat <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku tak, že přetáhnete z **sada nástrojů** do listu.  
  
 V tomto kroku přidáte dvou pojmenované oblasti ovládacích prvků na list pomocí **sada nástrojů**a pak přidejte text do listu.  
  
#### <a name="to-add-a-range-to-your-worksheet"></a>Chcete-li přidat rozsah do listu  
  
1.  Ověřte, zda **Moje s názvem rozsah Events.xlsx** je sešit otevřít v návrháři Visual Studio s `Sheet1` zobrazí.  
  
2.  Z **ovládací prvky aplikace Excel** karty z panelu nástrojů, přetáhněte <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku do buňky **A1** v `Sheet1`.  
  
     **Přidat NamedRange – ovládací prvek** zobrazí se dialogové okno.  
  
3.  Ověřte, že **$A 1 USD** se zobrazí v upravitelné textového pole a dané buňky **A1** je vybrána. Pokud není, klikněte na buňku **A1** ji vyberte.  
  
4.  Click **OK**.  
  
     Buňky **A1** stane oblast s názvem `namedRange1`. Není nijak viditelně naznačeno na listu, ale `namedRange1` se zobrazí v **název** pole (umístěný nad listu na levé straně) Pokud buňka **A1** je vybrána.  
  
5.  Přidejte další <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku do buňky **B3**.  
  
6.  Ověřte, že **$B$ 3** se zobrazí v upravitelné textového pole a dané buňky **B3** je vybrána. Pokud není, klikněte na buňku **B3** ji vyberte.  
  
7.  Click **OK**.  
  
     Buňky **B3** stane oblast s názvem `namedRange2`.  
  
#### <a name="to-add-text-to-your-worksheet"></a>Chcete-li přidat text do listu  
  
1.  V buňce **A1**, zadejte následující text:  
  
     **Jedná se o příklad ovládacího prvku NamedRange.**  
  
2.  V buňce **A3** (nalevo od `namedRange2`), zadejte následující text:  
  
     **Události:**  
  
 V následujících částech můžete psát kód, který se vloží text do `namedRange2` a upravit vlastnosti `namedRange2` ovládací prvek v reakci <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeDoubleClick>, <xref:Microsoft.Office.Tools.Excel.NamedRange.Change>, a <xref:Microsoft.Office.Tools.Excel.NamedRange.SelectionChange> události `namedRange1`.  
  
## <a name="adding-code-to-respond-to-the-beforedoubleclick-event"></a>Přidání kódu reagovat na událost BeforeDoubleClick  
  
#### <a name="to-insert-text-into-namedrange2-based-on-the-beforedoubleclick-event"></a>Vložení textu do NamedRange2 založené na události BeforeDoubleClick  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na **Sheet1.vb** nebo **Sheet1.cs** a vyberte **kód zobrazení**.  
  
2.  Přidejte kód, proto `namedRange1_BeforeDoubleClick` obslužné rutiny události vypadá takto:  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#24](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#24)]
     [!code-vb[Trin_VstcoreHostControlsExcel#24](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#24)]  
  
3.  V jazyce C#, musíte přidat obslužné rutiny událostí pojmenovaného rozsahu, jak je znázorněno <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> následující událost. Informace o vytváření obslužných rutin událostí najdete v tématu [postupy: vytvoření obslužné rutiny událostí v projektech Office](../vsto/how-to-create-event-handlers-in-office-projects.md).  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#25](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#25)]  
  
## <a name="adding-code-to-respond-to-the-change-event"></a>Přidání kódu reagovat na událost změny  
  
#### <a name="to-insert-text-into-namedrange2-based-on-the-change-event"></a>Vložení textu do namedRange2 založené na události změny  
  
1.  Přidejte kód, proto `NamedRange1_Change` obslužné rutiny události vypadá takto:  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#26](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#26)]
     [!code-vb[Trin_VstcoreHostControlsExcel#26](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#26)]  
  
    > [!NOTE]  
    >  Protože dvakrát klikněte na buňku v oblasti aplikace Excel vstupuje do režimu úprav <xref:Microsoft.Office.Tools.Excel.NamedRange.Change> události dojde, když na výběr je přesunut mimo rozsah, i v případě, že nedošlo k žádným změnám na text.  
  
## <a name="adding-code-to-respond-to-the-selectionchange-event"></a>Přidání kódu reagovat na SelectionChange – událost  
  
#### <a name="to-insert-text-into-namedrange2-based-on-the-selectionchange-event"></a>Vložení textu do namedRange2 podle SelectionChange – událost  
  
1.  Přidejte kód, proto **NamedRange1_SelectionChange** obslužné rutiny události vypadá takto:  
  
     [!code-csharp[Trin_VstcoreHostControlsExcel#27](../vsto/codesnippet/CSharp/Trin_VstcoreHostControlsExcelCS/Sheet1.cs#27)]
     [!code-vb[Trin_VstcoreHostControlsExcel#27](../vsto/codesnippet/VisualBasic/Trin_VstcoreHostControlsExcelVB/Sheet1.vb#27)]  
  
    > [!NOTE]  
    >  Protože dvakrát klikněte na buňku v oblasti aplikace Excel způsobí, že přesunutí do rozsahu, <xref:Microsoft.Office.Tools.Excel.NamedRange.SelectionChange> události dojde před <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeDoubleClick> dojde k události.  
  
## <a name="testing-the-application"></a>Testování aplikace  
 Nyní můžete otestovat ověření tento text popisu události z vašeho sešitu <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek je vložit do jiného pojmenované oblasti při události jsou vyvolány.  
  
#### <a name="to-test-your-document"></a>K testování dokumentu  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
2.  Umístěte ukazatel myši v `namedRange1`a ověřte, zda text ohledně <xref:Microsoft.Office.Tools.Excel.NamedRange.SelectionChange> událostí je vložen a který komentář je vložen do listu.  
  
3.  Dvakrát klikněte na tlačítko uvnitř `namedRange1`a ověřte, zda text ohledně <xref:Microsoft.Office.Tools.Excel.NamedRange.BeforeDoubleClick> události vložena s červenou text kurzívou v `namedRange2`.  
  
4.  Klikněte na tlačítko mimo `namedRange1` a Všimněte si, že dojde k události změny při ukončení režimu úprav, i když nebyla provedena žádná změna na text.  
  
5.  Změňte text v rámci `namedRange1`.  
  
6.  Klikněte na tlačítko mimo `namedRange1`a ověřte, zda text ohledně <xref:Microsoft.Office.Tools.Excel.NamedRange.Change> vložena událost s modrý text do `namedRange2`.  
  
## <a name="next-steps"></a>Další kroky  
 Tento návod ukazuje základní informace o programování ošetření událostí <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládacího prvku. Zde je úkol, který by mohl pocházet Další:  
  
-   Nasazení projektu. Další informace najdete v tématu [nasazení řešení Office](../vsto/deploying-an-office-solution.md).  
  
## <a name="see-also"></a>Viz také  
 [Přehled ovládacích prvků hostitele a hostitelské položky](../vsto/host-items-and-host-controls-overview.md)   
 [Automatizace aplikace Excel s použitím rozšířených objektů](../vsto/automating-excel-by-using-extended-objects.md)   
 [NamedRange – ovládací prvek](../vsto/namedrange-control.md)   
 [Postupy: Změna velikosti ovládacích prvků NamedRange](../vsto/how-to-resize-namedrange-controls.md)   
 [Postupy: Přidání ovládacích prvků NamedRange do listů](../vsto/how-to-add-namedrange-controls-to-worksheets.md)   
 [Programová omezení hostitelských položek a hostitelských ovládacích prvků](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Postupy: Vytváření obslužných rutin událostí v projektech pro systém Office](../vsto/how-to-create-event-handlers-in-office-projects.md)  
  
  