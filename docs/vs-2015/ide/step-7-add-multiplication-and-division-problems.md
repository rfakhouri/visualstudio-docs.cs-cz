---
title: 'Krok 7: Přidejte problémy násobení a dělení | Dokumentace Microsoftu'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e638959e-f6a4-4eb4-b2e9-f63b7855cf8f
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 83c85dfdca66e9df3634f84795042b331bf3f760
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42667426"
---
# <a name="step-7-add-multiplication-and-division-problems"></a>Krok 7: Přidejte problémy násobení a dělení
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [krok 7: Přidat úlohy násobení a dělení](https://docs.microsoft.com/visualstudio/ide/step-7-add-multiplication-and-division-problems).  
  
V sedmé části tohoto kurzu budete přidejte problémy násobení a dělení, ale nejprve přemýšlejte, jak provést tuto změnu. Zvažte počáteční krok, který zahrnuje ukládání hodnot.  
  
### <a name="to-add-multiplication-and-division-problems"></a>Chcete-li přidat úlohy násobení a dělení  
  
1.  Přidejte do formuláře čtyři další celočíselné proměnné.  
  
     [!code-csharp[VbExpressTutorial3Step7#15](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial3step7/cs/form1.cs#15)]
     [!code-vb[VbExpressTutorial3Step7#15](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial3step7/vb/form1.vb#15)]  
  
2.  Stejně jako dříve upravte `StartTheQuiz()` metoda k vyplnění náhodných čísel pro úlohy násobení a dělení.  
  
     [!code-csharp[VbExpressTutorial3Step7#16](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial3step7/cs/form1.cs#16)]
     [!code-vb[VbExpressTutorial3Step7#16](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial3step7/vb/form1.vb#16)]  
  
3.  Upravit `CheckTheAnswer()` metodu tak, aby také kontrolovala úlohy násobení a dělení.  
  
     [!code-csharp[VbExpressTutorial3Step7#17](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial3step7/cs/form1.cs#17)]
     [!code-vb[VbExpressTutorial3Step7#17](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial3step7/vb/form1.vb#17)]  
  
     Nelze snadno zadejte znaménko násobení (x) a dělení znaménko (÷) pomocí klávesnice, proto Visual C# a Visual Basic přijměte hvězdičku (*) pro násobení a dělení znak lomítka (/).  
  
4.  Změňte poslední část obslužné rutiny události cyklů časovače, aby vyplnila správnou odpověď, když vyprší čas.  
  
     [!code-csharp[VbExpressTutorial3Step7#23](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial3step7/cs/form1.cs#23)]
     [!code-vb[VbExpressTutorial3Step7#23](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial3step7/vb/form1.vb#23)]  
  
5.  Uložte program a spusťte jej.  
  
     Uživatelé vyplňující kvíz musí odpovědět na čtyři úlohy k dokončení kvízu, jako je vidět na následujícím obrázku.  
  
     ![Matematický kvíz se čtyřmi úlohami](../ide/media/express-finishedquiz.png "Express_FinishedQuiz")  
Matematický kvíz se čtyřmi úlohami  
  
### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
-   Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 8: přizpůsobení kvízu](../ide/step-8-customize-the-quiz.md).  
  
-   Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 6: přidejte problém odečtení](../ide/step-6-add-a-subtraction-problem.md).



