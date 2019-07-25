---
title: 'Krok 4: Přidání metody CheckTheAnswer()'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- csharp
- vb
ms.assetid: c66f3831-b4a0-40bc-a109-8f46f4db35ed
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c691b1db57fa1a00ad33441e36ff0f7f79716f11
ms.sourcegitcommit: 59e5758036223ee866f3de5e3c0ab2b6dbae97b6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2019
ms.locfileid: "68416510"
---
# <a name="step-4-add-the-checktheanswer-method"></a>Krok 4: Přidání metody CheckTheAnswer()
Ve čtvrté části tohoto kurzu napíšete metodu `CheckTheAnswer()`, která určuje, zda jsou odpovědi na matematické problémy správné. Toto téma je součástí série kurzů o základních konceptech kódování. Přehled tohoto kurzu najdete v [kurzu 2: Vytvoření časovaného matematického](../ide/tutorial-2-create-a-timed-math-quiz.md)kvízu

> [!NOTE]
> Pokud sledujete v Visual Basic, použijete `Function` místo obvyklého `Sub` klíčového slova klíčové slovo, protože tato metoda vrací hodnotu. Je to opravdu jednoduché: procedura Sub nevrací hodnotu, ale funkce.

## <a name="to-verify-whether-the-answers-are-correct"></a>Ověření, zda jsou odpovědi správné

1. `CheckTheAnswer()` Přidejte metodu.

     Při volání této metody přidá hodnoty addend1 a addend2 a porovná výsledek s hodnotou v ovládacím prvku Sum <xref:System.Windows.Forms.NumericUpDown> . Pokud jsou hodnoty stejné, metoda vrátí hodnotu `true`. V opačném případě metoda vrátí hodnotu `false`. Váš kód by měl vypadat takto.

     [!code-vb[VbExpressTutorial3Step4#8](../ide/codesnippet/VisualBasic/step-4-add-the-checktheanswer-parens-method_1.vb)]
     [!code-csharp[VbExpressTutorial3Step4#8](../ide/codesnippet/CSharp/step-4-add-the-checktheanswer-parens-method_1.cs)]

     V dalším kroku zkontrolujete odpověď tím, že aktualizujete kód v metodě obslužné rutiny <xref:System.Windows.Forms.Timer.Tick> události časovače k volání nové `CheckTheAnswer()` metody.

2. Do `if else` příkazu přidejte následující kód.

     [!code-vb[VbExpressTutorial3Step4#10](../ide/codesnippet/VisualBasic/step-4-add-the-checktheanswer-parens-method_2.vb)]
     [!code-csharp[VbExpressTutorial3Step4#10](../ide/codesnippet/CSharp/step-4-add-the-checktheanswer-parens-method_2.cs)]

     Pokud je odpověď správná, `CheckTheAnswer()` vrátí. `true` Obslužná rutina události zastaví časovač, zobrazí zprávu congratulatory a pak znovu zpřístupní tlačítko **Start** . V opačném případě kvíz pokračuje.

3. Uložte program, spusťte jej, spusťte kvíz a poskytněte správnou odpověď na problém sčítání.

    > [!NOTE]
    > Když zadáte odpověď, musíte buď vybrat výchozí hodnotu, než začnete zadávat odpověď, nebo musíte nulu odstranit ručně. Toto chování opravíte později v tomto kurzu.

     Když zadáte správnou odpověď, otevře se okno se zprávou, tlačítko **Start** bude k dispozici a časovač se zastaví.

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Pokud chcete přejít na další krok kurzu, přečtěte si [krok 5: Přidejte obslužné rutiny událostí Enter pro ovládací](../ide/step-5-add-enter-event-handlers-for-the-numericupdown-controls.md)prvky NumericUpDown.

- Pokud se chcete vrátit k předchozímu kroku kurzu [, podívejte se na krok 3: Přidejte časovač](../ide/step-3-add-a-countdown-timer.md)odpočítávání.
