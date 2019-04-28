---
title: 'Kurz 2: Vytvoření matematického kvízu | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: d7165d08-ace3-457d-b57d-fb8f80760a6f
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 2a87a192f7a14a4d59a5ca5cff15bc62abbdefc6
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63443288"
---
# <a name="tutorial-2-create-a-timed-math-quiz"></a>Kurz 2: Vytvoření matematického kvízu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V tomto kurzu vytvoříte kvíz, ve kterém hráč musí odpovědět na čtyři náhodné aritmetické úlohy v zadaném čase. Získáte informace o následujících postupech:  
  
- Generovat náhodná čísla pomocí `Random` třídy.  
  
- Aktivovat události dojde v určitém čase pomocí k **časovače** ovládacího prvku.  
  
- Kontrolovat tok programu pomocí `if else` příkazy.  
  
- Proveďte základní aritmetické operace v kódu.  
  
  Po dokončení, kvíz vypadat jako na následujícím obrázku, s výjimkou s různými počty.  
  
  ![Matematický kvíz se čtyřmi úlohami](../ide/media/express-finishedquiz.png "Express_FinishedQuiz")  
  V tomto kurzu vytvoříte kvíz  
  
  Chcete-li stáhnout úplnou verzi kvízu, přečtěte si téma [ukázkový kurz pro dokončení matematického kvízu](http://code.msdn.microsoft.com/Complete-Math-Quiz-8581813c).  
  
> [!NOTE]
> Tento kurz se zabývá Visual C# i Visual Basic, takže se zaměřte na informace, které jsou specifické pro programovací jazyk, který používáte.  
  
## <a name="related-topics"></a>Související témata  
  
|Název|Popis|  
|-----------|-----------------|  
|[Krok 1: Vytvoření projektu a přidání popisků do formuláře](../ide/step-1-create-a-project-and-add-labels-to-your-form.md)|Začněte vytvořením projektu, změnou vlastností a přidáním `Label` ovládacích prvků.|  
|[Krok 2: Vytvoření úlohy sčítání náhodných čísel](../ide/step-2-create-a-random-addition-problem.md)|Vytvořte úlohu sčítání a použít `Random` třídu pro generování náhodných čísel.|  
|[Krok 3: Přidání časovače odpočítávání](../ide/step-3-add-a-countdown-timer.md)|Přidejte časovač odpočítávání tak, aby kvíz mohou být vypršel časový limit.|  
|[Krok 4: Přidání metody CheckTheAnswer()](../ide/step-4-add-the-checktheanswer-parens-method.md)|Přidejte metodu ke kontrole, zda Autor kvízu zadal správnou odpověď pro problém.|  
|[Krok 5: Přidání obslužných rutin událostí Enter pro ovládací prvky NumericUpDown](../ide/step-5-add-enter-event-handlers-for-the-numericupdown-controls.md)|Přidání obslužných rutin událostí, které zjednodušují trvat kvíz.|  
|[Krok 6: Přidání úlohy odčítání](../ide/step-6-add-a-subtraction-problem.md)|Přidáte úlohu odčítání, která generuje náhodná čísla, používá časovač a kontroluje správné odpovědi.|  
|[Krok 7: Přidání úloh násobení a dělení](../ide/step-7-add-multiplication-and-division-problems.md)|Přidejte problémy násobení a dělení, které generují náhodná čísla, použijte časovač a zkontrolujte správné odpovědi.|  
|[Krok 8: Přizpůsobení kvízu](../ide/step-8-customize-the-quiz.md)|Vyzkoušejte další funkce, jako je například změna barev a přidání nápovědy.|
