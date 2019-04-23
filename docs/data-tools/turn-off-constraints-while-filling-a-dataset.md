---
title: Vypnutí omezení při naplňování datové sady
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- DataRow.BeginEdit
- DataRow.EndEdit
- DataRow.CancelEdit
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- updating datasets, constraints
- constraints [Visual Basic], datasets
- datasets [Visual Basic], constraints
- constraints [Visual Basic], suspending during dataset update
ms.assetid: 553f7d0c-2faa-4c17-b226-dd02855bf1dc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 9aca29de7e9c5a01e0c2caad2c42015cd31b3f75
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60102858"
---
# <a name="turn-off-constraints-while-filling-a-dataset"></a>Vypnutí omezení při naplňování datové sady

Pokud datová sada obsahuje omezení (například omezení foreign key), mohou vyvolat chyby související s odpovídajícího pořadí operací, které jsou provedeny datové sadě. Načítají se podřízené záznamy před načtením související například nadřazené záznamy může narušit omezení a způsobit chybu. Jakmile načtete podřízený záznam, omezení kontroluje související nadřazený záznam a vyvolá chybu.

Kdyby existovalo žádný mechanismus pro omezení dočasné pozastavení, by vyvolána chyba pokaždé, když se pokusila načíst záznam do podřízené tabulky. Dalším způsobem, jak pozastavit všechna omezení v datové sadě je <xref:System.Data.DataRow.BeginEdit%2A>, a <xref:System.Data.DataRow.EndEdit%2A> vlastnosti.

> [!NOTE]
> Události ověření (třeba <xref:System.Data.DataTable.ColumnChanging> a <xref:System.Data.DataTable.RowChanging>) nebude vyvolána, když jsou vypnuté omezení.

## <a name="to-suspend-update-constraints-programmatically"></a>Pozastavit aktualizace omezení prostřednictvím kódu programu

- Následující příklad ukazuje, jak dočasně vypnout kontrolu v datové sadě omezení:

     [!code-csharp[VbRaddataEditing#10](../data-tools/codesnippet/CSharp/turn-off-constraints-while-filling-a-dataset_1.cs)]
     [!code-vb[VbRaddataEditing#10](../data-tools/codesnippet/VisualBasic/turn-off-constraints-while-filling-a-dataset_1.vb)]

## <a name="to-suspend-update-constraints-using-the-dataset-designer"></a>Pozastavit aktualizace omezení pomocí návrháře datových sad

1. Otevřete svou datovou sadu v **Návrhář Dataset**. Další informace najdete v tématu [názorný postup: Vytvoření datové sady v návrháři datových sad](walkthrough-creating-a-dataset-with-the-dataset-designer.md).

2. V **vlastnosti** okno, nastaveno <xref:System.Data.DataSet.EnforceConstraints%2A> vlastnost `false`.

## <a name="see-also"></a>Viz také:

- [Vyplnění datových sad pomocí objektů TableAdapter](../data-tools/fill-datasets-by-using-tableadapters.md)
- [Relace v datových sadách](../data-tools/relationships-in-datasets.md)