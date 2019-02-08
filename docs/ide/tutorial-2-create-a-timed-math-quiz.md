---
title: 'Kurz 2: Vytvoření matematického kvízu'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d7165d08-ace3-457d-b57d-fb8f80760a6f
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c93ddfc85e318a2095f757c6131b151a5414c884
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55956932"
---
# <a name="tutorial-2-create-a-timed-math-quiz"></a>Kurz 2: Vytvoření matematického kvízu

V tomto kurzu vytvoříte kvíz, ve kterém hráč musí odpovědět na čtyři náhodné aritmetické úlohy v zadaném čase. Získáte informace o následujících postupech:

-   Generovat náhodná čísla pomocí <xref:System.Random> třídy.

-   Aktivovat události dojde v určitém čase pomocí k <xref:System.Windows.Forms.Timer> ovládacího prvku.

-   Kontrolovat tok programu pomocí `if else` příkazy.

-   Proveďte základní aritmetické operace v kódu.

Po dokončení, kvíz vypadat jako na následujícím obrázku, s výjimkou s různými počty:

![Matematický kvíz se čtyřmi úlohami](../ide/media/express_finishedquiz.png)

## <a name="tutorial-links"></a>Kurz odkazy

Chcete-li stáhnout úplnou verzi kvízu, přečtěte si téma [ukázkový kurz pro dokončení matematický kvíz](https://code.msdn.microsoft.com/Complete-Math-Quiz-8581813c).

> [!NOTE]
> Tento kurz se zabývá Visual C# i Visual Basic, takže se zaměřte na informace, které jsou specifické pro programovací jazyk, který používáte.

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[Krok 1: Vytvořte projekt a přidejte do svého formuláře popisky](../ide/step-1-create-a-project-and-add-labels-to-your-form.md)|Začněte vytvořením projektu, změnou vlastností a přidáním `Label` ovládacích prvků.|
|[Krok 2: Vytvořit náhodnou úlohu sčítání](../ide/step-2-create-a-random-addition-problem.md)|Vytvořte úlohu sčítání a použít `Random` třídu pro generování náhodných čísel.|
|[Krok 3: Přidejte časovač odpočítávání](../ide/step-3-add-a-countdown-timer.md)|Přidejte časovač odpočítávání tak, aby kvíz mohou být vypršel časový limit.|
|[Krok 4: Přidejte metodu CheckTheAnswer()](../ide/step-4-add-the-checktheanswer-parens-method.md)|Přidejte metodu ke kontrole, zda Autor kvízu zadal správnou odpověď pro problém.|
|[Krok 5: Přidání obslužné rutiny událostí Enter pro ovládací prvky NumericUpDown](../ide/step-5-add-enter-event-handlers-for-the-numericupdown-controls.md)|Přidání obslužných rutin událostí, které zjednodušují trvat kvíz.|
|[Krok 6: Přidejte problém odečtení](../ide/step-6-add-a-subtraction-problem.md)|Přidáte úlohu odčítání, která generuje náhodná čísla, používá časovač a kontroluje správné odpovědi.|
|[Krok 7: Přidejte problémy násobení a dělení](../ide/step-7-add-multiplication-and-division-problems.md)|Přidejte problémy násobení a dělení, které generují náhodná čísla, použijte časovač a zkontrolujte správné odpovědi.|
|[Krok 8: Přizpůsobení kvízu](../ide/step-8-customize-the-quiz.md)|Vyzkoušejte další funkce, jako je například změna barev a přidání nápovědy.|
