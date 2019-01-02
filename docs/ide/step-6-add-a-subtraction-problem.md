---
title: 'Krok 6: Přidejte problém odečtení'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 59204ef9-24bd-4f81-b85f-e3168e518a3e
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f42d2b414e79c1138f699964808ff13a375ec4fe
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53948164"
---
# <a name="step-6-add-a-subtraction-problem"></a>Krok 6: Přidejte problém odečtení
V šesté části tohoto kurzu kurzu přidáte úlohu odčítání a zjistěte, jak provádět následující úlohy:

-   Store hodnoty odčítání.

-   Generovat náhodná čísla pro úlohu (a ujistěte se, že odpověď je od 0 do 100).

-   Aktualizujte metodu, která kontroluje odpovědi, takže příliš zkontroluje nový problém s odčítáním.

-   Aktualizovat časovače <xref:System.Windows.Forms.Timer.Tick> obslužná rutina události tak, aby obslužná rutina události vyplnila správnou odpověď, když vyprší čas.

## <a name="to-add-a-subtraction-problem"></a>Chcete-li přidat úlohu odčítání

1.  Přidáte dvě celočíselné proměnné pro odčítání do svého formuláře mezi celočíselné proměnné pro sčítání a časovač. Kód by měl vypadat nějak takto.

     [!code-vb[VbExpressTutorial3Step5_6#12](../ide/codesnippet/VisualBasic/step-6-add-a-subtraction-problem_1.vb)]
     [!code-csharp[VbExpressTutorial3Step5_6#12](../ide/codesnippet/CSharp/step-6-add-a-subtraction-problem_1.cs)]

     Názvy nových proměnných celých čísel –**minuend** a **subtrahend**– nejsou programovací termíny. Jsou to tradiční názvy v aritmetice pro číslo, které se ještě odečteno (subtrahend) a číslo, ze kterého je menšitel se odečte (minuend). Rozdíl je minuend mínus subtrahend. Můžete použít jiné názvy, protože program nevyžaduje konkrétní názvy pro proměnné, ovládací prvky, komponenty nebo metody. Je třeba dodržovat pravidla, například názvy číslicemi, ale obvykle můžete použít názvy, například x1, x2, x3 a x4. Ale obecný názvy usnadňují mohou ztížit čtení kódu a problémy téměř znemožnit sledování. Pokud chcete zachovat názvy proměnných jedinečný a užitečné, budete používat tradiční názvy pro násobení (násobenec x násobitel = produktu) a dělení (dělitel ÷ Delenec = podíl) později v tomto kurzu.

     V dalším kroku upravíte `StartTheQuiz()` metodu pro poskytnutí náhodných hodnot pro problém s odčítáním.

2.  Přidejte následující kód za komentář "Vyplnění úlohy odčítání".

     [!code-vb[VbExpressTutorial3Step5_6#13](../ide/codesnippet/VisualBasic/step-6-add-a-subtraction-problem_2.vb)]
     [!code-csharp[VbExpressTutorial3Step5_6#13](../ide/codesnippet/CSharp/step-6-add-a-subtraction-problem_2.cs)]

     K nedocházelo k záporným odpovědím pro úlohu odčítání, tento kód používá <xref:System.Random.Next> metodu <xref:System.Random> třídy trochu odlišně od jak na úlohu sčítání. Když poskytnete `Next()` metoda dvě hodnoty, použije náhodné číslo, které je větší než nebo rovno první hodnota a menší než druhý. Následující kód zvolí náhodné číslo od 1 do 100 a uloží jej do proměnné minuend.

     [!code-vb[VbExpressTutorial3Step5_6#21](../ide/codesnippet/VisualBasic/step-6-add-a-subtraction-problem_3.vb)]
     [!code-csharp[VbExpressTutorial3Step5_6#21](../ide/codesnippet/CSharp/step-6-add-a-subtraction-problem_3.cs)]

     Můžete volat `Next()` metody třídy Random, kterou jste nazvali "randomizer" dříve v tomto kurzu několika různými způsoby. Metody, které můžete volat více než jedním způsobem, se nazývají přetížené a můžete je zkoumala technologie IntelliSense. Znovu se podívejte na text nápovědy v okně technologie IntelliSense `Next()` metody.

     ![Okno popisu tlačítka technologie IntelliSense](../ide/media/express_overloads.png)
**IntelliSense** okno popisu tlačítka

     Zobrazí se popis **(+ 2 overload(s))**, což znamená, že můžete volat `Next()` metoda dvěma dalšími způsoby. Přetížení obsahují různá čísla nebo typy argumentů, tak, aby fungovaly mírně odlišně od sebe. Například metoda může převzít jediný celočíselný argument a jedno z jejich přetížení může trvat celé číslo a řetězec. Zvolíte správné přetížení na základě na co chcete udělat. Když přidáte kód, který `StartTheQuiz()` metoda, další informace se zobrazí v okně technologie IntelliSense ihned poté, co zadáte `randomizer.Next(`. Chcete-li cyklování skrze přetížení, zvolte **šipka nahoru** a **šipka dolů** klíče, jak je znázorněno na následujícím obrázku:

     ![Přetížení pro další&#40; &#41; metoda v technologii IntelliSense](../ide/media/express_nextoverload.png) přetížení pro **Next()** metoda **technologie IntelliSense**

     V tomto případě chcete zvolit poslední přetížení, protože můžete určit minimální a maximální hodnoty.

3.  Upravit `CheckTheAnswer()` metodu ke kontrole správného odečtení odpovědí.

     [!code-vb[VbExpressTutorial3Step5_6#14](../ide/codesnippet/VisualBasic/step-6-add-a-subtraction-problem_4.vb)]
     [!code-csharp[VbExpressTutorial3Step5_6#14](../ide/codesnippet/CSharp/step-6-add-a-subtraction-problem_4.cs)]

     V jazyce Visual C# `&&` je `logical and` operátor. V jazyce Visual Basic je ekvivalentní operátor `AndAlso`. Tyto operátory označují "Pokud součet addend1 a addend2 je roven hodnotě součtu NumericUpDown a minuend mínus subtrahend je roven hodnotě rozdílu NumericUpDown." `CheckTheAnswer()` Vrátí metoda `true` pouze v případě, že odpovědi na sčítání a odčítání problémy jsou obě správné.

4.  Nahraďte poslední část obslužné rutiny události cyklů časovače následujícím kódem, tak, aby vyplnila správnou odpověď, když vyprší čas.

     [!code-vb[VbExpressTutorial3Step5_6#22](../ide/codesnippet/VisualBasic/step-6-add-a-subtraction-problem_5.vb)]
     [!code-csharp[VbExpressTutorial3Step5_6#22](../ide/codesnippet/CSharp/step-6-add-a-subtraction-problem_5.cs)]

5.  Uložte a spusťte váš kód.

     Váš program zahrnuje úlohu odčítání, jako je vidět na následujícím obrázku:

     ![Matematický kvíz s úlohou odečítání](../ide/media/express_addsubtract.png)
**matematického kvízu** s úlohou odečítání

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

-   Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 7: Přidejte problémy násobení a dělení](../ide/step-7-add-multiplication-and-division-problems.md).

-   Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 5: Přidání obslužné rutiny událostí Enter pro ovládací prvky NumericUpDown](../ide/step-5-add-enter-event-handlers-for-the-numericupdown-controls.md).
