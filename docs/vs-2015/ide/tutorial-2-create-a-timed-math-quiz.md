---
title: 'Tutoriál 2: Vytvoření matematického kvízu | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7165d08-ace3-457d-b57d-fb8f80760a6f
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4ec4c1bd1c01229ab0c8f32a78e2b7483a1efc06
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668460"
---
# <a name="tutorial-2-create-a-timed-math-quiz"></a>Tutoriál 2: Vytvoření matematického kvízu s časovým limitem
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [kurz 2: vytvoření a Timed Math Quiz](https://docs.microsoft.com/visualstudio/ide/tutorial-2-create-a-timed-math-quiz).  
  
V tomto kurzu vytvoříte kvíz, ve kterém hráč musí odpovědět na čtyři náhodné aritmetické úlohy v zadaném čase. Získáte informace o následujících postupech:  
  
-   Generovat náhodná čísla pomocí `Random` třídy.  
  
-   Aktivovat události dojde v určitém čase pomocí k **časovače** ovládacího prvku.  
  
-   Kontrolovat tok programu pomocí `if else` příkazy.  
  
-   Proveďte základní aritmetické operace v kódu.  
  
 Po dokončení, kvíz vypadat jako na následujícím obrázku, s výjimkou s různými počty.  
  
 ![Matematický kvíz se čtyřmi úlohami](../ide/media/express-finishedquiz.png "Express_FinishedQuiz")  
V tomto kurzu vytvoříte kvíz  
  
 Chcete-li stáhnout úplnou verzi kvízu, přečtěte si téma [ukázkový kurz pro dokončení matematického kvízu](http://code.msdn.microsoft.com/Complete-Math-Quiz-8581813c).  
  
> [!NOTE]
>  Tento kurz se zabývá Visual C# i Visual Basic, takže se zaměřte na informace, které jsou specifické pro programovací jazyk, který používáte.  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Krok 1: Vytvořte projekt a přidejte do svého formuláře popisky](../ide/step-1-create-a-project-and-add-labels-to-your-form.md)|Začněte vytvořením projektu, změnou vlastností a přidáním `Label` ovládacích prvků.|  
|[Krok 2: Vytvořte náhodný problém s přidáním](../ide/step-2-create-a-random-addition-problem.md)|Vytvořte úlohu sčítání a použít `Random` třídu pro generování náhodných čísel.|  
|[Krok 3: Přidejte časovač odpočítávání](../ide/step-3-add-a-countdown-timer.md)|Přidejte časovač odpočítávání tak, aby kvíz mohou být vypršel časový limit.|  
|[Krok 4: Přidejte metodu CheckTheAnswer()](../ide/step-4-add-the-checktheanswer-parens-method.md)|Přidejte metodu ke kontrole, zda Autor kvízu zadal správnou odpověď pro problém.|  
|[Krok 5: Přidejte obslužné rutiny události pro ovládací prvky NumericUpDown](../ide/step-5-add-enter-event-handlers-for-the-numericupdown-controls.md)|Přidání obslužných rutin událostí, které zjednodušují trvat kvíz.|  
|[Krok 6: Přidejte problém odečtení](../ide/step-6-add-a-subtraction-problem.md)|Přidáte úlohu odčítání, která generuje náhodná čísla, používá časovač a kontroluje správné odpovědi.|  
|[Krok 7: Přidejte problémy násobení a dělení](../ide/step-7-add-multiplication-and-division-problems.md)|Přidejte problémy násobení a dělení, které generují náhodná čísla, použijte časovač a zkontrolujte správné odpovědi.|  
|[Krok 8: Přizpůsobení kvízu](../ide/step-8-customize-the-quiz.md)|Vyzkoušejte další funkce, jako je například změna barev a přidání nápovědy.|



