---
title: Minimálně jedna vybraná položka obsahuje datový typ, který návrhář nepodporuje.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 71dcd4f9-2946-42c5-9ce4-99c819ea2785
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 294bc51345eb6a9e09f9892c3b9ec17f78c42451
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54986121"
---
# <a name="one-or-more-selected-items-contain-a-data-type-that-is-not-supported-by-the-designer"></a>Minimálně jedna vybraná položka obsahuje datový typ, který návrhář nepodporuje.

Jeden nebo více položek přetáhnout z **Průzkumníka serveru** nebo **Průzkumník databáze** na **O/R Designer** obsahuje datový typ, který není podporován **O / R designer**, například [uživatelem definované typy CLR](/dotnet/framework/data/adonet/sql/clr-user-defined-types).

## <a name="to-correct-this-error"></a>Oprava této chyby

1. Vytvořit zobrazení, která je založena na požadovanou tabulku a nepodporovaný datový typ, který neobsahuje.

2. Přetáhněte zobrazení z **Průzkumníka serveru** nebo **Průzkumník databáze** do návrháře.

## <a name="see-also"></a>Viz také:

- [Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)
- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)