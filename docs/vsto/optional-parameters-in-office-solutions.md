---
title: Volitelné parametry v řešeních pro systém Office | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], optional parameters
- Visual C# [Office development in Visual Studio], optional parameters
- Visual Basic [Office development in Visual Studio], optional parameters
- application development [Office development in Visual Studio], optional parameters
- missing field [Office development in Visual Studio]
- optional parameters [Office development in Visual Studio]
- parameters [Office development in Visual Studio], optional
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9b03f6112ebf44a89da3b4d5cbf6f7ff23f54b9c
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34571981"
---
# <a name="optional-parameters-in-office-solutions"></a>Volitelné parametry v řešeních pro systém Office
  Mnoho z metod v objektové modely z aplikace Microsoft Office přijmout volitelné parametry. Pokud používáte Visual Basic pro vývoj řešení Office v sadě Visual Studio, nemáte předat hodnotu pro volitelné parametry, protože se automaticky použijí výchozí hodnoty pro každý parametr chybí. Ve většině případů můžete vypustit volitelné parametry v projektech Visual C#. Však nemůžete vynechat volitelné **ref** parametry `ThisDocument` třídy v projekty na úrovni dokumentu aplikace Word.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
 Další informace o práci s volitelné parametry v projektech Visual C# a Visual Basic najdete v tématu [pojmenované a nepovinné argumenty &#40;C&#35; Průvodce programováním&#41; ](/dotnet/csharp/programming-guide/classes-and-structs/named-and-optional-arguments) a [volitelné parametry &#40;Jazyka Visual Basic&#41;](/dotnet/visual-basic/programming-guide/language-features/procedures/optional-parameters).  
  
> [!NOTE]  
>  V dřívějších verzích sady Visual Studio musíte zadat hodnotu pro všechny volitelné parametry v projektech Visual C#. Pro větší pohodlí si tyto projekty zahrnout globální proměnné s názvem `missing` , pokud chcete použít výchozí hodnotu parametru, je můžete předat do volitelný parametr. Projekty Visual C# pro Office v sadě Visual Studio v nich zahrnuta `missing` proměnné, ale obvykle není nutné ho použít při vývoji řešení pro systém Office v [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)], s výjimkou při volání metody s volitelné **ref** Parametry v `ThisDocument` třídy v projekty na úrovni dokumentu ve Wordu.  
  
## <a name="example-in-excel"></a>Příklad v aplikaci Excel  
 <xref:Microsoft.Office.Tools.Excel.Worksheet.CheckSpelling%2A> Metoda má mnoho volitelné parametry. Můžete zadat hodnoty pro některé parametry a přijměte výchozí hodnotu jiných, jak je znázorněno v následujícím příkladu kódu. Tento příklad vyžaduje projekt na úrovni dokumentu a s listu třídy s názvem `Sheet1`.  
  
 [!code-csharp[Trin_VstrefGeneralExcel#1](../vsto/codesnippet/CSharp/excelworkbook1/Sheet1.cs#1)]
 [!code-vb[Trin_VstrefGeneralExcel#1](../vsto/codesnippet/VisualBasic/excelworkbook1/Sheet1.vb#1)]  
  
## <a name="example-in-word"></a>Příklad v aplikaci Word  
 <xref:Microsoft.Office.Interop.Word.Find.Execute%2A> Metoda má mnoho volitelné parametry. Můžete zadat hodnoty pro některé parametry a přijměte výchozí hodnotu jiných, jak je znázorněno v následujícím příkladu kódu.  
  
 [!code-vb[Trin_VstrefGeneralWord#1](../vsto/codesnippet/VisualBasic/worddocument1/ThisDocument.vb#1)]
 [!code-csharp[Trin_VstrefGeneralWord#1](../vsto/codesnippet/CSharp/worddocument1/ThisDocument.cs#1)]  
  
## <a name="use-optional-parameters-of-methods-in-the-thisdocument-class-in-visual-c-document-level-projects-for-word"></a>Volitelné parametry použití metod ve třídě ThisDocument v jazyce Visual C# projekty na úrovni dokumentu pro Word  
 Model objektů aplikace Word obsahuje mnoho způsobů s volitelnými **ref** parametry, které přijímají <xref:System.Object> hodnoty. Však nemůžete vynechat volitelné **ref** parametry metody generované `ThisDocument` třídy v jazyce Visual C# projekty na úrovni dokumentu ve Wordu. Visual C# umožňuje vynechat volitelné **ref** parametry jenom pro metody rozhraní, není třídy. Například následující příklad kódu nelze kompilovat, protože nemůžete vynechat volitelné **ref** parametry <xref:Microsoft.Office.Tools.Word.DocumentBase.CheckSpelling%2A> metodu `ThisDocument` třídy.  
  
 [!code-csharp[Trin_VstrefGeneralWord#3](../vsto/codesnippet/CSharp/worddocument1/ThisDocument.cs#3)]  
  
 Při volání metody `ThisDocument` třídy, postupujte podle následujících pokynů:  
  
-   Přijměte výchozí hodnotu volitelný **ref** parametr, předejte `missing` proměnnou na parametr. `missing` Proměnné je automaticky definovaný v projektech Visual C# Office a je přiřazena k hodnotě <xref:System.Type.Missing> v projektu generovaného kódu.  
  
-   Chcete-li určit vlastní hodnoty volitelný **ref** parametr deklarovat objekt, který je přiřazen na hodnotu, která chcete určit a pak tento objekt předat parametru.  
  
 Následující příklad kódu ukazuje způsob volání <xref:Microsoft.Office.Tools.Word.DocumentBase.CheckSpelling%2A> metoda zadáním hodnoty pro *ignoreUppercase* parametr a přijímá výchozí hodnota pro ostatní parametry.  
  
 [!code-csharp[Trin_VstrefGeneralWord#4](../vsto/codesnippet/CSharp/worddocument1/ThisDocument.cs#4)]  
  
 Pokud chcete psát kód, který vynechá volitelné **ref** parametry metody v `ThisDocument` třídu, můžete případně volat stejnou metodu na <xref:Microsoft.Office.Interop.Word.Document> objekt vrácený <xref:Microsoft.Office.Tools.Word.Document.InnerObject%2A> vlastnost a vynechat možnost parametry z dané metody. Můžete to provést, protože <xref:Microsoft.Office.Interop.Word.Document> je rozhraní, nikoli třída.  
  
 [!code-csharp[Trin_VstrefGeneralWord#5](../vsto/codesnippet/CSharp/worddocument1/ThisDocument.cs#5)]  
  
 Další informace o parametrech hodnota a odkaz na typ najdete v tématu [předání argumentů podle hodnoty a podle reference &#40;jazyka Visual Basic&#41; ](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference) (pro Visual Basic) a [předat parametry &#40;C&#35; Průvodce programováním&#41;](/dotnet/csharp/programming-guide/classes-and-structs/passing-parameters).  
  
## <a name="see-also"></a>Viz také:  
 [Vývoj řešení pro systém Office](../vsto/developing-office-solutions.md)   
 [Psaní kódu v řešeních pro systém Office](../vsto/writing-code-in-office-solutions.md)  
  
  