---
title: Aktualizace projektů Excel a Word, které při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office projects [Office development in Visual Studio], migrating to .NET Framework 4
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 38734366f5b7d19ef0780c8ef998efb19e50a46f
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767527"
---
# <a name="update-excel-and-word-projects-that-you-migrate-to-the-net-framework-4-or-the-net-framework-45"></a>Aktualizace projektů Excel a Word, které při migraci na rozhraní .NET Framework 4 nebo .NET Framework 4.5
  Pokud máte projekt aplikace Excel nebo Word, která používá následující funkce, musíte upravit kódu, pokud cílové rozhraní se změní na [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější:  
  
-   [Getvstoobject – a hasvstoobject – metody](#GetVstoObject)  
  
-   [Vygenerované třídy v projekty na úrovni dokumentu](#generatedclasses)  
  
-   [Ovládací prvky Windows Forms v dokumentech](#winforms)  
  
-   [Události ovládacích prvků obsahu aplikace Word](#ccevents)  
  
-   [Objekt OLE a OLEControl třídy](#ole)  
  
-   [Vlastnost Controls.Item(Object)](#itemproperty)  
  
-   [Kolekce, které jsou odvozeny od CollectionBase](#collections)  
  
 Musíte také odebrat `Microsoft.Office.Tools.Excel.ExcelLocale1033Attribute` a odkazech na `Microsoft.Office.Tools.Excel.ExcelLocale1033Proxy` třídy z projekty aplikace Excel, které jsou změnit cíl na necílené [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější. Visual Studio nedojde k odebrání tohoto atributu nebo odkaz na třídu pro vás.  
  
## <a name="remove-the-excellocale1033-attribute-from-excel-projects"></a>Odeberte atribut ExcelLocale1033 z projekty aplikace Excel  
 `Microsoft.Office.Tools.Excel.ExcelLocale1033Attribute` Byl odebrán z části Visual Studio 2010 Tools for Office runtime, který se používá pro řešení, které cílí [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější. Modul CLR (CLR) v [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] a později vždy předává národního prostředí ID 1033 model objektů aplikace Excel a už tento atribut lze použít pro toto chování zakázat. Další informace najdete v tématu [globalizace a lokalizace řešení pro aplikaci Excel](../vsto/globalization-and-localization-of-excel-solutions.md).  
  
### <a name="to-remove-the-excellocale1033attribute"></a>Chcete-li odebrat ExcelLocale1033Attribute  
  
1.  S projektem otevřeným v sadě Visual Studio, otevřete **Průzkumníku řešení**.  
  
2.  V části **vlastnosti** uzlu (pro jazyk C#) nebo **Můj projekt** uzlu (pro Visual Basic), poklikejte na soubor AssemblyInfo kódu a otevře se v editoru kódu.  
  
    > [!NOTE]  
    >  V projektech Visual Basic, musíte kliknout na **zobrazit všechny soubory** tlačítka na **Průzkumníku řešení** zobrazíte souboru AssemblyInfo kódu.  
  
3.  Vyhledejte `Microsoft.Office.Tools.Excel.ExcelLocale1033Attribute` a ze souboru odebrat nebo ho nastavte jako komentář.  
  
    ```vb  
    <Assembly: ExcelLocale1033Proxy(True)>  
    ```  
  
    ```csharp  
    [assembly: ExcelLocale1033Proxy(true)]  
    ```  
  
## <a name="remove-a-reference-to-the-excellocal1033proxy-class"></a>Odebrat odkaz na ExcelLocal1033Proxy – třída  
 Projekty, které byly vytvořeny pomocí Microsoft Visual Studio 2005 Tools pro systém Microsoft Office doložit aplikace Excel <xref:Microsoft.Office.Interop.Excel.Application> objekt pomocí `Microsoft.Office.Tools.Excel.ExcelLocale1033Proxy` třídy. Tato třída byla odebrána z části Visual Studio 2010 Tools for Office runtime, který byl použit pro řešení cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější. Proto musíte odebrat nebo Zakomentovat řádek kódu, který odkazuje na tato třída.  
  
### <a name="to-remove-the-reference-to-the-excellocal1033proxy-class"></a>Chcete-li odebrat odkaz na ExcelLocal1033Proxy – třída  
  
1.  Otevřete projekt v sadě Visual Studio a pak otevřete **Průzkumníku řešení**.  
  
2.  V **Průzkumníku řešení**, otevřete místní nabídku pro *ThisAddin.cs* (pro jazyk C#) nebo *ThisAddin.vb* (pro Visual Basic) a potom zvolte **kód zobrazení**.  
  
3.  V editoru kódu v `VSTO generated code` oblast, odebrat nebo komentář následující řádek kódu.  
  
    ```vb  
    Me.Application = CType(Microsoft.Office.Tools.Excel.ExcelLocale1033Proxy.Wrap(GetType(Excel.Application), Me.Application), Excel.Application)  
  
    ```  
  
    ```csharp  
    this.Application = (Excel.Application)Microsoft.Office.Tools.Excel.ExcelLocale1033Proxy.Wrap(typeof(Excel.Application), this.Application);  
  
    ```  
  
##  <a name="GetVstoObject"></a> Aktualizujte kód, který používá getvstoobject – a hasvstoobject – metody  
 V projektech cílených pro rozhraní .NET Framework 3.5 `GetVstoObject` nebo `HasVstoObject` metody jsou k dispozici jako rozšiřující metody na jednom z následujících nativních objektů ve vašem projektu: <xref:Microsoft.Office.Interop.Word.Document>, <xref:Microsoft.Office.Interop.Excel.Workbook>, <xref:Microsoft.Office.Interop.Excel.Worksheet>, nebo <xref:Microsoft.Office.Interop.Excel.ListObject>. Při volání těchto metod, není potřeba předání parametru. Následující příklad kódu ukazuje, jak lze pomocí této metody getvstoobject – v Add-in VSTO pro Word, která je cílena na rozhraní .NET Framework 3.5.  
  
```vb  
Dim vstoDocument as Microsoft.Office.Tools.Word.Document = _  
    Globals.ThisAddIn.Application.ActiveDocument.GetVstoObject()  
```  
  
```csharp  
Microsoft.Office.Tools.Word.Document vstoDocument =   
    Globals.ThisAddIn.Application.ActiveDocument.GetVstoObject();  
```  
  
 V projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, musíte upravit kód pro přístup k tyto metody v jednom z následujících způsobů:  
  
-   Tyto metody můžete stále přístup jako rozšiřující metody na <xref:Microsoft.Office.Interop.Word.Document>, <xref:Microsoft.Office.Interop.Excel.Workbook>, <xref:Microsoft.Office.Interop.Excel.Worksheet>, nebo <xref:Microsoft.Office.Interop.Excel.ListObject> objekty. Však musí nyní předat objekt vrácený `Globals.Factory` vlastnosti tak, aby tyto metody.  
  
    ```vb  
    Dim vstoDocument as Microsoft.Office.Tools.Word.Document = _  
        Globals.ThisAddIn.Application.ActiveDocument.GetVstoObject(Globals.Factory)  
    ```  
  
    ```csharp  
    Microsoft.Office.Tools.Word.Document vstoDocument =   
        Globals.ThisAddIn.Application.ActiveDocument.GetVstoObject(Globals.Factory);  
    ```  
  
-   Můžete také přístup k tyto metody u objektu, který je vrácen `Globals.Factory` vlastnost. Při přístupu k tyto metody tímto způsobem, musí projít nativní objekt, který chcete rozšířit metodě.  
  
    ```vb  
    Dim vstoDocument as Microsoft.Office.Tools.Word.Document = _  
        Globals.Factory.GetVstoObject(Globals.ThisAddIn.Application.ActiveDocument)  
    ```  
  
    ```csharp  
    Microsoft.Office.Tools.Word.Document vstoDocument =   
        Globals.Factory.GetVstoObject(Globals.ThisAddIn.Application.ActiveDocument);  
    ```  
  
 Další informace najdete v tématu [dokumentů rozšířit aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
##  <a name="generatedclasses"></a> Aktualizujte kód, který používá instancí generované třídy v projekty na úrovni dokumentu  
 Generované třídy v projektech v projekty na úrovni dokumentu cílených na rozhraní .NET Framework 3.5, jsou odvozeny od následující třídy v [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]:  
  
-   `ThisDocument`: <xref:Microsoft.Office.Tools.Word.Document>  
  
-   `ThisWorkbook`: <xref:Microsoft.Office.Tools.Excel.Workbook>  
  
-   `Sheet` *n*: <xref:Microsoft.Office.Tools.Excel.Worksheet>  
  
-   `Chart` *n*: <xref:Microsoft.Office.Tools.Excel.ChartSheet>  
  
 V projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, že typy v [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] uvedené výše jsou rozhraní, namísto třídy. Generované třídy v projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo později odvozena z následující nové třídy v [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]:  
  
-   `ThisDocument`: <xref:Microsoft.Office.Tools.Word.DocumentBase>  
  
-   `ThisWorkbook`: <xref:Microsoft.Office.Tools.Excel.WorkbookBase>  
  
-   `Sheet` *n*: <xref:Microsoft.Office.Tools.Excel.WorksheetBase>  
  
-   `Chart` *n*: <xref:Microsoft.Office.Tools.Excel.ChartSheetBase>  
  
 Pokud kódu v projektu odkazuje na instanci jednoho z vygenerované třídy jako základní třídu odvozenou od, je třeba upravit kód.  
  
 Například v projektu sešitu aplikace Excel, která je cílena na rozhraní .NET Framework 3.5, můžete mít Pomocná metoda, která provádí některé pracovní instancí vygenerovaného `Sheet` *n* třídy ve vašem projektu.  
  
```vb  
Private Sub DoSomethingToSheet(ByVal worksheet As Microsoft.Office.Tools.Excel.Worksheet)  
    ' Do something to the worksheet object.  
End Sub  
```  
  
```csharp  
private void DoSomethingToSheet(Microsoft.Office.Tools.Excel.Worksheet worksheet)  
{  
    // Do something to the worksheet object.  
}  
```  
  
 Pokud jste změnit cílový projekt, který má [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, je nutné provést jednu z následujících změn kódu:  
  
-   Upravit kód, který volá `DoSomethingToSheet` metoda předat <xref:Microsoft.Office.Tools.Excel.WorksheetBase.Base%2A> vlastnost <xref:Microsoft.Office.Tools.Excel.WorksheetBase> objekt ve vašem projektu. Tato vlastnost vrací <xref:Microsoft.Office.Tools.Excel.Worksheet> objektu.  
  
    ```vb  
    DoSomethingToSheet(Globals.Sheet1.Base)  
    ```  
  
    ```csharp  
    DoSomethingToSheet(Globals.Sheet1.Base);  
    ```  
  
-   Změnit `DoSomethingToSheet` parametru metody očekávat <xref:Microsoft.Office.Tools.Excel.WorksheetBase> objektu místo.  
  
    ```vb  
    Private Sub DoSomethingToSheet(ByVal worksheet As Microsoft.Office.Tools.Excel.WorksheetBase)  
        ' Do something to the worksheet object.  
    End Sub  
    ```  
  
    ```csharp  
    private void DoSomethingToSheet (Microsoft.Office.Tools.Excel.WorksheetBase worksheet)  
    {  
        // Do something to the worksheet object.  
    }  
    ```  
  
##  <a name="winforms"></a> Aktualizujte kód, který používá ovládací prvky Windows Forms v dokumentech  
 Je nutné přidat **pomocí** (C#) nebo **importy** – příkaz (Visual Basic) pro <xref:Microsoft.Office.Tools.Excel> nebo <xref:Microsoft.Office.Tools.Word> oboru názvů do horní části všech souborů kódu, které používá k přidání Windows Forms – ovládací prvky vlastnost ovládací prvky dokumentu nebo listů prostřednictvím kódu programu.  
  
 V projektech cílených na rozhraní .NET Framework 3.5, metody, které přidání ovládacích prvků Windows Forms (například `AddButton` metoda) jsou definovány v <xref:Microsoft.Office.Tools.Excel.ControlCollection> a <xref:Microsoft.Office.Tools.Word.ControlCollection> třídy.  
  
 V projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, jsou tyto metody rozšiřující metody, které jsou k dispozici u vlastnosti ovládacích prvků. Pokud chcete použít tyto metody rozšíření, musíte mít k souboru kódu, ve kterém můžete použít metody **pomocí** nebo **importy** údajů <xref:Microsoft.Office.Tools.Excel> nebo <xref:Microsoft.Office.Tools.Word> oboru názvů. Tento příkaz je generován automaticky v nové projekty, které cílí [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější. Však tento příkaz není automaticky přidá, v projektech cílených na rozhraní .NET Framework 3.5, takže když můžete změnit cílový projekt, musíte jej přidat.  
  
 Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
##  <a name="ccevents"></a> Aktualizovat kód, který zpracovává události ovládacích prvků obsahu aplikace Word  
 V projektech cílených pro rozhraní .NET Framework 3.5, jsou události obsahu ovládací prvky aplikace Word zpracovávány obecná <xref:System.EventHandler%601> delegovat. V projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, jsou tyto události zpracovávány jiné delegáti.  
  
 Následující tabulka uvádí události obsahu ovládacího prvku aplikace Word a delegáti, které jsou spojeny s nimi v projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější.  
  
|Událost|Delegát pro použití v [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] a novější projekty|  
|-----------|---------------------------------------------------------------------------------------------------|  
|<xref:Microsoft.Office.Tools.Word.ContentControlBase.Added>|<xref:Microsoft.Office.Tools.Word.ContentControlAddedEventHandler>|  
|<xref:Microsoft.Office.Tools.Word.ContentControlBase.ContentUpdating>|<xref:Microsoft.Office.Tools.Word.ContentControlContentUpdatingEventHandler>|  
|<xref:Microsoft.Office.Tools.Word.ContentControlBase.Deleting>|<xref:Microsoft.Office.Tools.Word.ContentControlDeletingEventHandler>|  
|<xref:Microsoft.Office.Tools.Word.ContentControlBase.Entering>|<xref:Microsoft.Office.Tools.Word.ContentControlEnteringEventHandler>|  
|<xref:Microsoft.Office.Tools.Word.ContentControlBase.Exiting>|<xref:Microsoft.Office.Tools.Word.ContentControlExitingEventHandler>|  
|<xref:Microsoft.Office.Tools.Word.ContentControlBase.StoreUpdating>|<xref:Microsoft.Office.Tools.Word.ContentControlStoreUpdatingEventHandler>|  
  
##  <a name="ole"></a> Aktualizujte kód, který používá objekt OLE a OLEControl třídy  
 V projektech cílených pro rozhraní .NET Framework 3.5, můžete přidat vlastní ovládací prvky (například uživatelské ovládací prvky Windows Forms) dokumentu nebo listu s použitím `Microsoft.Office.Tools.Excel.OLEObject` a `Microsoft.Office.Tools.Word.OLEControl` třídy.  
  
 V projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, tyto třídy byly nahrazeny <xref:Microsoft.Office.Tools.Excel.ControlSite> a <xref:Microsoft.Office.Tools.Word.ControlSite> rozhraní. Je třeba upravit kód, který odkazuje na `Microsoft.Office.Tools.Excel.OLEObject` a `Microsoft.Office.Tools.Word.OLEControl` místo odkazovat na <xref:Microsoft.Office.Tools.Excel.ControlSite> a <xref:Microsoft.Office.Tools.Word.ControlSite>. Tyto ovládací prvky než nové názvy chovají stejně, jako v projektech cílených pro rozhraní .NET Framework 3.5.  
  
 Další informace najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
##  <a name="itemproperty"></a> Aktualizujte kód, který používá vlastnost Controls.Item(Object)  
 V projektech cílených pro rozhraní .NET Framework 3.5, můžete použít vlastnost Item(Object) Microsoft.Office.Tools.Word.Document.Controls nebo `Microsoft.Office.Tools.Excel.Worksheet.Controls` kolekce k určení, zda je dokument nebo listu obsahuje zadaný prvek.  
  
 V projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, vlastnost Item(Object) byla odebrána z těchto kolekcí. Pokud chcete zjistit, jestli je dokument nebo sešit obsahuje zadaný ovládací prvek, použijte metodu Contains(System.Object) <xref:Microsoft.Office.Tools.Word.Document.Controls%2A> nebo <xref:Microsoft.Office.Tools.Excel.Worksheet.Controls%2A> kolekce místo.  
  
 Další informace o ovládací prvky kolekce dokumentů a listů najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
##  <a name="collections"></a> Aktualizujte kód, který používá kolekce, které jsou odvozeny od CollectionBase  
 V projektech cílených pro rozhraní .NET Framework 3.5, několik kolekci typů v [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] odvozena od <xref:System.Collections.CollectionBase> třídy, jako například `Microsoft.Office.Tools.SmartTagCollection`, `Microsoft.Office.Tools.Excel.ControlCollection`, a `Microsoft.Office.Tools.Word.ControlCollection`.  
  
 V projektech cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější, jsou tyto typy kolekcí teď rozhraní, která není odvozena od <xref:System.Collections.CollectionBase>. Někteří členové již nejsou k dispozici na tyto typy kolekcí, jako například <xref:System.Collections.CollectionBase.Capacity%2A>, <xref:System.Collections.CollectionBase.List%2A>, a <xref:System.Collections.CollectionBase.InnerList%2A>.  
  
## <a name="see-also"></a>Viz také:  
 [Migrace řešení Office na rozhraní .NET Framework 4 nebo novější](../vsto/migrating-office-solutions-to-the-dotnet-framework-4-or-later.md)   
 [Ovládací prvky obsahu](../vsto/content-controls.md)   
 [Rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)   
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)   
 [Globální přístup k objektům v projektech pro systém Office](../vsto/global-access-to-objects-in-office-projects.md)  
  
  