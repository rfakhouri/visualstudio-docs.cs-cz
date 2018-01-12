---
title: "Návod: Přidání ovládacích prvků na list za běhu VSTO doplňku projekt | Microsoft Docs"
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
- add-ins [Office development in Visual Studio], adding controls
- controls [Office development in Visual Studio], adding to worksheets at run time
- application-level add-ins [Office development in Visual Studio], adding controls
- worksheets, adding controls at run time
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: f32db4aa6b547f1555fbccc9cb03c00998169eaa
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-adding-controls-to-a-worksheet-at-run-time-in-vsto-add-in-project"></a>Návod: Přidání ovládacích prvků na list za běhu v projektu doplňku VSTO
  Ovládací prvky můžete přidat do listu všechny otevřené pomocí doplňku VSTO v Excelu. Tento návod ukazuje, jak používat na pásu karet k umožnění uživatelům přidat <xref:Microsoft.Office.Tools.Excel.Controls.Button>, <xref:Microsoft.Office.Tools.Excel.NamedRange>a <xref:Microsoft.Office.Tools.Excel.ListObject> do listu. Informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 **Platí pro:** informace v tomto tématu se vztahují na projekty doplňku VSTO pro Excel. Další informace najdete v tématu [dostupné funkce podle aplikace Office a typu projektu](../vsto/features-available-by-office-application-and-project-type.md).  
  
 Tento návod znázorňuje následující úlohy:  
  
-   Poskytuje uživatelské rozhraní (UI) a přidání ovládacích prvků na list.  
  
-   Přidání ovládacích prvků na list.  
  
-   Odebrání ovládacích prvků z listu.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Požadavky  
 K dokončení tohoto návodu budete potřebovat následující komponenty:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Excel  
  
## <a name="creating-a-new-excel-vsto-add-in-project"></a>Vytvoření nové aplikace Excel VSTO přidejte v projektu  
 Začněte vytvořením projektu doplňku VSTO v Excelu.  
  
#### <a name="to-create-a-new-excel-vsto-add-in-project"></a>K vytvoření nového projektu doplňku VSTO pro Excel  
  
1.  V [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], vytvoření projektu doplňku VSTO pro Excel s názvem **ExcelDynamicControls**. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  Přidat odkaz na **Microsoft.Office.Tools.Excel.v4.0.Utilities.dll** sestavení. Tento odkaz je potřeba prostřednictvím kódu programu Přidání ovládacího prvku Windows Forms do listu dále v tomto návodu.  
  
## <a name="providing-a-ui-to-add-controls-to-a-worksheet"></a>Poskytnutí uživatelského rozhraní k přidávání ovládacích prvků na list  
 Přidáte vlastní karty na pásu karet aplikace Excel. Uživatelé mohou vybrat zaškrtávací políčka na kartě k přidávání ovládacích prvků na list.  
  
#### <a name="to-provide-a-ui-to-add-controls-to-a-worksheet"></a>K poskytování uživatelského rozhraní k přidávání ovládacích prvků na list  
  
1.  Na **projektu** nabídky, klikněte na tlačítko **přidat novou položku**.  
  
2.  V **přidat novou položku** dialogové okno, vyberte **pásu karet (vizuálního návrháře)**a potom klikněte na **přidat**.  
  
     Soubor s názvem **Ribbon1.cs** nebo **Ribbon1.vb** otevře v Návrháři pásu karet a zobrazí výchozí kartě a skupiny.  
  
3.  Z **ovládacích prvků pásu karet Office** kartě **sada nástrojů**, přetáhněte ovládací prvek zaškrtávací políčko do **group1**.  
  
4.  Klikněte na tlačítko **CheckBox1** ji vyberte.  
  
5.  V **vlastnosti** okně změnit následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**Tlačítko**|  
    |**Popisek**|**Tlačítko**|  
  
6.  Přidat druhý zaškrtnutím políčka **group1**a poté změňte následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**NamedRange**|  
    |**Popisek**|**NamedRange**|  
  
7.  Přidat třetí zaškrtnutím políčka **group1**a poté změňte následující vlastnosti.  
  
    |Vlastnost|Hodnota|  
    |--------------|-----------|  
    |**Jméno**|**ListObject**|  
    |**Popisek**|**ListObject**|  
  
## <a name="adding-controls-to-the-worksheet"></a>Přidání ovládacích prvků na list  
 Spravované ovládací prvky můžete přidat jenom do hostitelské položky, které fungují jako kontejnery. Protože projekty doplňku VSTO pracovat s žádné otevřeného sešitu, doplňku VSTO převede hostitelská položka sešitu nebo získá stávající položku hostitele, před přidáním ovládacího prvku. Přidání kódu do obslužné rutiny událostí kliknutím na každého ovládacího prvku k vygenerování <xref:Microsoft.Office.Tools.Excel.Worksheet> položky hostitele, který je založen na otevřete list. Potom přidat <xref:Microsoft.Office.Tools.Excel.Controls.Button>, <xref:Microsoft.Office.Tools.Excel.NamedRange>a <xref:Microsoft.Office.Tools.Excel.ListObject> na aktuální výběr v listu.  
  
#### <a name="to-add-controls-to-a-worksheet"></a>K přidávání ovládacích prvků na list  
  
1.  V Návrháři pásu karet klikněte dvakrát na **tlačítko**.  
  
     <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox.Click> Obslužnou rutinu události **tlačítko** políčko otevře v editoru kódu.  
  
2.  Nahraďte `Button_Click` obslužné rutiny události s následujícím kódem.  
  
     Tento kód používá `GetVstoObject` metoda získat položku hostitele, který představuje první listu v sešitu a pak přidá <xref:Microsoft.Office.Tools.Excel.Controls.Button> ovládací prvek pro aktuálně vybrané buňky.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#2](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/Ribbon1.cs#2)]
     [!code-vb[Trin_Excel_Dynamic_Controls#2](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/Ribbon1.vb#2)]  
  
3.  V **Průzkumníku**, vyberte Ribbon1.cs nebo Ribbon1.vb.  
  
4.  Na **zobrazení** nabídky, klikněte na tlačítko **Návrhář**.  
  
5.  V Návrháři pásu karet klikněte dvakrát na **NamedRange**.  
  
6.  Nahraďte `NamedRange_Click` obslužné rutiny události s následujícím kódem.  
  
     Tento kód používá `GetVstoObject` metoda získat položku hostitele, který představuje první listu v sešitu a pak definuje <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení pro aktuálně vybrané buňky nebo buněk.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#3](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/Ribbon1.cs#3)]
     [!code-vb[Trin_Excel_Dynamic_Controls#3](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/Ribbon1.vb#3)]  
  
7.  V Návrháři pásu karet klikněte dvakrát na **ListObject**.  
  
8.  Nahraďte `ListObject_Click` obslužné rutiny události s následujícím kódem.  
  
     Tento kód používá `GetVstoObject` metoda získat položku hostitele, který představuje první listu v sešitu a pak definuje <xref:Microsoft.Office.Tools.Excel.ListObject> pro aktuálně vybrané buňky nebo buňky.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#4](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/Ribbon1.cs#4)]
     [!code-vb[Trin_Excel_Dynamic_Controls#4](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/Ribbon1.vb#4)]  
  
9. Přidejte následující příkazy na začátek souboru kódu pásu karet.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#1](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/Ribbon1.cs#1)]
     [!code-vb[Trin_Excel_Dynamic_Controls#1](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/Ribbon1.vb#1)]  
  
## <a name="removing-controls-from-the-worksheet"></a>Odebrání ovládacích prvků z listu  
 Ovládací prvky nejsou trvalé při listu je uložit a zavřít. Prostřednictvím kódu programu byste měli odebrat všechny vygenerované ovládací prvky Windows Forms dřív, než je uložen na listu, nebo pouze Přehled ovládacího prvku se zobrazí, když je sešit otevřít znovu. Přidejte kód, který <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookBeforeSave> událost, která odebere ovládací prvky Windows Forms z kolekce ovládacích prvků položky generované hostitele. Další informace najdete v tématu [uchování dynamických ovládacích prvků v dokumentech Office](../vsto/persisting-dynamic-controls-in-office-documents.md).  
  
#### <a name="to-remove-controls-from-the-worksheet"></a>Chcete-li odebrat z listu ovládací prvky  
  
1.  V **Průzkumníku**, vyberte ThisAddIn.cs nebo ThisAddIn.vb.  
  
2.  Na **zobrazení** nabídky, klikněte na tlačítko **kód**.  
  
3.  Přidejte následující metodu do třídy ThisAddIn. Tento kód získá první listu v sešitu a pak použije `HasVstoObject` metody zkontrolujte, zda má list objekt generovaného listu. Pokud má objekt generovaného listu ovládací prvky, kód získá tento list objekt a provádí iteraci v kolekci řízení odebrání ovládacích prvků.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#6](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#6)]
     [!code-vb[Trin_Excel_Dynamic_Controls#6](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#6)]  
  
4.  V jazyce C#, musíte vytvořit obslužnou rutinu události pro <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookBeforeSave> událostí. Tento kód můžete umístit `ThisAddIn_Startup` metoda. Další informace o vytváření obslužných rutin událostí najdete v tématu [postupy: vytvoření obslužné rutiny událostí v projektech Office](../vsto/how-to-create-event-handlers-in-office-projects.md). Nahraďte `ThisAddIn_Startup` metoda následujícím kódem.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#5](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#5)]  
  
## <a name="testing-the-solution"></a>Testování řešení  
 Přidání ovládacích prvků na list jejich výběrem ze vlastní karty na pásu karet. Pokud list uložíte, budou odebrány tyto ovládací prvky.  
  
#### <a name="to-test-the-solution"></a>Testovat řešení.  
  
1.  Stisknutím klávesy F5 spusťte projekt.  
  
2.  Vyberte libovolnou buňku ve Sheet1.  
  
3.  Klikněte **doplňky** kartě.  
  
4.  V **group1** klikněte na možnost **tlačítko**.  
  
     Tlačítko se zobrazí ve vybrané buňky.  
  
5.  V Sheet1 vyberte jinou buňku.  
  
6.  V **group1** klikněte na možnost **NamedRange**.  
  
     Pojmenované oblasti je definována pro vybrané buňky.  
  
7.  Vyberte řady buněk v Sheet1.  
  
8.  V **group1** klikněte na možnost **ListObject**.  
  
     Přidá objekt seznamu se pro vybrané buňky.  
  
9. Uložte listu.  
  
     Ovládací prvky, které jste přidali do Sheet1 už nebude zobrazovat.  
  
## <a name="next-steps"></a>Další kroky  
 Další informace o ovládacích prvcích v projekty doplňku VSTO v Excelu z tohoto tématu:  
  
-   Další informace o tom, jak uložit ovládacích prvků na list, najdete v části aplikaci Excel VSTO Add-in dynamické ovládací prvky ukázku najdete na adrese [Office Ukázky a návody vývoje](../vsto/office-development-samples-and-walkthroughs.md).  
  
## <a name="see-also"></a>Viz také  
 [Řešení pro aplikaci Excel](../vsto/excel-solutions.md)   
 [Windows Forms – ovládací prvky na přehled dokumenty sady Office](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Ovládací prvky v dokumentech Office](../vsto/controls-on-office-documents.md)   
 [NamedRange – ovládací prvek](../vsto/namedrange-control.md)   
 [ListObject – ovládací prvek](../vsto/listobject-control.md)  
  
  