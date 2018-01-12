---
title: "Postupy: aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku | Microsoft Docs"
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
- documents [Office development in Visual Studio], data source updates
- data [Office development in Visual Studio], updating a data source from a document
- host controls [Office development in Visual Studio], data source updates
- Office documents [Office development in Visual Studio, data sources
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 20e0e896389abc48d3f0b08136f06b90748b161d
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-update-a-data-source-with-data-from-a-host-control"></a>Postupy: Aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku
  Můžete vytvořit vazbu ovládacího prvku hostitele ke zdroji dat a aktualizovat zdroj dat se změnami, které jsou vytvářeny pro data v ovládacím prvku. Existují dva hlavní kroky v tomto procesu:  
  
1.  Aktualizace zdroje dat v paměti s použitím změny dat v ovládacím prvku. Obvykle je zdroj dat v paměti <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, nebo jiný datový objekt.  
  
2.  Aktualizace databáze s použitím změněné dat ve zdroji dat v paměti. Tuto možnost lze použít pouze v případě, že zdroj dat je připojen k databázi back-end, jako je databáze systému SQL Server nebo Microsoft Office Access.  
  
 Další informace o hostitelské ovládací prvky a datová vazba najdete v tématu [hostitelských položek a Přehled ovládacích prvků hostitele](../vsto/host-items-and-host-controls-overview.md) a [vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md).  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
## <a name="updating-the-in-memory-data-source"></a>Aktualizace zdroje dat v paměti  
 Ve výchozím nastavení hostitelské ovládací prvky, které umožňují jednoduchá datová vazba (například ovládací prvky obsahu na dokument aplikace Word nebo pojmenovaného rozsahu ovládacího prvku v listu aplikace Excel) bez uložení změn dat do zdroje dat v paměti. To znamená když koncový uživatel změní hodnotu v ovládacím prvku hostitele a poté přejde z ovládacího prvku, nová hodnota v ovládacím prvku automaticky neuloží ke zdroji dat.  
  
 Chcete-li uložit data do zdroje dat, můžete napsat kód, který aktualizuje zdroj dat v reakci na určité události v době běhu nebo můžete konfigurovat řízení se automaticky aktualizovat zdroj dat při změně hodnoty v ovládacím prvku.  
  
 Není potřeba uložit <xref:Microsoft.Office.Tools.Excel.ListObject> změny ke zdroji dat v paměti. Po vytvoření vazby <xref:Microsoft.Office.Tools.Excel.ListObject> řízení k datům, <xref:Microsoft.Office.Tools.Excel.ListObject> řízení automaticky uloží změny do zdroje dat v paměti bez nutnosti další kód.  
  
#### <a name="to-update-the-in-memory-data-source-at-run-time"></a>K aktualizaci zdroje dat v paměti za běhu  
  
-   Volání <xref:System.Windows.Forms.Binding.WriteValue%2A> metodu <xref:System.Windows.Forms.Binding> objekt, který vytváří vazbu ovládacího prvku do zdroje dat.  
  
     Následující příklad uloží změny provedené <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek v listu aplikace Excel ke zdroji dat. Tento příklad předpokládá, že máte <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek s názvem `namedRange1` s jeho <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> vlastnost vázána na pole v datovém zdroji.  
  
     [!code-csharp[Trin_VstcoreDataExcel#1](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#1)]
     [!code-vb[Trin_VstcoreDataExcel#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#1)]  
  
### <a name="automatically-updating-the-in-memory-data-source"></a>Automaticky aktualizaci zdroje dat v paměti  
 Můžete také nakonfigurovat ovládacího prvku tak, aby se automaticky aktualizuje zdroj dat v paměti. V projektech na úrovni dokumentu musíte pomocí kódu nebo návrháře. V projektu doplňku VSTO je nutné použít kód.  
  
##### <a name="to-set-a-control-to-automatically-update-the-in-memory-data-source-by-using-code"></a>O nastavení ovládacího prvku se automaticky aktualizovat zdroj dat v paměti pomocí kódu  
  
1.  Použijte režim System.Windows.Forms.DataSourceUpdateMode.OnPropertyChanged <xref:System.Windows.Forms.Binding> objekt, který vytváří vazbu ovládacího prvku do zdroje dat. Existují dvě možnosti pro aktualizaci zdroje dat:  
  
    -   K aktualizaci zdroje dat po ověření se ovládací prvek, nastavte tuto vlastnost na System.Windows.Forms.DataSourceUpdateMode.OnValidation.  
  
    -   Pokud chcete aktualizovat zdroj dat při změně hodnoty vlastnosti vázané na data ovládacího prvku, nastavte tuto vlastnost na System.Windows.Forms.DataSourceUpdateMode.OnPropertyChanged.  
  
        > [!NOTE]  
        >  System.Windows.Forms.DataSourceUpdateMode.OnPropertyChanged možnost se nevztahuje hostitelské ovládací prvky aplikace Word, protože Word nemá nabídka dokumentu změnit nebo změna řízení oznámení. Tato možnost však lze použít pro ovládací prvky Windows Forms v dokumentech aplikace Word.  
  
     Následující příklad konfiguruje <xref:Microsoft.Office.Tools.Excel.NamedRange> řízení se automaticky aktualizovat zdroj dat při změně hodnoty v ovládacím prvku. Tento příklad předpokládá, že máte <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek s názvem `namedRange1` s jeho <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> vlastnost vázána na pole v datovém zdroji.  
  
     [!code-csharp[Trin_VstcoreDataExcel#19](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#19)]
     [!code-vb[Trin_VstcoreDataExcel#19](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#19)]  
  
##### <a name="to-set-a-control-to-automatically-update-the-in-memory-data-source-by-using-the-designer"></a>O nastavení ovládacího prvku se automaticky aktualizovat zdroj dat v paměti pomocí návrháře  
  
1.  V sadě Visual Studio otevřete dokument aplikace Word nebo sešitu aplikace Excel v návrháři.  
  
2.  Klikněte na ovládací prvek, který chcete automaticky aktualizovat zdroj dat.  
  
3.  V **vlastnosti** okno, rozbalte **(datové vazby)** vlastnost.  
  
4.  Vedle položky **(rozšířené)** vlastnosti, klikněte na tlačítko se třemi tečkami (![VisualStudioEllipsesButton snímek](../vsto/media/vbellipsesbutton.png "VisualStudioEllipsesButton snímek")).  
  
5.  V **formátování a rozšířené vazby** dialogové okno, klikněte **režim aktualizace zdroje dat** rozevíracího seznamu a vyberte jednu z následujících hodnot:  
  
    -   Chcete-li aktualizovat zdroj dat po ověření se ovládací prvek, vyberte **OnValidation**.  
  
    -   Chcete-li aktualizovat zdroj dat při změně hodnoty vlastnosti vázané na data ovládacího prvku, vyberte **OnPropertyChanged –**.  
  
        > [!NOTE]  
        >  **OnPropertyChanged –** možnost se nevztahuje na ovládací prvky aplikace Word hostitele, protože Word nemá nabídka dokumentu změnit nebo změna řízení oznámení. Tato možnost však lze použít pro ovládací prvky Windows Forms v dokumentech aplikace Word.  
  
6.  Zavřít **formátování a rozšířené vazby** dialogové okno.  
  
## <a name="updating-the-database"></a>Aktualizace databáze  
 Pokud zdroj dat v paměti je spojen s databází, je nutné aktualizovat databázi změnami, ke zdroji dat. Další informace o aktualizaci databáze najdete v tématu [uložit data zpět do databáze](../data-tools/save-data-back-to-the-database.md) a [aktualizace dat pomocí TableAdapter](../data-tools/update-data-by-using-a-tableadapter.md) .  
  
#### <a name="to-update-the-database"></a>Postup aktualizace databáze  
  
1.  Volání <xref:System.Windows.Forms.BindingSource.EndEdit%2A> metodu <xref:System.Windows.Forms.BindingSource> pro ovládací prvek.  
  
     <xref:System.Windows.Forms.BindingSource> Se automaticky generuje při přidání ovládacího prvku vázané na data dokumentu nebo sešitu v době návrhu. <xref:System.Windows.Forms.BindingSource> Ovládacího prvku se připojuje k typové datové sady ve vašem projektu. Další informace najdete v tématu [BindingSource – přehled komponenty](/dotnet/framework/winforms/controls/bindingsource-component-overview).  
  
     Následující příklad kódu předpokládá, že váš projekt obsahuje <xref:System.Windows.Forms.BindingSource> s názvem `customersBindingSource`.  
  
     [!code-csharp[Trin_VstcoreDataExcel#20](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#20)]
     [!code-vb[Trin_VstcoreDataExcel#20](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#20)]  
  
2.  Volání `Update` metoda generovaného TableAdapter ve vašem projektu.  
  
     TableAdapter se automaticky generuje při přidání ovládacího prvku vázané na data dokumentu nebo sešitu v době návrhu. TableAdapter typové datové sady ve vašem projektu připojuje k databázi. Další informace najdete v tématu [TableAdapter – přehled](../data-tools/fill-datasets-by-using-tableadapters.md#tableadapter-overview).  
  
     Následující příklad kódu předpokládá mít připojení k tabulce Zákazníci v databázi Northwind, a že projekt obsahuje TableAdapter s názvem `customersTableAdapter` a typové datové sady s názvem `northwindDataSet`.  
  
     [!code-csharp[Trin_VstcoreDataExcel#21](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#21)]
     [!code-vb[Trin_VstcoreDataExcel#21](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#21)]  
  
## <a name="see-also"></a>Viz také  
 [Vazba dat k ovládacím prvkům v řešeních pro systém Office](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Uložit data zpět do databáze](../data-tools/save-data-back-to-the-database.md)    
 [Aktualizace dat pomocí TableAdapter](../data-tools/update-data-by-using-a-tableadapter.md)    
 [Postupy: procházení databázových záznamů na listu](../vsto/how-to-scroll-through-database-records-in-a-worksheet.md)   
 [Postupy: naplnění listů daty z databáze](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)   
 [Postupy: naplnění dokumentů daty z objektů](../vsto/how-to-populate-documents-with-data-from-objects.md)   
 [Postupy: naplnění dokumentů daty z databáze](../vsto/how-to-populate-documents-with-data-from-a-database.md)   
 [Postupy: Naplnění dokumentů daty ze služeb](../vsto/how-to-populate-documents-with-data-from-services.md)  
  
  