---
title: 'Postupy: Mezipaměť dat pro použití v režimu offline nebo na serveru'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data caching [Office development in Visual Studio], server use
- Office applications [Office development in Visual Studio], data
- datasets [Office development in Visual Studio], caching
- offline data [Office development in Visual Studio]
- data [Office development in Visual Studio], caching
- data caching [Office development in Visual Studio], offline use
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: bae12ea054c674e14da53fe60879c5466120d0a9
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/21/2019
ms.locfileid: "56636512"
---
# <a name="how-to-cache-data-for-use-offline-or-on-a-server"></a>Postupy: Mezipaměť dat pro použití v režimu offline nebo na serveru
  Můžete označit položku dat do mezipaměti v dokumentu, tak, aby byly k dispozici offline. To také umožňuje pro data v dokumentu, abychom manipulovat jiným kódem, když je dokument uložen na serveru.

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

 Můžete označit položku dat do mezipaměti, když položka dat je deklarovaný ve vašem kódu, nebo pokud používáte <xref:System.Data.DataSet>, nastavením vlastnosti **vlastnosti** okno. Pokud se ukládání do mezipaměti datové položky, které nejsou <xref:System.Data.DataSet> nebo <xref:System.Data.DataTable>, ujistěte se, že splňuje kritéria pro ukládat se do mezipaměti v dokumentu. Další informace najdete v tématu [ukládat data do mezipaměti](../vsto/caching-data.md).

> [!NOTE]
>  Datové sady vytvořené pomocí jazyka Visual Basic, která jsou označena jako **mezipamětí** a **WithEvents** (včetně datových sad, které jsou přetáhnout z **zdroje dat** okna nebo **Nástrojů** , které mají **CacheInDocument** vlastnost nastavena na hodnotu **True**) mají podtržítkem předponou jejich názvů v mezipaměti. Pokud vytvoříte datovou sadu a pojmenujte ji třeba **zákazníkům**, <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> bude mít název **_Customers** v mezipaměti. Při použití <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> pro přístup k této položce v mezipaměti, je nutné zadat **_Customers** místo **zákazníkům**.

### <a name="to-cache-data-in-the-document-using-code"></a>Ukládání dat do mezipaměti v dokumentu pomocí kódu

1.  Deklarovat veřejné pole nebo vlastnost pro položky dat jako člen třídy položku hostitele ve vašem projektu, jako `ThisDocumen`t třídy v projektu aplikace Word nebo `ThisWorkbook` třídu v projektu aplikace Excel.

2.  Použít <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> atribut na člen k označení položek dat k uložení do mezipaměti dat dokumentu. Následující příklad používá k deklaraci pole pro tento atribut <xref:System.Data.DataSet>.

     [!code-csharp[Trin_VstcoreDataExcel#11](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet1.cs#11)]
     [!code-vb[Trin_VstcoreDataExcel#11](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet1.vb#11)]

3.  Přidejte kód k vytvoření instance datové položky a v případě potřeby načíst z databáze.

     Datová položka je načtena pouze při prvním vytvoření; Po tomto datu zůstane mezipaměti se dokument a je nutné napsat další kód ji aktualizovat.

### <a name="to-cache-a-dataset-in-the-document-by-using-the-properties-window"></a>Pro ukládání do mezipaměti pomocí okna Vlastnosti datové sady v dokumentu

1.  Přidat datovou sadu do projektu pomocí nástrojů v návrháři aplikace Visual Studio, například přidáním zdroje dat do vašeho projektu pomocí **zdroje dat** okna.

2.  Vytvoření instance datové sady, pokud ještě není účet máte a vyberte instanci v návrháři.

3.  V **vlastnosti** okno, nastaveno **CacheInDocument** vlastnost **True**.

     Další informace najdete v tématu [Properties in Office Projects](../vsto/properties-in-office-projects.md).

4.  V **vlastnosti** okno, nastaveno **modifikátory** vlastnost **veřejné** (ve výchozím nastavení je **interní**).

## <a name="see-also"></a>Viz také:
- [Data v mezipaměti](../vsto/caching-data.md)
- [Postupy: Zdroj dat v dokumentu systému Office do mezipaměti prostřednictvím kódu programu](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md)
- [Postupy: Data v mezipaměti v dokumentu chráněném heslem](../vsto/how-to-cache-data-in-a-password-protected-document.md)
- [Přístup k datům v dokumentech na serveru](../vsto/accessing-data-in-documents-on-the-server.md)
- [Ukládání dat](../data-tools/saving-data.md)
