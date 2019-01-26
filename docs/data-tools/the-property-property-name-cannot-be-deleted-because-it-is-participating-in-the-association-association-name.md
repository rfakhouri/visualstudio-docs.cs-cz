---
title: Vlastnost nejde odstranit, protože se účastní asociace
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 32eeef65eaf8cfebbce0458b90f954bf491f718a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54997959"
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

- [Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)
- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)