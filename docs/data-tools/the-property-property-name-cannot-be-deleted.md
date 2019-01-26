---
title: Vlastnost nelze odstranit.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 55873f74-7834-4ec1-8815-eeeb65618d87
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: 6940da198fddc4213bbec1271164b20cfbeb6672
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54994157"
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