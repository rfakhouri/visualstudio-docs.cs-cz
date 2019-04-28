---
title: Vlastnosti v projektech pro systém Office
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Trust Assemblies Location property
- Cache in Document property
- properties [Office development in Visual Studio]
- Namespace for Host Item property
- Office projects [Office development in Visual Studio], properties
- projects [Office development in Visual Studio], properties
- Value2 property
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 9fc2a0774206eac0c9295a425d81555ffdd3cac8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62561359"
---
# <a name="properties-in-office-projects"></a>Vlastnosti v projektech pro systém Office
  Existuje několik důležitých vlastnosti, které jsou k dispozici pro projekty Office v sadě Visual Studio. Tyto vlastnosti je možný **vlastnosti** okna.

 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]

## <a name="namespace-for-host-item"></a>Namespace pro hostitelský objekt
 Použití **Namespace pro hostitelský objekt** vlastnost změnit obor názvů pro hostitele tříd položek (například `ThisAddIn`, `ThisWorkbook`, nebo `ThisDocument` třídy) ve Vizuálu C# projekty. Tato vlastnost se zobrazí v **vlastnosti** okno, když vyberete uzel dokumentu v projektu úrovni dokumentu (například *ExcelWorkbook1.xlsx* nebo *WordDocument1.docx* ) nebo uzlu aplikace v doplňku VSTO projektu (například aplikace Excel nebo Word) v **Průzkumníka řešení**.

 Při vytváření Vizuálu C# Office project, hostitelské položky jsou uvedeny obor názvů založený na název projektu. Doporučuje se, že používáte **Namespace pro hostitelský objekt** vlastnosti pro obor názvů změnit, spíše než upravit jeho kód soubory přímo. Při použití této vlastnosti se změní obor názvů v souborech generovaný kód (skryté), stejně jako v viditelné soubory kódu.

## <a name="cacheindocument"></a>CacheInDocument
 **CacheInDocument** vlastnost se zobrazí v **vlastnosti** okno pro projekty na úrovni dokumentu po výběru instance <xref:System.Data.DataSet> v návrháři aplikace Visual Studio. Pouze veřejné členy můžete uložit do mezipaměti; Ujistěte se, že **modifikátory** je nastavena na **veřejné** Pokud chcete uložit do mezipaměti <xref:System.Data.DataSet>.

 Tato vlastnost nabývá logických hodnot:

- Vyberte **true** pro ukládání do mezipaměti datovou sadu v dokumentu.

- Vyberte **false** Pokud nechcete, aby datovou sadu do mezipaměti v dokumentu.

  Další informace o ukládání dat do mezipaměti najdete v tématu [data v přizpůsobeních na úrovni dokumentu v mezipaměti](../vsto/cached-data-in-document-level-customizations.md).

## <a name="value2"></a>Hodnota2
 **Hodnota2** vlastnost je dostupná jenom pro projekty sešitu nebo šabloně aplikace Excel. Se zobrazí v části **datové vazby** vlastnost uzlu v **vlastnosti** okno vyberete <xref:Microsoft.Office.Tools.Excel.NamedRange> ovládací prvek v Návrháři list.

 Použití **hodnota2** vlastnost **vlastnosti** okno pro vytvoření vazby <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> vlastnost <xref:Microsoft.Office.Tools.Excel.NamedRange> pole ve zdroji dat.

## <a name="see-also"></a>Viz také:
- [Návrh a vytvoření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)
- [Přehled šablon projektů Office](../vsto/office-project-templates-overview.md)
- [Události v projektech pro systém Office](../vsto/events-in-office-projects.md)
