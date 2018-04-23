---
title: Vlastnost nelze odstranit.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 55873f74-7834-4ec1-8815-eeeb65618d87
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: d12f974e1949bfb96cd2d6bb774eb2b73f371689
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="the-property-property-name-cannot-be-deleted"></a>Vlastnost \<název vlastnosti > nelze odstranit

Vlastnost \<název vlastnosti > nelze odstranit, protože je nastavený jako **diskriminátoru vlastnost** pro vztah dědičnosti mezi \<název třídy > a \<název třídy >

Vybranou vlastnost je nastavena jako **diskriminátoru vlastnost** pro vztah dědičnosti mezi třídami uvedené v chybové zprávě. Vlastnosti nelze odstranit, pokud se účastní konfiguraci dědičnosti mezi datových tříd.

Nastavte **diskriminátoru vlastnost** na jinou vlastnost třídy dat. Chcete-li povolit úspěšné odstranění požadované vlastnosti.

## <a name="to-correct-this-error"></a>Oprava této chyby

1. V Návrháři relací objektů vyberte dědičnosti čáry propojující datové třídy uvedené v chybové zprávě.

2. Nastavte **diskriminátoru** vlastnost, která má jinou vlastnost.

3. Pokuste se znovu odstranit vlastnost.

## <a name="see-also"></a>Viz také

- [Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)
- [Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)