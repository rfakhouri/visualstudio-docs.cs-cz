---
title: "Krok 4: Přidejte metodu CheckTheAnswer() | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c66f3831-b4a0-40bc-a109-8f46f4db35ed
caps.latest.revision: "19"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.openlocfilehash: efa83606dd7ef00cb82ea0d139a7238f0425664c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="step-4-add-the-checktheanswer-method"></a>Krok 4: Přidejte metodu CheckTheAnswer()
V čtvrté části tohoto kurzu, budete napíšete metodu, `CheckTheAnswer()`, který určuje, zda odpovědi na matematické úlohy jsou správné. Toto téma je součástí série, kurz o základních konceptech kódování. Přehled kurzu, najdete v tématu [kurzu 2: vytvoření vypršel časový limit matematického kvízu](../ide/tutorial-2-create-a-timed-math-quiz.md).  
  
> [!NOTE]
>  Pokud jste podle v jazyce Visual Basic, budete používat `Function` – klíčové slovo namísto obvyklého `Sub` – klíčové slovo vzhledem k tomu, že tato metoda vrátí hodnotu. To skutečně tak jednoduché: dílčí nevrací hodnotu, ale nepodporuje funkci.  
  
### <a name="to-verify-whether-the-answers-are-correct"></a>Ověřte, zda jsou správné odpovědi  
  
1.  Přidat `CheckTheAnswer()` metoda.  
  
     Když tato metoda je volána, přidá hodnoty addend1 a addend2 a porovná výsledek, který má hodnotu v součet `NumericUpDown` ovládacího prvku. Pokud jsou hodnoty stejné, metoda vrátí hodnotu `true`. Jinak, vrátí metoda hodnotu `false`. Váš kód by měl vypadat následovně.  
  
     [!code-vb[VbExpressTutorial3Step4#8](../ide/codesnippet/VisualBasic/step-4-add-the-checktheanswer-parens-method_1.vb)]
     [!code-csharp[VbExpressTutorial3Step4#8](../ide/codesnippet/CSharp/step-4-add-the-checktheanswer-parens-method_1.cs)]  
  
     Dále budete Zkontrolujte odpověď aktualizací kód v metodě pro obslužnou rutinu události časovače značek k volání nové `CheckTheAnswer()` metoda.  
  
2.  Přidejte následující kód, který `if else` příkaz.  
  
     [!code-vb[VbExpressTutorial3Step4#10](../ide/codesnippet/VisualBasic/step-4-add-the-checktheanswer-parens-method_2.vb)]
     [!code-csharp[VbExpressTutorial3Step4#10](../ide/codesnippet/CSharp/step-4-add-the-checktheanswer-parens-method_2.cs)]  
  
     Pokud je odpověď správná, `CheckTheAnswer()` vrátí `true`. Obslužné rutiny události zastaví časovač, zobrazí zprávu s gratulací a potom provede **spustit** tlačítko znovu k dispozici. V opačném kvízu pokračuje.  
  
3.  Uložení programu, spustit, spusťte kvízu a zadejte správnou odpověď na přidání problému.  
  
    > [!NOTE]
    >  Když zadáte odpověď, musíte buď vybrat výchozí hodnota dřív, než začnete zadejte svou odpověď, nebo je nutné ručně odstranit na nule. Později v tomto kurzu budete opravte toto chování.  
  
     Pokud zadáte správnou odpověď, otevře se okno se zprávou, **spustit** bude k dispozici tlačítko a časovač zastaví.  
  
### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
-   Chcete-li přejít k dalšímu kroku kurzu, přečtěte si téma [krok 5: přidejte zadejte obslužných rutin událostí pro ovládací prvky NumericUpDown](../ide/step-5-add-enter-event-handlers-for-the-numericupdown-controls.md).  
  
-   Chcete-li vrátit k předchozímu kroku kurzu, přečtěte si téma [krok 3: přidejte časovač odpočítávání](../ide/step-3-add-a-countdown-timer.md).