---
title: Vázání dat k ovládacím prvkům v řešeních pro systém Office
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office documents [Office development in Visual Studio], connecting to data
- data, data binding
- data binding
- data binding, Office solutions
- data binding, controls
- Office applications [Office development in Visual Studio], data binding
- controls, data binding
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 540dc1f05ee54bc0a9cb0a9f4965c297aa42e33d
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="bind-data-to-controls-in-office-solutions"></a>Vázání dat k ovládacím prvkům v řešeních pro systém Office
  Můžete vytvořit vazbu ovládacích prvků Windows Forms a *hostování ovládacích prvků* na dokument aplikace Microsoft Office Word nebo sešitu aplikace Microsoft Office Excel ke zdroji dat, data se automaticky zobrazit ovládací prvky. Data můžete vázat na ovládací prvky v projektech na úrovni aplikace i na úrovni dokumentu.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Hostitelské ovládací prvky rozšířit objekty, které jsou v aplikaci Word a Excel objektové modely, jako je například ovládací prvky obsahu v aplikaci Word a pojmenované oblasti v aplikaci Excel. Další informace najdete v tématu [hostitele položky a hostitelem Přehled ovládacích prvků](../vsto/host-items-and-host-controls-overview.md).  
  
 Windows Forms a hostitelských ovládacích prvků Windows Forms model vazby dat, který podporuje obě použít *jednoduché datové vazby* a *rozšířené datové vazby* ke zdrojům dat, jako je například datové sady a data tabulky. Úplné informace o modelu vazby dat v systému Windows Forms najdete v tématu [datové vazby a rozhraní Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms).  
  
 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související Videoukázka, najdete v části [jak využívat I: databázových dat v aplikaci Excel?](http://go.microsoft.com/fwlink/?LinkID=130287).  
  
## <a name="simple-data-binding"></a>Jednoduchá datová vazba  
 Jednoduchá datová vazba existuje, pokud je vlastnost ovládací prvek vázán na jeden datový prvek, jako je například hodnotu v tabulce dat. Například <xref:Microsoft.Office.Tools.Excel.NamedRange> má ovládací prvek <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> vlastnost, která mohou být vázány na pole v datové sadě. Při změně pole v datové sadě, změní se také hodnotu pojmenované oblasti. Všechny hostitele ovládací prvky, s výjimkou <xref:Microsoft.Office.Tools.Word.XMLNodes> řídit, podporu jednoduché datové vazby. <xref:Microsoft.Office.Tools.Word.XMLNodes> Ovládací prvek je kolekce, a proto ho nepodporuje datová vazba.  
  
 Chcete-li provést jednoduché datové vazby k hostitelského ovládacího prvku, přidejte <xref:System.Windows.Forms.Binding> k `DataBindings` vlastností ovládacího prvku. A <xref:System.Windows.Forms.Binding> objekt představuje jednoduchý vazbu mezi hodnotu vlastnosti ovládacího prvku a hodnotu datový prvek.  
  
 Následující příklad ukazuje, jak vytvořit vazbu <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> vlastnost, která má datový prvek v projektech na úrovni dokumentu.  
  
 [!code-vb[Trin_BindableComponent#4](../vsto/codesnippet/VisualBasic/Trin_BindableComponent/Sheet1.vb#4)]
 [!code-csharp[Trin_BindableComponent#4](../vsto/codesnippet/CSharp/Trin_BindableComponent/Sheet1.cs#4)]  
  
 Postupy, které ukazuje jednoduché datové vazby, najdete v části [návod: jednoduché datové vazby v projektech na úrovni dokumentu](../vsto/walkthrough-simple-data-binding-in-a-document-level-project.md) pro projekt na úrovni dokumentu a [návod: jednoduché datové vazby v projektu doplňku VSTO ](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md) projektu doplňku VSTO.  
  
## <a name="complex-data-binding"></a>Komplexní datová vazba  
 Komplexní datová vazba existuje, pokud je vlastnost ovládací prvek vázán na více než jeden element data, jako je více sloupců v tabulce data. <xref:Microsoft.Office.Tools.Excel.ListObject> Řízení pro aplikaci Excel je pouze hostitelského ovládacího prvku, který podporuje rozšířené datové vazby. Existují také mnoho ovládací prvky Windows Forms, které podporují rozšířené datové vazby, jako například <xref:System.Windows.Forms.DataGridView> ovládacího prvku.  
  
 Chcete-li provést rozšířené datové vazby, nastavte `DataSource` vlastnost ovládacího prvku na objekt zdroje dat, který podporuje rozšířené datové vazby. Například <xref:Microsoft.Office.Tools.Excel.ListObject.DataSource%2A> vlastnost <xref:Microsoft.Office.Tools.Excel.ListObject> může být vázán k více sloupců v tabulce data. Všechna data v tabulce dat se zobrazí v <xref:Microsoft.Office.Tools.Excel.ListObject> řízení a jako data v tabulce změny dat, <xref:Microsoft.Office.Tools.Excel.ListObject> také změní. Seznam zdrojů dat, které můžete použít pro komplexní datová vazba najdete v tématu [zdroje dat podporované rozhraním Windows Forms](/dotnet/framework/winforms/data-sources-supported-by-windows-forms).  
  
 Následující příklad kódu vytvoří <xref:System.Data.DataSet> se dvěma <xref:System.Data.DataTable> objekty a naplní jednu z tabulek s daty. Kód pak váže <xref:Microsoft.Office.Tools.Excel.ListObject> do tabulky, který obsahuje data. V tomto příkladu je pro projektu na úrovni dokumentu aplikace Excel.  
  
 [!code-csharp[Trin_ExcelListObject#18](../vsto/codesnippet/CSharp/Trin_ExcelListObject/Trin_ExcelListObject.cs#18)]
 [!code-vb[Trin_ExcelListObject#18](../vsto/codesnippet/VisualBasic/Trin_ExcelListObject/Sheet1.vb#18)]  
  
 Návody, které ukazují rozšířené datové vazby, najdete v části [návod: rozšířené datové vazby v projektech na úrovni dokumentu](../vsto/walkthrough-complex-data-binding-in-a-document-level-project.md) pro projekt na úrovni dokumentu a [návod: rozšířené datové vazby v projektu doplňku VSTO ](../vsto/walkthrough-complex-data-binding-in-vsto-add-in-project.md) projektu doplňku VSTO.  
  
## <a name="display-data-in-documents-and-workbooks"></a>Zobrazení dat v dokumentech a sešitů  
 V projektech na úrovni dokumentu, můžete použít **zdroje dat** okno pro přidání ovládací prvky vázané na data dokumenty nebo sešity snadno, stejným způsobem, můžete ji použít pro Windows Forms. Další informace o používání **zdroje dat** okně najdete v části [vazby Windows Forms – ovládací prvky k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md) a [přidat nové zdroje dat](../data-tools/add-new-data-sources.md).  
  
### <a name="drag-controls-from-the-data-sources-window"></a>Ovládací prvky přetažení z okna zdroje dat  
 Vytvoření ovládacího prvku na dokument při přetažení objektu na ze **zdroje dat** okno. Typ ovládacího prvku, který se vytvoří závisí na tom, jestli jsou vazby jeden sloupec dat nebo dat více sloupců.  
  
 V aplikaci Excel <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek je vytvořen v listu pro každé jednotlivé pole a <xref:Microsoft.Office.Tools.Excel.ListObject> ovládací prvek je vytvořen pro každou oblast dat, která obsahuje více řádků a sloupců. Můžete změnit toto výchozí nastavení tak, že vyberete v tabulce nebo pole v **zdroje dat** okna a pak vyberete různé ovládací prvek z rozevíracího seznamu.  
  
 A <xref:Microsoft.Office.Tools.Word.ContentControl> ovládací prvek přidán do dokumentů. Typ obsahu ovládacího prvku, závisí na datový typ pole, které jste vybrali.  
  
### <a name="bind-data-in-document-level-projects-at-design-time"></a>Vázání dat v projekty na úrovni dokumentu v době návrhu  
 Následující témata ukazují příklady vazba dat v době návrhu:  
  
-   [Postupy: naplnění listů daty z databáze](../vsto/how-to-populate-worksheets-with-data-from-a-database.md)  
  
-   [Postupy: naplnění dokumentů daty z databáze](../vsto/how-to-populate-documents-with-data-from-a-database.md)  
  
-   [Postupy: naplnění dokumentů daty z objektů](../vsto/how-to-populate-documents-with-data-from-objects.md)  
  
-   [Postupy: naplnění dokumentů daty ze služeb](../vsto/how-to-populate-documents-with-data-from-services.md)  
  
-   [Postupy: procházení databázových záznamů na listu](../vsto/how-to-scroll-through-database-records-in-a-worksheet.md)  
  
### <a name="bind-data-in-vsto-add-in-projects"></a>Vytvoření vazby dat ve projekty doplňku VSTO  
 V doplňku VSTO projekty můžete přidat ovládací prvky jenom za běhu. Následující témata ukazují příklady vazba dat za běhu:  
  
-   [Návod: Jednoduché datové vazby v projektu doplňku VSTO](../vsto/walkthrough-simple-data-binding-in-vsto-add-in-project.md)  
  
-   [Návod: Rozšířené datové vazby v projektu doplňku VSTO](../vsto/walkthrough-complex-data-binding-in-vsto-add-in-project.md)  
  
## <a name="update-data-that-is-bound-to-host-controls"></a>Aktualizovat data, která je vázána na hostitelské ovládací prvky  
 Datová vazba mezi zdrojem dat a hostitelského ovládacího prvku zahrnuje obousměrný data aktualizace. V jednoduché datové vazby ve zdroji dat se projeví automaticky v ovládacím prvku hostitele, ale vyžadují explicitní volání aktualizovat zdroj dat změny v ovládacím prvku hostitele. Důvodem je, že v některých případech změny do jednoho pole vázané na data nebyly přijaty. Pokud jsou opatřeny změny v jiné pole vázané na data. Máte například dvě pole, jednu pro stáří a druhou pro let prostředí. Prostředí nesmí překročit stáří. Uživatele nelze aktualizovat stáří z 50 až 25 a potom zkušenost od 30 do 10 Pokud uživatel provede změny ve stejnou dobu. Chcete-li tento problém vyřešit, nebudou aktualizovány pole s jednoduché datové vazby, dokud aktualizace explicitně odesílá kódu.  
  
 Chcete-li aktualizovat zdroj dat z hostitelské ovládací prvky, které umožňují jednoduché datové vazby, je nutné odeslat aktualizace ke zdroji dat v paměti (například <xref:System.Data.DataSet> nebo <xref:System.Data.DataTable>) a k databázi back-end, pokud řešení používá jednu.  
  
 Není potřeba explicitně aktualizovat zdroj dat v paměti, když provádíte pomocí rozšířené datové vazby <xref:Microsoft.Office.Tools.Excel.ListObject> ovládacího prvku. V takovém případě se ke zdroji dat v paměti bez další kód automaticky odešlou změny.  
  
 Další informace najdete v tématu [postup: aktualizace zdroje dat s použitím dat z hostitelského ovládacího prvku](../vsto/how-to-update-a-data-source-with-data-from-a-host-control.md).  
  
## <a name="see-also"></a>Viz také  
 [Jak se I: využívat data databáze v aplikaci Excel?](http://go.microsoft.com/fwlink/?LinkID=130287)   
 [Datová vazba a systém Windows Forms](/dotnet/framework/winforms/data-binding-and-windows-forms)   
 [Postupy: vytvoření jednoduše připojeného ovládacího prvku ve formuláři Windows](/dotnet/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form)   
 [Vytvoření vazby ovládacích prvků Windows Forms k datům v sadě Visual Studio](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)   
 [Uložit data zpět do databáze](../data-tools/save-data-back-to-the-database.md)    
 [Aktualizace dat pomocí TableAdapter](../data-tools/update-data-by-using-a-tableadapter.md)    
 [Data do mezipaměti](../vsto/caching-data.md)   
 [Data v řešeních pro systém Office](../vsto/data-in-office-solutions.md)  
  
  