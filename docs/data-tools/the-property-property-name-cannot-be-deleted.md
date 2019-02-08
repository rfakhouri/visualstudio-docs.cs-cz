---
title: Vlastnost nelze odstranit.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 55873f74-7834-4ec1-8815-eeeb65618d87
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 4b1e0652d19b10b1d1ede7b1b950d89ca1bf670c
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55939642"
---
# <a name="the-property-property-name-cannot-be-deleted"></a>Vlastnost \<název vlastnosti > nelze odstranit

Vlastnost \<název vlastnosti > nejde odstranit, protože je nastaven jako **vlastnost diskriminátoru** dědičnosti mezi \<název třídy > a \<název třídy >

Vybraná vlastnost je nastavena jako **vlastnost diskriminátoru** dědičnosti mezi třídami uvedené v chybové zprávě. Vlastnosti nelze odstranit, pokud se účastníte v konfiguraci dědičnosti mezi třídami data.

Nastavte **vlastnost diskriminátoru** různé vlastnosti třídy dat umožňující úspěšné odstranění sady požadovanou vlastnost.

## <a name="to-correct-this-error"></a>Oprava této chyby

1. V **O/R Designer**, vybrat čáru dědičnosti, která se připojuje datové třídy uvedené v chybové zprávě.

2. Nastavte **diskriminátoru** vlastnost na jinou vlastnost.

3. Zkuste znovu odstranit vlastnost.

## <a name="see-also"></a>Viz také:

- [Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)
- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)