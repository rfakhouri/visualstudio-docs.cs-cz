---
title: 'Krok 7: Přidejte problémy násobení a dělení'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: e638959e-f6a4-4eb4-b2e9-f63b7855cf8f
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e60cb6c289fa582eb27137483f44b7557d4e426d
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60068519"
---
# <a name="step-7-add-multiplication-and-division-problems"></a>Krok 7: Přidejte problémy násobení a dělení
V sedmé části tohoto kurzu budete přidejte problémy násobení a dělení, ale nejprve přemýšlejte, jak provést tuto změnu. Zvažte počáteční krok, který zahrnuje ukládání hodnot.

## <a name="to-add-multiplication-and-division-problems"></a>Chcete-li přidat úlohy násobení a dělení

1. Přidejte do formuláře čtyři další celočíselné proměnné.

     [!code-vb[VbExpressTutorial3Step7#15](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_1.vb)]
     [!code-csharp[VbExpressTutorial3Step7#15](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_1.cs)]

2. Stejně jako dříve upravte `StartTheQuiz()` metoda k vyplnění náhodných čísel pro úlohy násobení a dělení.

     [!code-vb[VbExpressTutorial3Step7#16](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_2.vb)]
     [!code-csharp[VbExpressTutorial3Step7#16](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_2.cs)]

3. Upravit `CheckTheAnswer()` metodu tak, aby také kontrolovala úlohy násobení a dělení.

     [!code-vb[VbExpressTutorial3Step7#17](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_3.vb)]
     [!code-csharp[VbExpressTutorial3Step7#17](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_3.cs)]

     Nelze snadno zadejte znaménko násobení (x) a dělení znaménko (÷) pomocí klávesnice, proto Visual C# a Visual Basic přijměte hvězdičku (*) pro násobení a dělení znak lomítka (/).

4. Změňte poslední část časovače <xref:System.Windows.Forms.Timer.Tick> obslužná rutina události tak, že vyplní správnou odpověď, když vyprší čas.

     [!code-vb[VbExpressTutorial3Step7#23](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_4.vb)]
     [!code-csharp[VbExpressTutorial3Step7#23](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_4.cs)]

5. Uložte program a spusťte jej.

     Uživatelé vyplňující kvíz musí odpovědět na čtyři úlohy k dokončení kvízu, jako je vidět na následujícím obrázku.

     ![Matematický kvíz se čtyřmi úlohami](../ide/media/express_finishedquiz.png)
**matematického kvízu** se čtyřmi úlohami

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 8: Přizpůsobení kvízu](../ide/step-8-customize-the-quiz.md).

- Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 6: Přidejte problém odečtení](../ide/step-6-add-a-subtraction-problem.md).
