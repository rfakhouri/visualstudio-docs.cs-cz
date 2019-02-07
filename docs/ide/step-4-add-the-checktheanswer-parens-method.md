---
title: 'Krok 4: Přidejte metodu CheckTheAnswer()'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: c66f3831-b4a0-40bc-a109-8f46f4db35ed
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b1eb2c16767be8f1607daf345e754ec9d0209126
ms.sourcegitcommit: 01334abf36d7e0774329050d34b3a819979c95a2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55853846"
---
# <a name="step-4-add-the-checktheanswer-method"></a>Krok 4: Přidejte metodu CheckTheAnswer()
Ve čtvrté části tohoto tutoriálu budete zapisovat metodu `CheckTheAnswer()`, která určuje, zda jsou odpovědi na matematické úlohy správné. Toto téma je součástí série kurzů o základních principech kódování. Přehled kurzu, naleznete v tématu [kurz 2: Vytvoření matematického kvízu](../ide/tutorial-2-create-a-timed-math-quiz.md).

> [!NOTE]
>  Pokud jste postupovali v jazyce Visual Basic, budete používat `Function` – klíčové slovo namísto obvyklého `Sub` – klíčové slovo vzhledem k tomu, že tato metoda vrátí hodnotu. Je skutečně tak jednoduché: sub nevrací hodnotu, ale funkce Ano.

## <a name="to-verify-whether-the-answers-are-correct"></a>Chcete-li ověřit, zda jsou odpovědi správné

1.  Přidat `CheckTheAnswer()` metody.

     Když tato metoda je volána, přidá hodnoty addend1 a addend2 a porovnává výsledek s hodnotou v součtu <xref:System.Windows.Forms.NumericUpDown> ovládacího prvku. Pokud jsou hodnoty stejné, vrátí metoda hodnotu `true`. Jinak metoda vrátí hodnotu `false`. Váš kód by měl vypadat nějak takto.

     [!code-vb[VbExpressTutorial3Step4#8](../ide/codesnippet/VisualBasic/step-4-add-the-checktheanswer-parens-method_1.vb)]
     [!code-csharp[VbExpressTutorial3Step4#8](../ide/codesnippet/CSharp/step-4-add-the-checktheanswer-parens-method_1.cs)]

     Dále zkontrolujte odpověď aktualizací kódu v metodě pro časovače <xref:System.Windows.Forms.Timer.Tick> obslužnou rutinu události pro zavolání nové `CheckTheAnswer()` metody.

2.  Přidejte následující kód, který `if else` příkazu.

     [!code-vb[VbExpressTutorial3Step4#10](../ide/codesnippet/VisualBasic/step-4-add-the-checktheanswer-parens-method_2.vb)]
     [!code-csharp[VbExpressTutorial3Step4#10](../ide/codesnippet/CSharp/step-4-add-the-checktheanswer-parens-method_2.cs)]

     Pokud je odpověď správná, `CheckTheAnswer()` vrátí `true`. Obslužná rutina události zastaví časovač, zobrazí zprávu s gratulací a pak **Start** opět zpřístupní tlačítko. V opačném případě kvíz pokračuje.

3.  Uložte program, spusťte ho, spusťte kvíz a zadejte správnou odpověď úlohu sčítání.

    > [!NOTE]
    >  Když zadáte vaši odpověď, musíte buď vybrat výchozí hodnotu, než začnete zadávat odpověď nebo musíte nulu odstranit ručně. Opravu tohoto chování provedeme dále v tomto kurzu.

     Pokud zadáte správnou odpověď, otevře se okno se zprávou, **Start** tlačítko bude k dispozici a časovač se zastaví.

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

-   Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 5: Přidání obslužné rutiny událostí Enter pro ovládací prvky NumericUpDown](../ide/step-5-add-enter-event-handlers-for-the-numericupdown-controls.md).

-   Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 3: Přidejte časovač odpočítávání](../ide/step-3-add-a-countdown-timer.md).
