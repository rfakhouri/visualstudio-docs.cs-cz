---
title: Zachování dynamické ovládacích prvků do dokumentů Office | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office documents [Office development in Visual Studio, Windows Forms controls
- Office documents [Office development in Visual Studio, host controls
- controls [Office development in Visual Studio], persisting in the document
- Windows Forms controls [Office development in Visual Studio], persisting in the document
- documents [Office development in Visual Studio], Windows Forms controls
- documents [Office development in Visual Studio], host controls
- host controls [Office development in Visual Studio], persisting in the document
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 220a6e2c0b7e4633f91e7391448d27dddb5895c8
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="persisting-dynamic-controls-in-office-documents"></a>Uchování dynamických ovládacích prvků v dokumentech systému Office
  Ovládací prvky, které jsou přidány za běhu nejsou trvalé, když je uložit a zavřít tento dokument nebo sešitu. Přesné chování se liší pro hostitele a ovládacích prvků Windows Forms. V obou případech můžete přidat kód pro vaše řešení se znovu vytvořit ovládacích prvků, když uživatel znovu otevře dokument.  
  
 Ovládací prvky, které přidáte do dokumentů za běhu, se nazývají *dynamických ovládacích prvků*. Další informace o dynamických ovládacích prvků najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 [!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]  
  
## <a name="persisting-host-controls-in-the-document"></a>Zachování hostitelské ovládací prvky v dokumentu  
 Pokud dokument je uložit a potom uzavřen, všechny dynamické hostitelské ovládací prvky jsou vyřazeny z dokumentu. Zůstanou pouze základní nativních objektů Office za. Například <xref:Microsoft.Office.Tools.Excel.ListObject> stane hostitelského ovládacího prvku <xref:Microsoft.Office.Interop.Excel.ListObject>. Nativní objektů Office nejsou připojené k události ovládacího prvku hostitele a nemají funkce vazby dat z hostitelského ovládacího prvku.  
  
 Následující tabulka uvádí nativní Office objekt, který je ponecháno v dokumentu pro každý typ hostitelského ovládacího prvku.  
  
|Hostitel – typ ovládacího prvku|Typ objektu nativní Office|  
|-----------------------|-------------------------------|  
|<xref:Microsoft.Office.Tools.Excel.Chart>|<xref:Microsoft.Office.Interop.Excel.Chart>|  
|<xref:Microsoft.Office.Tools.Excel.ListObject>|<xref:Microsoft.Office.Interop.Excel.ListObject>|  
|<xref:Microsoft.Office.Tools.Excel.NamedRange>|<xref:Microsoft.Office.Interop.Excel.Range>|  
|<xref:Microsoft.Office.Tools.Word.Bookmark>|<xref:Microsoft.Office.Interop.Word.Bookmark>|  
|<xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.ContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.DatePickerContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.DropDownListContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.GroupContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.PictureContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.PlainTextContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.RichTextContentControl>|<xref:Microsoft.Office.Interop.Word.ContentControl>|  
  
### <a name="re-creating-dynamic-host-controls-when-documents-are-opened"></a>Když jsou otevřené dokumenty znovu vytvořit dynamické hostitelské ovládací prvky  
 Dynamické hostitelské ovládací prvky místo existující nativní ovládací prvky můžete znovu vytvořit pokaždé, když uživatel otevře dokument. Vytváření ovládacích prvků hostitele tímto způsobem, při otevření dokumentu simuluje prostředí, které uživatelé můžou očekávat.  
  
 Opětovné vytvoření hostitelského ovládacího prvku pro Word, nebo <xref:Microsoft.Office.Tools.Excel.NamedRange> nebo <xref:Microsoft.Office.Tools.Excel.ListObject> hostování ovládacího prvku pro aplikaci Excel, použijte `Add` \< *třídu ovládacího prvku*> metodu <xref:Microsoft.Office.Tools.Excel.ControlCollection> nebo <xref:Microsoft.Office.Tools.Word.ControlCollection> objektu. Použijte metodu, která má parametr pro objekt nativní Office.  
  
 Například, pokud chcete vytvořit <xref:Microsoft.Office.Tools.Excel.ListObject> hostování ovládacího prvku z existující nativní <xref:Microsoft.Office.Interop.Excel.ListObject> při otevření dokumentu, použijte <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddListObject%2A> metoda a předejte jí existující <xref:Microsoft.Office.Interop.Excel.ListObject>. Následující příklad kódu ukazuje to v projektech na úrovni dokumentu pro Excel. Kód znovu vytvoří dynamický <xref:Microsoft.Office.Tools.Excel.ListObject> založený na existujícím <xref:Microsoft.Office.Interop.Excel.ListObject> s názvem `MyListObject` v `Sheet1` třídy.  
  
 [!code-csharp[Trin_ExcelWorkbookDynamicControls#6](../vsto/codesnippet/CSharp/trin_excelworkbookdynamiccontrols4/Sheet1.cs#6)]
 [!code-vb[Trin_ExcelWorkbookDynamicControls#6](../vsto/codesnippet/VisualBasic/trin_excelworkbookdynamiccontrols4/Sheet1.vb#6)]  
  
### <a name="re-creating-charts"></a>Opětovné vytváření grafů  
 Znovu vytvořit <xref:Microsoft.Office.Tools.Excel.Chart> hostování ovládacího prvku, musíte nejprve odstranit nativního <xref:Microsoft.Office.Interop.Excel.Chart>a potom je znovu vytvořit <xref:Microsoft.Office.Tools.Excel.Chart> pomocí <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddChart%2A> nebo <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddChart%2A> metoda. Neexistuje žádné `Add` \< *třídu ovládacího prvku*> metoda, která umožňuje vytvořit nový <xref:Microsoft.Office.Tools.Excel.Chart> na základě existujícího <xref:Microsoft.Office.Interop.Excel.Chart>.  
  
 Pokud nejdříve neodstraníte nativního <xref:Microsoft.Office.Interop.Excel.Chart>, a druhé, duplicitní grafu se vytvoří, když znovu vytvoříte <xref:Microsoft.Office.Tools.Excel.Chart>.  
  
## <a name="persisting-windows-forms-controls-in-documents"></a>Ovládací prvky zachování Windows Forms v dokumentech  
 Když je dokument uložit a potom uzavřen, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] automaticky odstraní všechny ovládací prvky Windows Forms dynamicky vytvořený z dokumentu. Chování se ale liší na úrovni dokumentu a projekty doplňku VSTO.  
  
 V přizpůsobeních na úrovni dokumentu budou odebrány při příštím otevření dokumentu ovládací prvky a jejich základní obálky ActiveX (které budou použity k hostování ovládacích prvků na dokument). Neexistuje žádná informace, které ovládací prvky byly někdy existuje.  
  
 V doplňcích VSTO ovládací prvky jsou odebrány, ale obálky ActiveX zůstanou v dokumentu. Při příštím otevření dokumentu obálky ActiveX jsou viditelné. V aplikaci Excel obálky ActiveX zobrazit obrázky ovládací prvky, jako jsou uvedeny posledním uložení dokumentu. V aplikaci Word obálky ActiveX jsou neviditelná, pokud uživatel klikne na nich, v takovém případě se zobrazí tečkovaná čára, který představuje ohraničení ovládacích prvků. Obálky ActiveX můžete odebrat několika způsoby. Další informace najdete v tématu [odebrání obálky ActiveX v doplňku](#removingActiveX).  
  
### <a name="re-creating-windows-forms-controls-when-documents-are-opened"></a>Opětovné vytvoření Windows Forms – ovládací prvky při otevírání dokumentů  
 Můžete znovu vytvořit odstraněné ovládací prvky Windows Forms, když uživatel znovu otevře dokument. Chcete-li to provést, musí vaše řešení provádět následující úlohy:  
  
1.  Uložení informací o velikosti, umístění a stavu ovládacích prvků, když je dokument uložit nebo uzavřený. V přizpůsobení na úrovni dokumentu můžete uložit tato data do mezipaměti data v dokumentu. V VSTO doplňku můžete tato data uložit na vlastní část XML v dokumentu.  
  
2.  Ovládací prvky v událost, která se vyvolá, když je dokument otevřít znovu vytvořte. V projektech na úrovni dokumentu, můžete k tomu `Sheet` *n* `_Startup` nebo `ThisDocument_Startup` obslužné rutiny událostí. Na projekty doplňku VSTO lze provádět v tomto událostí obslužné rutiny <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookOpen> nebo <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentOpen> události.  
  
###  <a name="removingActiveX"></a> Odebírání obálky ActiveX v doplňku  
 Když přidáte dynamických ovládacích prvků Windows Forms do dokumentů pomocí doplňku VSTO, můžete obálky ActiveX ovládacích prvků zabránit zobrazování v dokumentu, při příštím otevření následujícími způsoby.  
  
#### <a name="removing-activex-wrappers-when-the-document-is-opened"></a>Odebrání ActiveX obálky při otevření dokumentu  
 Pokud chcete odebrat všechny ActiveX obálky, volejte metodu getvstoobject – ke generování položku hostitele pro <xref:Microsoft.Office.Interop.Word.Document> nebo <xref:Microsoft.Office.Interop.Excel.Workbook> představující nově otevřené dokumentu. Například můžete odebrat všechny obálky ActiveX z dokumentu aplikace Word, voláním metody getvstoobject – generování položku hostitele pro <xref:Microsoft.Office.Interop.Word.Document> objekt, který je předán do obslužné rutiny události pro <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentOpen> událostí.  
  
 Tento postup je užitečný, když víte, že, otevřou se jenom na počítače, které mají VSTO doplněk nainstalován. Pokud dokument mohla být předána do jiných uživatelů, kteří nemají VSTO doplněk nainstalován, zvažte odebrání ovládacích prvků před jeho zavřením dokumentu místo toho.  
  
 Následující příklad kódu ukazuje, jak volat metodu getvstoobject – při otevření dokumentu.  
  
 [!code-vb[Trin_WordAddInDynamicControls#11](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#11)]
 [!code-csharp[Trin_WordAddInDynamicControls#11](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#11)]  
  
 I když getvstoobject – metoda slouží především ke generování novou položku hostitele v době běhu, tato metoda také vymaže všechny obálky ActiveX z dokumentu při prvním volání pro konkrétní dokument. Další informace o tom, jak použít metodu getvstoobject – najdete v tématu [rozšíření dokumentů aplikace Word a sešitů aplikace Excel v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).  
  
 Všimněte si, že pokud vaše doplňku VSTO vytvoří dynamických ovládacích prvků při otevření dokumentu, vaše doplňku VSTO již zavolá getvstoobject – metoda jako součást procesu vytváření ovládacích prvků. Není nutné přidat samostatné volání getvstoobject – metoda odebrat obálky ActiveX v tomto scénáři.  
  
#### <a name="removing-the-dynamic-controls-before-the-document-is-closed"></a>Odebrání dynamických ovládacích prvků, než zavření dokumentu  
 Vaše doplňku VSTO můžete explicitně odebrat každý dynamické řízení z dokumentu před zavření dokumentu. Tento postup je užitečný pro dokumenty, které mohla být předána do jiných uživatelů, kteří nemají VSTO doplněk nainstalován.  
  
 Následující příklad kódu ukazuje, jak odebrat všechny ovládací prvky Windows Forms z dokumentu aplikace Word při zavření v dokumentu.  
  
 [!code-vb[Trin_WordAddInDynamicControls#10](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#10)]
 [!code-csharp[Trin_WordAddInDynamicControls#10](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#10)]  
  
## <a name="see-also"></a>Viz také  
 [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)  
  
  