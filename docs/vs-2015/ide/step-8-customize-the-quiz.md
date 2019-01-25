---
title: 'Krok 8: Přizpůsobení kvízu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: dc8edb13-1b23-47d7-b859-8c6f7888c1a9
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 413a0cb2f1445f166f1a5c9e541b2a4268ff2e31
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54776082"
---
# <a name="step-8-customize-the-quiz"></a>Krok 8: Přizpůsobení kvízu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V poslední části tutoriálu prozkoumáte několik způsobů, jak kvíz přizpůsobit a rozšíříte si již nabyté znalosti. Například se zamyslíte nad tím, jak program vytvoří problém náhodného dělení, jehož odpovědí není nikdy zlomek. Další informace, zapněte `timeLabel` určit jinou barvu a dejte účastníkovi kvízu nápovědu.  
  
### <a name="to-customize-the-quiz"></a>Přizpůsobení kvízu  
  
-   Když v kvízu zbývá pouze pět sekund, zapněte **timeLabel** řídit červenou nastavením jeho **BackColor** vlastnosti (`timeLabel.BackColor = Color.Red;`). Resetujte barvu, když že kvíz.  
  
-   Dejte účastníkovi kvízu nápovědu pomocí přehrání zvuku při zadání správné odpovědi do ovládacího prvku NumericUpDown. (Pro každou událost ovládacího prvku `ValueChanged()` je nutné napsat obslužnou rutinu události, která se vyvolá vždy, když účastník kvízu změní hodnotu ovládacího prvku.)  
  
### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
-   Chcete-li stáhnout úplnou verzi kvízu, přečtěte si téma [ukázkový kurz pro dokončení matematického kvízu](http://code.msdn.microsoft.com/Complete-Math-Quiz-8581813c).  
  
-   Chcete-li přejít k dalšímu kurzu, přečtěte si téma [Tutorial 3: Vytvořit odpovídající her](../ide/tutorial-3-create-a-matching-game.md).  
  
-   Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 7: Přidejte problémy násobení a dělení](../ide/step-7-add-multiplication-and-division-problems.md).
