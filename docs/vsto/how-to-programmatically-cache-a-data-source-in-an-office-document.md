---
title: 'Postupy: Zdroj dat v dokumentu systému Office do mezipaměti prostřednictvím kódu programu'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office applications [Office development in Visual Studio], data
- datasets [Office development in Visual Studio], caching
- StartCaching method
- data caching [Office development in Visual Studio], programmatically
- data [Office development in Visual Studio], caching
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: dd125e105681aa389a0c1b213fc5373b1177db6f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53960693"
---
# <a name="how-to-programmatically-cache-a-data-source-in-an-office-document"></a>Postupy: Zdroj dat v dokumentu systému Office do mezipaměti prostřednictvím kódu programu
  Můžete programově přidat datového objektu do datové mezipaměti v dokumentu voláním `StartCaching` metoda hostitele položky, jako například <xref:Microsoft.Office.Tools.Word.Document>, <xref:Microsoft.Office.Tools.Excel.Workbook>, nebo <xref:Microsoft.Office.Tools.Excel.Worksheet>. Odebrat datový objekt z mezipaměti dat voláním `StopCaching` metoda položky hostitele.

 `StartCaching` Metoda a `StopCaching` metody jsou privátní, ale zobrazí se v IntelliSense.

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

 Při použití `StartCaching` není potřeba deklarovat metodu pro přidání datového objektu do datové mezipaměti datový objekt <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> atribut. Datový objekt však musí splňovat určité požadavky mají být přidány do datové mezipaměti. Další informace najdete v tématu [ukládat data do mezipaměti](../vsto/caching-data.md).

## <a name="to-programmatically-cache-a-data-object"></a>Chcete-li datový objekt mezipaměti prostřednictvím kódu programu

1.  Datový objekt na úrovni třídy, ne uvnitř metodu deklarujte. Tento příklad předpokládá, že deklarujete <xref:System.Data.DataSet> s názvem `dataSet1` , které chcete ukládat do mezipaměti prostřednictvím kódu programu.

     [!code-csharp[Trin_VstcoreDataExcel#12](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#12)]
     [!code-vb[Trin_VstcoreDataExcel#12](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#12)]

2.  Vytvoření instance objektu data a následně zavolat `StartCaching` metoda instance dokumentu nebo listu a předat mu název datového objektu.

     [!code-csharp[Trin_VstcoreDataExcel#13](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#13)]
     [!code-vb[Trin_VstcoreDataExcel#13](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#13)]

## <a name="to-stop-caching-a-data-object"></a>Zastavit ukládání do mezipaměti datový objekt

1.  Volání `StopCaching` metoda instance dokumentu nebo listu a předat mu název datového objektu. Tento příklad předpokládá, že máte <xref:System.Data.DataSet> s názvem `dataSet1` , kterou chcete zastavit ukládání do mezipaměti.

     [!code-csharp[Trin_VstcoreDataExcel#14](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#14)]
     [!code-vb[Trin_VstcoreDataExcel#14](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#14)]

    > [!NOTE]
    >  Nevolejte `StopCaching` z obslužné rutiny události pro `Shutdown` události z dokumentu nebo sešitu. Časem `Shutdown` událost se vyvolá, je příliš pozdě upravit datovou mezipaměť. Další informace o `Shutdown` událostí, naleznete v tématu [události v projektech pro systém Office](../vsto/events-in-office-projects.md).

## <a name="see-also"></a>Viz také:

- [Data v mezipaměti](../vsto/caching-data.md)
- [Postupy: Mezipaměť dat pro použití v režimu offline nebo na serveru](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md)
- [Postupy: Data v mezipaměti v dokumentu chráněném heslem](../vsto/how-to-cache-data-in-a-password-protected-document.md)
- [Přístup k datům v dokumentech na serveru](../vsto/accessing-data-in-documents-on-the-server.md)
- [Ukládání dat](../data-tools/saving-data.md)
