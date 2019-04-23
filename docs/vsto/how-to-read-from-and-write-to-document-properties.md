---
title: 'Postupy: Čtení a zápis do vlastnosti dokumentu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Word [Office development in Visual Studio], document properties
- documents [Office development in Visual Studio], properties
- document properties [Office development in Visual Studio]
- Excel [Office development in Visual Studio], document properties
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ac0d81c9e42a5c3aa22a09d59f346e6127b1284f
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60115767"
---
# <a name="how-to-read-from-and-write-to-document-properties"></a>Postupy: Čtení a zápis do vlastnosti dokumentu
  Můžete uložit vlastnosti dokumentu společně s dokumentem. Aplikace Office poskytují celou řadou integrované vlastnosti, jako je například autor, název a předmět. Toto téma ukazuje, jak nastavit vlastnosti dokumentu v aplikaci Microsoft Office Excel a Microsoft Office Word.

 ![odkaz na video](../vsto/media/playvideo.gif "odkaz na video") související video ukázku naleznete v tématu [postup: Přístup k a manipulaci s vlastní vlastnosti dokumentu v aplikaci Microsoft Word? ](http://go.microsoft.com/fwlink/?LinkId=136772).

 [!INCLUDE[appliesto_docprops](../vsto/includes/appliesto-docprops-md.md)]

## <a name="set-document-properties-in-excel"></a>Nastavení vlastností dokumentu v aplikaci Excel
 Pro práci s předdefinované vlastnosti v aplikaci Excel, použijte následující vlastnosti:

- V projektu úrovni dokumentu pomocí <xref:Microsoft.Office.Tools.Excel.Workbook.BuiltinDocumentProperties%2A> vlastnost `ThisWorkbook` třídy.

- V projektu doplňku VSTO, použijte <xref:Microsoft.Office.Interop.Excel._Workbook.BuiltinDocumentProperties%2A> vlastnost <xref:Microsoft.Office.Interop.Excel.Workbook> objektu.

  Tyto vlastnosti vrátit <xref:Microsoft.Office.Core.DocumentProperties> objekt, což je kolekce z <xref:Microsoft.Office.Core.DocumentProperty> objekty. Můžete použít `Item` vlastnost kolekce, kterou chcete načíst určité vlastnosti, podle názvu nebo podle indexu v rámci kolekce.

  Následující příklad kódu ukazuje, jak změnit předdefinované **číslo revize** vlastnost v projektu úrovni dokumentu.

### <a name="to-change-the-revision-number-property-in-excel"></a>Chcete-li změnit vlastnost číslo revize v aplikaci Excel

1. Proměnné můžete přiřadíte předdefinované vlastnosti.

     [!code-vb[Trin_VstcoreProgramming#7](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/ThisWorkbook.vb#7)]
     [!code-csharp[Trin_VstcoreProgramming#7](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingExcelCS/ThisWorkbook.cs#7)]

2. Přírůstek `Revision Number` vlastností o jednu.

     [!code-vb[Trin_VstcoreProgramming#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingExcelVB/ThisWorkbook.vb#8)]
     [!code-csharp[Trin_VstcoreProgramming#8](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingExcelCS/ThisWorkbook.cs#8)]

## <a name="set-document-properties-in-word"></a>Nastavit vlastnosti dokumentu ve Wordu
 Chcete-li pracovat předdefinované vlastnosti v aplikaci Word, použijte následující vlastnosti:

- V projektu úrovni dokumentu pomocí <xref:Microsoft.Office.Tools.Word.Document.BuiltInDocumentProperties%2A> vlastnost `ThisDocument` třídy.

- V projektu doplňku VSTO, použijte <xref:Microsoft.Office.Interop.Word._Document.BuiltInDocumentProperties%2A> vlastnost <xref:Microsoft.Office.Interop.Word.Document> objektu.

  Tyto vlastnosti vrátit <xref:Microsoft.Office.Core.DocumentProperties> objekt, což je kolekce z <xref:Microsoft.Office.Core.DocumentProperty> objekty. Můžete použít `Item` vlastnost kolekce, kterou chcete načíst určité vlastnosti, podle názvu nebo podle indexu v rámci kolekce.

  Následující příklad kódu ukazuje, jak změnit předdefinované **subjektu** vlastnost v projektu úrovni dokumentu.

### <a name="to-change-the-subject-property"></a>Chcete-li změnit vlastnost předmětu

1. Proměnné můžete přiřadíte předdefinované vlastnosti.

     [!code-csharp[Trin_VstcoreProgrammingWord#1](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingWordCS/ThisDocument.cs#1)]
     [!code-vb[Trin_VstcoreProgrammingWord#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingWordVB/ThisDocument.vb#1)]

2. Změnit `Subject` nastavte na dokument White Paper "o".

     [!code-csharp[Trin_VstcoreProgrammingWord#2](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingWordCS/ThisDocument.cs#2)]
     [!code-vb[Trin_VstcoreProgrammingWord#2](../vsto/codesnippet/VisualBasic/Trin_VstcoreProgrammingWordVB/ThisDocument.vb#2)]

## <a name="robust-programming"></a>Robustní programování
 V příkladech se předpokládá, že jste napsali kód `ThisWorkbook` třídy v projektu úrovni dokumentu pro Excel a `ThisDocument` třídy v projektu úrovni dokumentu pro aplikaci Word.

 I když pracujete s aplikací Word a Excel a objekty, které, Microsoft Office poskytuje seznam vlastností dostupných předdefinovaných dokumentu. Pokus o přístup k nedefinovanou vlastnost vyvolá výjimku.

## <a name="see-also"></a>Viz také:
- [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)
- [Programování přizpůsobení na úrovni dokumentu](../vsto/programming-document-level-customizations.md)
- [Postupy: Vytvoření a změny přizpůsobených vlastností dokumentu](../vsto/how-to-create-and-modify-custom-document-properties.md)
