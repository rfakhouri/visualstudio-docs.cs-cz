---
title: 'Krok 7: Přidání úloh násobení a dělení'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- csharp
- vb
ms.assetid: e638959e-f6a4-4eb4-b2e9-f63b7855cf8f
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 887af3a439e1f6e0f21d5ca68061d2f9977dfac7
ms.sourcegitcommit: 59e5758036223ee866f3de5e3c0ab2b6dbae97b6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2019
ms.locfileid: "68416547"
---
# <a name="step-7-add-multiplication-and-division-problems"></a>Krok 7: Přidání úloh násobení a dělení
V sedmé části tohoto kurzu přidáte problémy násobení a dělení, ale nejprve si myslíte, jak tuto změnu provést. Vezměte v úvahu počáteční krok, který zahrnuje ukládání hodnot.

## <a name="to-add-multiplication-and-division-problems"></a>Přidání problémů násobení a dělení

1. Přidejte do formuláře čtyři další celočíselné proměnné.

     [!code-vb[VbExpressTutorial3Step7#15](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_1.vb)]
     [!code-csharp[VbExpressTutorial3Step7#15](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_1.cs)]

2. Jak jste předtím, upravte `StartTheQuiz()` metodu tak, aby vyplnila náhodná čísla pro problémy násobení a dělení.

     [!code-vb[VbExpressTutorial3Step7#16](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_2.vb)]
     [!code-csharp[VbExpressTutorial3Step7#16](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_2.cs)]

3. `CheckTheAnswer()` Upravte metodu tak, aby také kontrolovala problémy násobení a dělení.

     [!code-vb[VbExpressTutorial3Step7#17](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_3.vb)]
     [!code-csharp[VbExpressTutorial3Step7#17](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_3.cs)]

     Pomocí klávesnice nemůžete snadno zadat znak násobení (×) a znaménko dělení (÷), takže vizuál C# a Visual Basic přijímají pro násobení znak hvězdičky (*) a lomítko (/) pro dělení.

4. Změňte poslední část obslužné rutiny <xref:System.Windows.Forms.Timer.Tick> události časovače tak, aby vyplnila správnou odpověď, když vyprší čas.

     [!code-vb[VbExpressTutorial3Step7#23](../ide/codesnippet/VisualBasic/step-7-add-multiplication-and-division-problems_4.vb)]
     [!code-csharp[VbExpressTutorial3Step7#23](../ide/codesnippet/CSharp/step-7-add-multiplication-and-division-problems_4.cs)]

5. Uložte program a spusťte jej.

     Kvíz uživatelé vyplňující musí odpovědět na čtyři problémy, aby se dokončil kvíz, jak ukazuje následující obrázek.

     ![Matematický kvíz se čtyřmi](../ide/media/express_finishedquiz.png)
problémy**Matematický kvíz** se čtyřmi problémy

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Pokud chcete přejít na další krok kurzu, přečtěte si [krok 8: Přizpůsobení kvízu](../ide/step-8-customize-the-quiz.md).

- Pokud se chcete vrátit k předchozímu kroku kurzu [, přečtěte si krok 6: Přidejte problém](../ide/step-6-add-a-subtraction-problem.md)odčítání.
