---
title: Uchování dynamických ovládacích prvků v dokumentech Office
ms.date: 02/02/2017
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
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 8fd44d535cd8a9920ebc3de37d0c483a19dac8f8
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60117977"
---
# <a name="persist-dynamic-controls-in-office-documents"></a>Uchování dynamických ovládacích prvků v dokumentech Office

Ovládací prvky, které jsou přidány za běhu nejsou zachované při dokumentem nebo sešitem, je uložit a zavřít. Přesné chování se liší pro hostitelské ovládací prvky a ovládací prvky Windows Forms. V obou případech můžete přidat kód do svého řešení k opětovnému vytvoření ovládacích prvků, když uživatel otevře dokument.

Ovládací prvky, které přidáte do dokumentů za běhu se nazývají *dynamické ovládací prvky*. Další informace o dynamické ovládací prvky najdete v tématu [přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md).

[!INCLUDE[appliesto_controls](../vsto/includes/appliesto-controls-md.md)]

## <a name="persist-host-controls-in-the-document"></a>Zachovat hostitelské ovládací prvky v dokumentu

Po uložení a pak zavření dokumentu, odeberou se všechny dynamické hostitelské ovládací prvky z dokumentu. Zůstat pouze základní nativních objektů Office za. Například <xref:Microsoft.Office.Tools.Excel.ListObject?displayProperty=fullName> hostitelského ovládacího prvku se stane <xref:Microsoft.Office.Interop.Excel.ListObject?displayProperty=fullName>. Nativní objekty Office nejsou připojené k hostiteli události ovládacích prvků a nemají funkce vazby dat z hostitelského ovládacího prvku.

Následující tabulka uvádí nativní objekt Office, který se zachovají v dokumentu pro každý typ hostitelského ovládacího prvku.

|Hostitel – typ ovládacího prvku|Nativní typ objektu sady Office|
|-----------------------|-------------------------------|
|<xref:Microsoft.Office.Tools.Excel.Chart>|<xref:Microsoft.Office.Interop.Excel.Chart>|
|<xref:Microsoft.Office.Tools.Excel.ListObject>|<xref:Microsoft.Office.Interop.Excel.ListObject>|
|<xref:Microsoft.Office.Tools.Excel.NamedRange>|<xref:Microsoft.Office.Interop.Excel.Range>|
|<xref:Microsoft.Office.Tools.Word.Bookmark>|<xref:Microsoft.Office.Interop.Word.Bookmark>|
|<xref:Microsoft.Office.Tools.Word.BuildingBlockGalleryContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.ComboBoxContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.ContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.DatePickerContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.DropDownListContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.GroupContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.PictureContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.PlainTextContentControl><br /><br /> <xref:Microsoft.Office.Tools.Word.RichTextContentControl>|<xref:Microsoft.Office.Interop.Word.ContentControl>|

### <a name="re-create-dynamic-host-controls-when-documents-are-opened"></a>Znovu vytvořit dynamické hostitelské ovládací prvky, když jsou otevřené dokumenty

Pokaždé, když uživatel otevře dokument můžete znovu vytvořit dynamické hostitelské ovládací prvky místo stávající nativní ovládací prvky. Vytvoření hostitelské ovládací prvky tímto způsobem, při otevření dokumentu simuluje prostředí, které můžou uživatelé očekávají.

Chcete znovu vytvořit hostitelský ovládací prvek pro aplikaci Word, nebo <xref:Microsoft.Office.Tools.Excel.NamedRange> nebo <xref:Microsoft.Office.Tools.Excel.ListObject> hostování ovládacího prvku pro Excel, použijte `Add` \< *třídu ovládacího prvku*> metodu <xref:Microsoft.Office.Tools.Excel.ControlCollection?displayProperty=fullName> nebo <xref:Microsoft.Office.Tools.Word.ControlCollection?displayProperty=fullName> objektu. Použijte metodu, která má parametr pro nativní objekt Office.

Například, pokud chcete vytvořit <xref:Microsoft.Office.Tools.Excel.ListObject?displayProperty=fullName> hostování ovládacího prvku z existujících nativního <xref:Microsoft.Office.Interop.Excel.ListObject?displayProperty=fullName> při otevření dokumentu, použijte <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddListObject%2A> a předáte v existujícím <xref:Microsoft.Office.Interop.Excel.ListObject>. Následující příklad kódu ukazuje to v projektu úrovni dokumentu pro Excel. Kód znovu vytvoří dynamické <xref:Microsoft.Office.Tools.Excel.ListObject> , který je založen na existujícím <xref:Microsoft.Office.Interop.Excel.ListObject> s názvem `MyListObject` v `Sheet1` třídy.

[!code-csharp[Trin_ExcelWorkbookDynamicControls#6](../vsto/codesnippet/CSharp/trin_excelworkbookdynamiccontrols4/Sheet1.cs#6)]
[!code-vb[Trin_ExcelWorkbookDynamicControls#6](../vsto/codesnippet/VisualBasic/trin_excelworkbookdynamiccontrols4/Sheet1.vb#6)]

### <a name="re-create-chart"></a>Znovu vytvořte graf

K opětovnému vytvoření <xref:Microsoft.Office.Tools.Excel.Chart?displayProperty=fullName> hostování ovládacího prvku, musíte nejprve odstranit nativní <xref:Microsoft.Office.Interop.Excel.Chart?displayProperty=fullName>a potom ho znovu vytvořit <xref:Microsoft.Office.Tools.Excel.Chart?displayProperty=fullName> pomocí <xref:Microsoft.Office.Tools.Excel.ControlCollection.AddChart%2A> – metoda. Neexistuje žádná `Add` \< *třídu ovládacího prvku*> metodu, která vám umožní vytvořit nový <xref:Microsoft.Office.Tools.Excel.Chart?displayProperty=fullName> založené na existujícím <xref:Microsoft.Office.Interop.Excel.Chart?displayProperty=fullName>.

Pokud nejdříve neodstraníte nativní <xref:Microsoft.Office.Interop.Excel.Chart>, pak vytvoříte druhý, duplicitní grafu, když znovu vytvoříte <xref:Microsoft.Office.Tools.Excel.Chart?displayProperty=fullName>.

## <a name="persist-windows-forms-controls-in-documents"></a>Zachovat ovládacích prvků Windows Forms v dokumentech

Po uložení a pak zavření dokumentu [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] automaticky odstraní všechny ovládací prvky Windows Forms dynamicky generovaný z dokumentu. Chování je však liší na úrovni dokumentu a projekty doplňku VSTO.

V přizpůsobeních na úrovni dokumentu jsou odebrány ovládací prvky a jejich podkladové obálky ActiveX (které se používají k hostování ovládacích prvků na dokumentu) při příštím otevření dokumentu. Neexistuje žádné označení, které ovládací prvky byly stále existuje.

V doplňcích VSTO jsou odebrány ovládací prvky, ale zůstávají obálky ActiveX v dokumentu. Při příštím otevření dokumentu, obálky ActiveX jsou viditelné. V aplikaci Excel obálky ActiveX zobrazit obrázky ovládacích prvků, jak jsou uvedeny při posledním uložení dokumentu. V aplikaci Word obálky ActiveX nejsou viditelná, pokud uživatel klikne na nich, v takovém případě se zobrazí tečkovaná čára, která představuje ohraničení ovládacích prvků. Existuje několik způsobů, jak můžete odebrat obálky ActiveX. Další informace najdete v tématu [odebrat obálky ActiveX v doplňku](#removingActiveX).

### <a name="re-create-windows-forms-controls-when-documents-are-opened"></a>Znovu vytvořte ovládací prvky Windows Forms, když jsou otevřené dokumenty

Můžete znovu vytvořit odstraněný ovládacích prvků Windows Forms, když uživatel otevře dokument. Chcete-li to provést, musí vaše řešení provádět následující úlohy:

1. Informace o velikost, umístění a stav ovládacích prvků Store, když je dokument uložen nebo uzavřený. V přizpůsobení na úrovni dokumentu můžete uložit data do datové mezipaměti v dokumentu. VSTO Add-in můžete data uložit na vlastní část XML v dokumentu.

2. Vytvořte ovládací prvky na událost, která se vyvolá, když je dokument otevřít znovu. V projektech na úrovni dokumentu, musíte `Sheet` *n* `_Startup` nebo `ThisDocument_Startup` obslužných rutin událostí. V doplňku VSTO projekty můžete dělat v tomto události obslužné rutiny <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookOpen> nebo <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentOpen> události.

### <a name="removingActiveX"></a> Odebrat obálky ActiveX v doplňku

Při přidání dynamických ovládacích prvků Windows Forms do dokumentů s použitím doplňku VSTO je lze zabránit obálky ActiveX pro ovládací prvky v dokumentu při příštím otevření následujícími způsoby.

#### <a name="remove-activex-wrappers-when-the-document-is-opened"></a>Odstranit obálky ActiveX, je-li dokument otevřít

Chcete-li odebrat všechny ActiveX obálky, zavolejte `GetVstoObject` metoda ke generování určitou položku hostitele <xref:Microsoft.Office.Interop.Word.Document> nebo <xref:Microsoft.Office.Interop.Excel.Workbook> , která představuje nově otevřeném dokumentu. Pokud chcete odebrat všechny ActiveX obálky z Wordového dokumentu, například můžete volat `GetVstoObject` metoda ke generování určitou položku hostitele <xref:Microsoft.Office.Interop.Word.Document> objektu, který je předán do obslužné rutiny události pro <xref:Microsoft.Office.Interop.Word.ApplicationEvents4_Event.DocumentOpen> událostí.

Tento postup je užitečný, když víte, že se dokument otevřít pouze v počítačích, které mají doplňku VSTO nainstalované. Pokud dokument mohla být předána ostatním uživatelům, kteří nemají doplňku VSTO nainstalované, zvažte odebrání ovládacích prvků před zavřením dokumentu místo toho.

Následující příklad kódu ukazuje, jak volat `GetVstoObject` metoda při otevření dokumentu.

[!code-vb[Trin_WordAddInDynamicControls#11](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#11)]
[!code-csharp[Trin_WordAddInDynamicControls#11](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#11)]

I když `GetVstoObject` metoda slouží především ke generování novou položku hostitele v době běhu, tato metoda také odstraní všechny ActiveX obálky z dokumentu první přihlášení je volána pro určitého dokumentu. Další informace o tom, jak používat `GetVstoObject` metodu, najdete v článku [rozšíření Wordových dokumentů a Excelových sešitů v doplňcích VSTO za běhu](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md).

Pokud váš doplněk VSTO vytvoří dynamické ovládací prvky při otevření dokumentu, doplňku VSTO již zavolá `GetVstoObject` metoda jako součást procesu vytváření ovládacích prvků. Není potřeba přidat samostatné volání `GetVstoObject` metoda odebrání obálky ActiveX v tomto scénáři.

#### <a name="remove-the-dynamic-controls-before-the-document-is-closed"></a>Odebrat dynamické ovládací prvky před zavřením dokumentu

Doplňku VSTO můžete explicitně každý dynamický ovládací prvek z dokumentu odstranit před zavřením dokumentu. Tento postup je užitečný pro dokumenty, které může být předána ostatním uživatelům, kteří nemají doplňku VSTO nainstalované.

Následující příklad kódu ukazuje, jak při zavření dokumentu z Wordového dokumentu odebrat všechny ovládací prvky Windows Forms.

[!code-vb[Trin_WordAddInDynamicControls#10](../vsto/codesnippet/VisualBasic/trin_wordaddindynamiccontrols/ThisAddIn.vb#10)]
[!code-csharp[Trin_WordAddInDynamicControls#10](../vsto/codesnippet/CSharp/Trin_WordAddInDynamicControls/ThisAddIn.cs#10)]

## <a name="see-also"></a>Viz také:

- [Přidání ovládacích prvků do dokumentů Office za běhu](../vsto/adding-controls-to-office-documents-at-run-time.md)
