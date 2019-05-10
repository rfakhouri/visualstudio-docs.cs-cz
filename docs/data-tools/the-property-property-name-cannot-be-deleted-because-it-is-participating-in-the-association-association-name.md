---
title: Vlastnost nejde odstranit, protože se účastní asociace
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: d277919229316768cde27efdc9b2797d0351e9fe
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65458494"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted-because-it-is-participating-in-the-association-ltassociation-namegt"></a>Vlastnost &lt;název vlastnosti&gt; nejde odstranit, protože se účastní asociace &lt;název přidružení&gt;

Vybraná vlastnost je nastavena jako **přidružení vlastnost** pro přidružení mezi třídami uvedené v chybové zprávě. Vlastnosti nelze odstranit, pokud se účastní asociace mezi datových tříd.

Nastavte **přidružení vlastnost** různé vlastnosti třídy dat umožňující úspěšné odstranění sady požadovanou vlastnost.

## <a name="to-correct-this-error"></a>Oprava této chyby

1. Vyberte na Asociační čára **O/R Designer** datové třídy uvedené v chybové zprávě, která se připojuje.

2. Dvakrát klikněte na řádek otevřít **Editor asociace** dialogové okno.

3. Odebere vlastnost z **vlastnosti přidružení**.

4. Zkuste znovu odstranit vlastnost.

## <a name="see-also"></a>Viz také:

- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)