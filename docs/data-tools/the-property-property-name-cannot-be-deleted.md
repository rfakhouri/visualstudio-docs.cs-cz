---
title: Vlastnost nelze odstranit.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 55873f74-7834-4ec1-8815-eeeb65618d87
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 80b5e40900cd8912b727270a46ebcf119c324f53
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
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