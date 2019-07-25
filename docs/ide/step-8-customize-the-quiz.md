---
title: 'Krok 8: Přizpůsobení kvízu'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- csharp
- vb
ms.assetid: dc8edb13-1b23-47d7-b859-8c6f7888c1a9
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1868cd30cc41187ac995e71ee86d81dd0fb83d5a
ms.sourcegitcommit: 59e5758036223ee866f3de5e3c0ab2b6dbae97b6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2019
ms.locfileid: "68416460"
---
# <a name="step-8-customize-the-quiz"></a>Krok 8: Přizpůsobení kvízu
V poslední části tutoriálu prozkoumáte několik způsobů, jak kvíz přizpůsobit a rozšíříte si již nabyté znalosti. Například se zamyslíte nad tím, jak program vytvoří problém náhodného dělení, jehož odpovědí není nikdy zlomek. Chcete-li získat další informace `timeLabel` , přepněte ovládací prvek na jinou barvu a dejte pomocnému kvízu.

## <a name="to-customize-the-quiz"></a>Přizpůsobení kvízu

- Když v kvízu zůstane jenom pět sekund, otočte ovládací prvek **timeLabel** červen nastavením jeho vlastnosti **BackColor** .

```csharp
timeLabel.BackColor = Color.Red;
```

```vb
timeLabel.BackColor = Color.Red
```

Resetovat barvu při překročení kvízu.

- Dejte tomuto kvízu pokyn, aby pomohli přehrání zvuku při zadání správné odpovědi do <xref:System.Windows.Forms.NumericUpDown> ovládacího prvku. (Pro každou událost ovládacího prvku <xref:System.Windows.Forms.NumericUpDown.ValueChanged> je nutné napsat obslužnou rutinu události, která se vyvolá vždy, když účastník kvízu změní hodnotu ovládacího prvku.)

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Pokud si chcete stáhnout dokončenou verzi kvízu, přečtěte si [ukázku kurz dokončení matematického kvízu](https://code.msdn.microsoft.com/Complete-Math-Quiz-8581813c).

- Pokud chcete přejít k dalšímu kurzu, přečtěte si [kurz 3: Vytvořte porovnávací hru](../ide/tutorial-3-create-a-matching-game.md).

- Pokud se chcete vrátit k předchozímu kroku kurzu [, přečtěte si krok 7: Přidejte problémy](../ide/step-7-add-multiplication-and-division-problems.md)násobení a dělení.
