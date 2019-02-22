---
title: 'Postupy: Data v mezipaměti v dokumentu chráněném heslem'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data caching [Office development in Visual Studio], protected documents
- datasets [Office development in Visual Studio], caching
- data [Office development in Visual Studio], caching
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 5f6e9bea3d45249d847f2dccfe522f832d6a07b5
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56644520"
---
# <a name="how-to-cache-data-in-a-password-protected-document"></a>Postupy: Data v mezipaměti v dokumentu chráněném heslem
  Pokud chcete přidat data do datové mezipaměti v dokumentu nebo sešitu, který je chráněný heslem, změny dat v mezipaměti nejsou uloženy automaticky. Změny můžete uložit do data uložená v mezipaměti tak, že přepíšete dvě metody ve vašem projektu.

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

## <a name="caching-in-word-documents"></a>Ukládání do mezipaměti v dokumentech aplikace Word

### <a name="to-cache-data-in-a-word-document-that-is-protected-with-a-password"></a>Ukládání dat do mezipaměti ve Wordovém dokumentu, který je chráněný heslem

1.  V `ThisDocument` třídy, označte veřejné pole nebo vlastnost ukládat do mezipaměti. Další informace najdete v tématu [ukládat data do mezipaměti](../vsto/caching-data.md).

2.  Přepsat <xref:Microsoft.Office.Tools.Word.DocumentBase.UnprotectDocument%2A> metodu `ThisDocument` třídy a odebrat ochranu z dokumentu.

     Když je dokument uložen, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] volá tuto metodu za účelem vám poskytnou příležitost k odemknutí dokumentu. To umožňuje uložení změn dat v mezipaměti.

3.  Přepsat <xref:Microsoft.Office.Tools.Word.DocumentBase.ProtectDocument%2A> metodu `ThisDocument` třídy a znovu nastavit ochranu dokumentu.

     Po uložení dokumentu [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] volá tuto metodu za účelem vám poskytnou příležitost k opětovnému použití ochrany v dokumentu.

### <a name="example"></a>Příklad
 Následující příklad kódu ukazuje, jak do mezipaměti ukládat data ve Wordovém dokumentu, který je chráněný heslem. Předtím, než kód odebere ochranu v <xref:Microsoft.Office.Tools.Word.DocumentBase.UnprotectDocument%2A> metoda, uloží aktuální <xref:Microsoft.Office.Tools.Word.Document.ProtectionType%2A> hodnoty tak, aby se stejný typ ochrany může být znovu použita v <xref:Microsoft.Office.Tools.Word.DocumentBase.ProtectDocument%2A> metody.

 [!code-csharp[Trin_CachedDataProtectedDocument#1](../vsto/codesnippet/CSharp/Trin_CachedDataProtectedDocument/ThisDocument.cs#1)]
 [!code-vb[Trin_CachedDataProtectedDocument#1](../vsto/codesnippet/VisualBasic/Trin_CachedDataProtectedDocument/ThisDocument.vb#1)]

### <a name="compile-the-code"></a>Kompilace kódu
 Přidejte tento kód `ThisDocument` třídu ve vašem projektu. Tento kód předpokládá, že heslo je uloženo v poli s názvem `securelyStoredPassword`.

## <a name="cache-in-excel-workbooks"></a>V sešitech aplikace Excel do mezipaměti
 V projektech aplikace Excel, tento postup je nezbytný, pouze v případě, že chráníte pomocí celého sešitu s heslem <xref:Microsoft.Office.Tools.Excel.Workbook.Protect%2A> metody. Tento postup není nutný, pokud budete chránit pouze konkrétní list s heslem pomocí <xref:Microsoft.Office.Tools.Excel.Worksheet.Protect%2A> metody.

### <a name="to-cache-data-in-an-excel-workbook-that-is-protected-with-a-password"></a>Ukládání dat do mezipaměti v Excelovém sešitu, který je chráněný heslem

1.  V `ThisWorkbook` třídy nebo některé z `Sheet` *n* třídy, označte veřejné pole nebo vlastnost ukládat do mezipaměti. Další informace najdete v tématu [ukládat data do mezipaměti](../vsto/caching-data.md).

2.  Přepsat <xref:Microsoft.Office.Tools.Excel.WorkbookBase.UnprotectDocument%2A> metodu `ThisWorkbook` třídy a odebrat ochranu ze sešitu.

     Při uložení sešitu [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] volá tuto metodu za účelem vám poskytnou příležitost k odemknutí sešitu. To umožňuje uložení změn dat v mezipaměti.

3.  Přepsat <xref:Microsoft.Office.Tools.Excel.WorkbookBase.ProtectDocument%2A> metodu `ThisWorkbook` třídy a znovu nastavit ochranu dokumentu.

     Po uložení sešitu [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] volá tuto metodu za účelem vám poskytnou příležitost k opětovnému použití ochrany v sešitu.

### <a name="example"></a>Příklad
 Následující příklad kódu ukazuje, jak do mezipaměti ukládat data v Excelovém sešitu, který je chráněný heslem. Předtím, než kód odebere ochranu v <xref:Microsoft.Office.Tools.Excel.WorkbookBase.UnprotectDocument%2A> metoda, uloží aktuální <xref:Microsoft.Office.Tools.Excel.Workbook.ProtectStructure%2A> a <xref:Microsoft.Office.Tools.Excel.Workbook.ProtectWindows%2A> hodnoty tak, aby se stejný typ ochrany může být znovu použita v <xref:Microsoft.Office.Tools.Excel.WorkbookBase.ProtectDocument%2A> metody.

 [!code-vb[Trin_CachedDataProtectedWorkbook#1](../vsto/codesnippet/VisualBasic/Trin_CachedDataProtectedWorkbook/ThisWorkbook.vb#1)]
 [!code-csharp[Trin_CachedDataProtectedWorkbook#1](../vsto/codesnippet/CSharp/Trin_CachedDataProtectedWorkbook/ThisWorkbook.cs#1)]

### <a name="compile-the-code"></a>Kompilace kódu
 Přidejte tento kód `ThisWorkbook` třídu ve vašem projektu. Tento kód předpokládá, že heslo je uloženo v poli s názvem `securelyStoredPassword`.

## <a name="see-also"></a>Viz také:
- [Data v mezipaměti](../vsto/caching-data.md)
- [Postupy: Mezipaměť dat pro použití v režimu offline nebo na serveru](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)
- [Postupy: Zdroj dat v dokumentu systému Office do mezipaměti prostřednictvím kódu programu](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md)
