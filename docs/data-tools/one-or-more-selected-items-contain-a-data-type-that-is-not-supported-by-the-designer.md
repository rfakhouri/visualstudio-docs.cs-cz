---
title: Minimálně jedna vybraná položka obsahuje datový typ, který návrhář nepodporuje.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 71dcd4f9-2946-42c5-9ce4-99c819ea2785
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 12ec2ed7dc2a12556fcb6eeeddbe2d0745ae7f72
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62566365"
---
# <a name="one-or-more-selected-items-contain-a-data-type-that-is-not-supported-by-the-designer"></a>Minimálně jedna vybraná položka obsahuje datový typ, který návrhář nepodporuje.

Jeden nebo více položek přetáhnout z **Průzkumníka serveru** nebo **Průzkumník databáze** na **O/R Designer** obsahuje datový typ, který není podporován **O / R designer**, například [uživatelem definované typy CLR](/dotnet/framework/data/adonet/sql/clr-user-defined-types).

## <a name="to-correct-this-error"></a>Oprava této chyby

1. Vytvořit zobrazení, která je založena na požadovanou tabulku a nepodporovaný datový typ, který neobsahuje.

2. Přetáhněte zobrazení z **Průzkumníka serveru** nebo **Průzkumník databáze** do návrháře.

## <a name="see-also"></a>Viz také:

- [Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)
- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)