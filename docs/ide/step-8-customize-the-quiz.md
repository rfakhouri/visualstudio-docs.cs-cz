---
title: 'Krok 8: Přizpůsobení kvízu'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: dc8edb13-1b23-47d7-b859-8c6f7888c1a9
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f2b2f9d46b623f63d216ce530cd283bf799a3a73
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53842353"
---
# <a name="step-8-customize-the-quiz"></a>Krok 8: Přizpůsobení kvízu
V poslední části tutoriálu prozkoumáte několik způsobů, jak kvíz přizpůsobit a rozšíříte si již nabyté znalosti. Například se zamyslíte nad tím, jak program vytvoří problém náhodného dělení, jehož odpovědí není nikdy zlomek. Další informace, zapněte `timeLabel` určit jinou barvu a dejte účastníkovi kvízu nápovědu.  

## <a name="to-customize-the-quiz"></a>Přizpůsobení kvízu  

-   Když v kvízu zbývá pouze pět sekund, zapněte **timeLabel** řídit červenou nastavením jeho **BackColor** vlastnosti (`timeLabel.BackColor = Color.Red;`). Resetujte barvu, když že kvíz.  
  
-   Dejte účastníkovi kvízu nápovědu pomocí přehrání zvuku při zadání správné odpovědi do <xref:System.Windows.Forms.NumericUpDown> ovládacího prvku. (Pro každou událost ovládacího prvku <xref:System.Windows.Forms.NumericUpDown.ValueChanged> je nutné napsat obslužnou rutinu události, která se vyvolá vždy, když účastník kvízu změní hodnotu ovládacího prvku.)  
  
## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
-   Chcete-li stáhnout úplnou verzi kvízu, přečtěte si téma [ukázkový kurz pro dokončení matematický kvíz](https://code.msdn.microsoft.com/Complete-Math-Quiz-8581813c).  
  
-   Chcete-li přejít k dalšímu kurzu, přečtěte si téma [Tutorial 3: Vytvořit odpovídající her](../ide/tutorial-3-create-a-matching-game.md).  
  
-   Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 7: Přidejte problémy násobení a dělení](../ide/step-7-add-multiplication-and-division-problems.md).
