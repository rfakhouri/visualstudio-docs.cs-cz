---
title: 'Krok 7: Přidejte problémy násobení a dělení | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: e638959e-f6a4-4eb4-b2e9-f63b7855cf8f
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 47623d7a65de85b50ad1910425052288a261e49d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68178570"
---
# <a name="step-7-add-multiplication-and-division-problems"></a>Krok 7: Přidání úloh násobení a dělení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

V sedmé části tohoto kurzu budete přidejte problémy násobení a dělení, ale nejprve přemýšlejte, jak provést tuto změnu. Zvažte počáteční krok, který zahrnuje ukládání hodnot.  
  
### <a name="to-add-multiplication-and-division-problems"></a>Chcete-li přidat úlohy násobení a dělení  
  
1. Přidejte do formuláře čtyři další celočíselné proměnné.  
  
     [!code-csharp[VbExpressTutorial3Step7#15](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial3step7/cs/form1.cs#15)]
     [!code-vb[VbExpressTutorial3Step7#15](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial3step7/vb/form1.vb#15)]  
  
2. Stejně jako dříve upravte `StartTheQuiz()` metoda k vyplnění náhodných čísel pro úlohy násobení a dělení.  
  
     [!code-csharp[VbExpressTutorial3Step7#16](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial3step7/cs/form1.cs#16)]
     [!code-vb[VbExpressTutorial3Step7#16](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial3step7/vb/form1.vb#16)]  
  
3. Upravit `CheckTheAnswer()` metodu tak, aby také kontrolovala úlohy násobení a dělení.  
  
     [!code-csharp[VbExpressTutorial3Step7#17](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial3step7/cs/form1.cs#17)]
     [!code-vb[VbExpressTutorial3Step7#17](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial3step7/vb/form1.vb#17)]  
  
     Nelze snadno zadejte znaménko násobení (x) a dělení znaménko (÷) pomocí klávesnice, proto Visual C# a Visual Basic přijměte hvězdičku (*) pro násobení a dělení znak lomítka (/).  
  
4. Změňte poslední část obslužné rutiny události cyklů časovače, aby vyplnila správnou odpověď, když vyprší čas.  
  
     [!code-csharp[VbExpressTutorial3Step7#23](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial3step7/cs/form1.cs#23)]
     [!code-vb[VbExpressTutorial3Step7#23](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial3step7/vb/form1.vb#23)]  
  
5. Uložte program a spusťte jej.  
  
     Uživatelé vyplňující kvíz musí odpovědět na čtyři úlohy k dokončení kvízu, jako je vidět na následujícím obrázku.  
  
     ![Matematický kvíz se čtyřmi úlohami](../ide/media/express-finishedquiz.png "Express_FinishedQuiz")  
Matematický kvíz se čtyřmi úlohami  
  
### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
- Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 8: Přizpůsobení kvízu](../ide/step-8-customize-the-quiz.md).  
  
- Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 6: Přidejte problém odečtení](../ide/step-6-add-a-subtraction-problem.md).
