---
title: 'Tutoriál 2: Vytvoření matematického kvízu'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: d7165d08-ace3-457d-b57d-fb8f80760a6f
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bd0c2a0d239cca67eda9454f522e5041af29c7fc
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34747877"
---
# <a name="tutorial-2-create-a-timed-math-quiz"></a>Tutoriál 2: Vytvoření matematického kvízu
V tomto kurzu vytvoříte kvízu, ve kterém příjemce kvízu s časovým limitem musí odpovědět na čtyři náhodné aritmetické úlohy v zadaném čase. Získáte informace o následujících postupech:

-   Generovat náhodná čísla pomocí <xref:System.Random> třídy.

-   Aktivovat události dochází v určitém čase podle <xref:System.Windows.Forms.Timer> ovládacího prvku.

-   Řízení toku programu pomocí `if else` příkazy.

-   Proveďte základní aritmetické operace v kódu.

 Po dokončení, vaše kvízu bude vypadat jako na následujícím obrázku, s výjimkou s různá čísla.

 ![Matematického kvízu s čtyři problémy](../ide/media/express_finishedquiz.png) kvízu s časovým limitem, které vytvoříte v tomto kurzu

## <a name="tutorial-links"></a>Kurz odkazy

 Si můžete stáhnout dokončenou verzi kvízu [dokončení matematické kvízu s časovým limitem kurz ukázka](http://code.msdn.microsoft.com/Complete-Math-Quiz-8581813c).

> [!NOTE]
>  Tento kurz popisuje, jak Visual C# a Visual Basic, takže zaměřit se na informace, které jsou specifické pro programovací jazyk, který používáte.

## <a name="related-topics"></a>Související témata

|Název|Popis|
|-----------|-----------------|
|[Krok 1: Vytvořte projekt a přidejte do svého formuláře popisky](../ide/step-1-create-a-project-and-add-labels-to-your-form.md)|Začněte tím, že vytváření projektu, změna vlastností a přidání `Label` ovládací prvky.|
|[Krok 2: Vytvořte náhodný problém s přidáním](../ide/step-2-create-a-random-addition-problem.md)|Vytvořit problém a použít `Random` k vygenerování náhodných čísel.|
|[Krok 3: Přidejte časovač odpočítávání](../ide/step-3-add-a-countdown-timer.md)|Přidejte časovač odpočítávání, takže můžete kvízu vypršel časový limit.|
|[Krok 4: Přidejte metodu CheckTheAnswer()](../ide/step-4-add-the-checktheanswer-parens-method.md)|Přidejte metodu ke kontrole, jestli příjemce kvízu s časovým limitem zadali správnou odpověď pro problém.|
|[Krok 5: Přidejte obslužné rutiny událostí Enter pro ovládací prvky NumericUpDown](../ide/step-5-add-enter-event-handlers-for-the-numericupdown-controls.md)|Přidání obslužných rutin událostí, které usnadňují trvat vaší kvízu s časovým limitem.|
|[Krok 6: Přidejte problém odečtení](../ide/step-6-add-a-subtraction-problem.md)|Přidejte problém odečtení, který generuje náhodná čísla, používá časovač a kontroluje správné odpovědi.|
|[Krok 7: Přidejte problémy násobení a dělení](../ide/step-7-add-multiplication-and-division-problems.md)|Přidejte problémy násobení a dělení, které generovat náhodná čísla, použijte časovač a zkontrolujte správné odpovědi.|
|[Krok 8: Přizpůsobení kvízu](../ide/step-8-customize-the-quiz.md)|Vyzkoušejte jiné funkce, jako je například změna barev a přidání nápovědy.|
