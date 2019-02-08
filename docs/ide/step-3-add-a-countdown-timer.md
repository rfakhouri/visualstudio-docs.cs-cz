---
title: 'Krok 3: Přidejte časovač odpočítávání'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 62670a2b-efdc-45c6-9646-9b17eeb33dcb
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ac6ea6f45446b35d9b65d9665ede5b2e76b387e3
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55940708"
---
# <a name="step-3-add-a-countdown-timer"></a>Krok 3: Přidejte časovač odpočítávání
Ve třetí části tohoto kurzu přidáte časovač odpočítávání ke sledování počtu sekund pro dokončení kvízu.

> [!NOTE]
>  Toto téma je součástí série kurzů o základních principech kódování. Přehled kurzu, naleznete v tématu [kurz 2: Vytvoření matematického kvízu](../ide/tutorial-2-create-a-timed-math-quiz.md).

## <a name="to-add-a-countdown-timer"></a>Chcete-li přidat časovač odpočítávání

1.  Přidejte celočíselnou proměnnou s názvem **timeLeft**, stejně jako v předchozím postupu. Váš kód by měl vypadat nějak takto.

     [!code-vb[VbExpressTutorial3Step3#5](../ide/codesnippet/VisualBasic/step-3-add-a-countdown-timer_1.vb)]
     [!code-csharp[VbExpressTutorial3Step3#5](../ide/codesnippet/CSharp/step-3-add-a-countdown-timer_1.cs)]

     Teď budete potřebovat metodu, která ve skutečnosti vrátí počet sekund, jako je například časovač, což vyvolá událost po dobu, kterou zadáte.

2.  V okně návrhu přesuňte <xref:System.Windows.Forms.Timer> řízení z **součásti** kategorii **nástrojů** do formuláře.

     Ovládací prvek se zobrazí v šedé oblasti v dolní části okna návrhu.

3.  Ve formuláři, zvolte **timer1** ikonu, která jste právě přidali a nastavte jeho **Interval** vlastnost **1000**.

     Vzhledem k tomu, že hodnota intervalu jsou milisekund, hodnota 1000 způsobí, že <xref:System.Windows.Forms.Timer.Tick> událost vyvolána každou sekundu.

4.  Ve formuláři, dvakrát klikněte **časovače** ovládací prvek, nebo jej vyberte a klikněte na tlačítko **Enter** klíč.

     Zobrazí se editor kódu a metoda obslužné rutiny události Tick, kterou jste právě přidali.

5.  Přidejte následující příkazy do nové metody obslužné rutiny události.

     [!code-vb[VbExpressTutorial3Step3#6](../ide/codesnippet/VisualBasic/step-3-add-a-countdown-timer_2.vb)]
     [!code-csharp[VbExpressTutorial3Step3#6](../ide/codesnippet/CSharp/step-3-add-a-countdown-timer_2.cs)]

     Na základě toho, co jste přidali, každou sekundu časovač zkontroluje, jestli se má spustit tak, že určíte, zda **timeLeft** celočíselná proměnná je větší než 0. Pokud se jedná, doba stále trvá. Časovač se nejprve odečte 1 z proměnné timeLeft a poté aktualizuje **Text** vlastnost **timeLabel** ovládacího prvku na kvízu zobrazit, kolik sekund uživateli.

     Jestliže nezbývá žádný čas, časovač se zastaví a změní se text **timeLabel** tak, aby zobrazuje **čas vypršel!** Okno se zprávou oznamuje, že kvíz a odpověď je odhalena – v tomto případě přidáním addend1 a addend2. **Povoleno** vlastnost **startButton** ovládacího prvku nastavená na **true** tak, aby kvízu, mohl spustit další kvíz.

     Právě jste přidali `if else` příkazu, který je, jak můžete programům sdělujete, abyste se mohli rozhodovat. `if else` Příkaz vypadá takto.

    > [!NOTE]
    >  Následující příklad je pouze pro ilustraci-nepřidávejte ho do projektu.

    ```vb
    If (something that your program will check) Then
        ' One or more statements that will run
        ' if what the program checked is true.
    Else
        ' One or more statements that will run
        ' if what the program checked is false.
    End If
    ```

    ```csharp
    if (something that your program will check)
    {
        // One or more statements that will run
        // if what the program checked is true.
    }
    else
    {
        // One or more statements that will run
        // if what the program checked is false.
    }
    ```

     Prohlédněte si blíže příkaz, který jste přidali v kroku `else` blok k zobrazení odpovědi na úlohu sčítání.

     [!code-vb[VbExpressTutorial3Step3#24](../ide/codesnippet/VisualBasic/step-3-add-a-countdown-timer_3.vb)]
     [!code-csharp[VbExpressTutorial3Step3#24](../ide/codesnippet/CSharp/step-3-add-a-countdown-timer_3.cs)]

     Příkaz `addend1 + addend2` sečte hodnoty obou proměnných společně. První část (`sum.Value`) používá **hodnotu** vlastnost součtový ovládací prvek pro zobrazení správné odpovědi. Stejnou vlastnost můžete použít později ke zkontrolování odpovědi kvízu.

     Uživatelé vyplňující kvíz mohou zadávat čísla snadněji pomocí <xref:System.Windows.Forms.NumericUpDown> ovládací prvek, který je důvod, proč ho použijete pro odpovědi na matematické úlohy. Všechny možné odpovědi jsou celá čísla od 0 do 100. Ponechte výchozí hodnoty **minimální**, **maximální**, a **počet desetinných míst** , zajistíte, že uživatelům vyplňujícím kvíz nelze zadat desetinná čísla, záporná čísla, nebo čísla, která jsou příliš vysoká. (Pokud jste chtěli povolit uživatelům vyplňujícím kvíz zadání hodnoty 3,141, ale nikoli 3,1415, můžete nastavit **počet desetinných míst** vlastnost na 3.)

6.  Přidejte tři řádky na konec objektu `StartTheQuiz()` metoda, takže kód vypadá následovně.

     [!code-vb[VbExpressTutorial3Step3#7](../ide/codesnippet/VisualBasic/step-3-add-a-countdown-timer_4.vb)]
     [!code-csharp[VbExpressTutorial3Step3#7](../ide/codesnippet/CSharp/step-3-add-a-countdown-timer_4.cs)]

     Teď, když spustíte kvíz, **timeLeft** proměnná je nastavená na 30 a **Text** vlastnost **timeLabel** řízení je nastavené na 30 sekund. Pak bude <xref:System.Windows.Forms.Timer.Start> metoda ovládacím prvku časovač spustí odpočítávání. (Kvíz zatím kontrolu odpovědi –, který obsahuje další.)

7.  Uložte program, spusťte ho a klikněte na tlačítko **Start** tlačítko na formuláři.

     Časovač spustí odpočet. Když čas vyprší, kvíz skončí a zobrazí se odpověď. Následující obrázek znázorňuje probíhající kvíz.

     ![Probíhající matematický kvíz](../ide/media/express_addcountdown.png) probíhající matematický kvíz

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

-   Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 4: Přidejte metodu CheckTheAnswer()](../ide/step-4-add-the-checktheanswer-parens-method.md).

-   Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 2: Vytvořit náhodnou úlohu sčítání](../ide/step-2-create-a-random-addition-problem.md).
