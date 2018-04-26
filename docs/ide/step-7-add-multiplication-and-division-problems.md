---
title: 'Krok 7: Přidejte problémy násobení a dělení'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: e638959e-f6a4-4eb4-b2e9-f63b7855cf8f
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dbeeca2e53addab923fa3f62c661543497ea1f35
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="step-7-add-multiplication-and-division-problems"></a>Krok 7: Přidejte problémy násobení a dělení
V sedmého části tohoto kurzu budete přidejte problémy násobení a dělení, ale nejdřív myslíte o tom, jak tuto změnu provést. Zvažte počáteční krok, který zahrnuje ukládání hodnot.  

### <a name="to-add-multiplication-and-division-problems"></a>Chcete-li přidat násobení a dělení  

1.  Přidejte do formuláře čtyři další proměnné celé číslo.  

     [!code-vb[VbExpressTutorial3Step7#15](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_1.vb)]
     [!code-csharp[VbExpressTutorial3Step7#15](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_1.cs)]  

2.  Stejně jako před upravit `StartTheQuiz()` metoda vyplnit náhodná čísla pro problémy násobení a dělení.  

     [!code-vb[VbExpressTutorial3Step7#16](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_2.vb)]
     [!code-csharp[VbExpressTutorial3Step7#16](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_2.cs)]  

3.  Změnit `CheckTheAnswer()` metody, které se také zkontroluje problémy násobení a dělení.  

     [!code-vb[VbExpressTutorial3Step7#17](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_3.vb)]
     [!code-csharp[VbExpressTutorial3Step7#17](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_3.cs)]  

     Nelze snadno zadat znak násobení (x) a dělení přihlašovací (÷) pomocí klávesnice, takže Visual C# a Visual Basic přijměte hvězdičku (*) pro násobení a lomítko (/) pro dělení.  

4.  Poslední část obslužné rutiny události časovače značek změňte tak, že vyplní správnou odpověď, když vyprší čas.  

     [!code-vb[VbExpressTutorial3Step7#23](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_4.vb)]
     [!code-csharp[VbExpressTutorial3Step7#23](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_4.cs)]  

5.  Uložte program a spusťte jej.  

     Píší kvízu s časovým limitem poznámky musí odpovědět na čtyři úlohy k dokončení kvízu, jak ukazuje následující obrázek.  

     ![Matematického kvízu s čtyři problémy](../ide/media/express_finishedquiz.png "Express_FinishedQuiz")  
Matematického kvízu s čtyři problémy  

### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  

-   Chcete-li přejít k dalšímu kroku kurzu, přečtěte si téma [krok 8: přizpůsobení kvízu](../ide/step-8-customize-the-quiz.md).  

-   Chcete-li vrátit k předchozímu kroku kurzu, přečtěte si téma [krok 6: přidejte problém odečtení](../ide/step-6-add-a-subtraction-problem.md).
