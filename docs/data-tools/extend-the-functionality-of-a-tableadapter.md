---
title: Rozšíření funkcí objektů TableAdapter
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], TableAdapters
- data [Visual Studio], extending TableAdapters
- TableAdapters, adding functionality
ms.assetid: 418249c8-c7f3-47ef-a94c-744cb6fe6aaf
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: d0ec905670c72ff7c2c5f5d94c9f5189241daebb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62567429"
---
# <a name="extend-the-functionality-of-a-tableadapter"></a>Rozšíření funkcí objektů TableAdapter

Funkce objektu typu TableAdapter můžete rozšířit přidáním kódu do souboru částečné třídy TableAdapter.

Při jakékoli změně TableAdapter v se znovu vygeneroval kód, který definuje objektu typu TableAdapter **Návrhář Dataset**, nebo když průvodce změní konfiguraci objektu TableAdapter. Abyste zabránili odstranění při generování objektu TableAdapter kódu, přidejte kód do souboru částečné třídy TableAdapter.

Částečné třídy povolit kód pro konkrétní třídu rozdělit mezi několik fyzických souborů. Další informace najdete v tématu [částečné](/dotnet/visual-basic/language-reference/modifiers/partial) nebo [partial (typ)](/dotnet/csharp/language-reference/keywords/partial-type).

## <a name="locate-tableadapters-in-code"></a>Najít objekty TableAdapter v kódu

Zatímco objekty TableAdapter jsou navrženy s **Návrhář Dataset**, generované třídy TableAdapter nejsou vnořené třídy typu <xref:System.Data.DataSet>. Objekty TableAdapter jsou umístěny v oboru názvů na základě názvu objektu TableAdapter přidružený objekt dataset. Například, pokud vaše aplikace obsahuje datovou sadu s názvem `HRDataSet`, objekty TableAdapter by být umístěný ve `HRDataSetTableAdapters` oboru názvů. (Tento vzor dodržuje zásady vytváření názvů: *DatasetName* + `TableAdapters`).

V následujícím příkladu se předpokládá TableAdapter s názvem `CustomersTableAdapter`nachází v projektu s `NorthwindDataSet`.

### <a name="to-create-a-partial-class-for-a-tableadapter"></a>Chcete-li vytvořit částečné třídy objektu TableAdapter

1. Přidejte novou třídu do projektu tak, že přejdete **projektu** nabídky a vyberete **přidat třídu**.

2. Název třídy `CustomersTableAdapterExtended`.

3. Vyberte **Přidat**.

4. Nahraďte kód správný obor názvů a název dílčí třídy pro váš projekt následujícím způsobem:

     [!code-csharp[VbRaddataTableAdapters#2](../data-tools/codesnippet/CSharp/extend-the-functionality-of-a-tableadapter_1.cs)]
     [!code-vb[VbRaddataTableAdapters#2](../data-tools/codesnippet/VisualBasic/extend-the-functionality-of-a-tableadapter_1.vb)]

## <a name="see-also"></a>Viz také:

- [Vyplnění datových sad pomocí objektů TableAdapter](../data-tools/fill-datasets-by-using-tableadapters.md)