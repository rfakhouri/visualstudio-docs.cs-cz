---
title: 'Krok 8: Přidejte metodu k ověření, zda hráč vyhrál'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 6e317f6e-ba4c-4306-8924-300b0c2f65c6
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b6bd64908c902c83023bc48bc72ab6443b2a7df7
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55934455"
---
# <a name="step-8-add-a-method-to-verify-whether-the-player-won"></a>Krok 8: Přidejte metodu k ověření, zda hráč vyhrál
Vytvořili jste zábavnou hru, která však potřebuje ještě něco. Hra by měla skončit vítězstvím hráče, takže budete muset přidat `CheckForWinner()` metodu k ověření, zda hráč zvítězil.

## <a name="to-add-a-method-to-verify-whether-the-player-won"></a>Přidání metody k ověření, zda hráč zvítězil

1.  Přidat `CheckForWinner()` metoda do dolní části kódu, níže `timer1_Tick()` obslužná rutina události, jak je znázorněno v následujícím kódu.

     [!code-csharp[VbExpressTutorial4Step8#10](../ide/codesnippet/CSharp/step-8-add-a-method-to-verify-whether-the-player-won_1.cs)]
     [!code-vb[VbExpressTutorial4Step8#10](../ide/codesnippet/VisualBasic/step-8-add-a-method-to-verify-whether-the-player-won_1.vb)]

     Metoda používá další `foreach` smyčky ve Vizuálu C# nebo `For Each` smyčky v jazyce Visual Basic k projití každého popisku v <xref:System.Windows.Forms.TableLayoutPanel>. Používá operátor rovnosti (`==` v jazyce Visual C# a `=` v jazyce Visual Basic) ke kontrole barvy ikony každého popisku k ověření, zda odpovídá pozadí. Pokud se barvy shodují, zůstane ikona skryta a hráč nespároval všechny zbývající ikony. V takovém případě program použije `return` příkaz k vynechání zbývající metody. Pokud smyčka projde přes všechny popisky bez spuštění `return` příkazu, to znamená, že všechny ikony ve formuláři byly spárovány. Program zobrazí prvek MessageBox s blahopřáním k vítězství a pak zavolá formuláře `Close()` metoda k ukončení hry.

2.  Dále nechejme popisku <xref:System.Windows.Forms.Control.Click> zavolat novou obslužnou rutinu události `CheckForWinner()` metody. Ujistěte se, že váš program kontroluje vítěze ihned po tom, co zobrazí druhou ikonu, kterou hráč vybere. Vyhledejte řádek, kde jste nastavili barvu druhé vybrané ikony a poté zavolejte `CheckForWinner()` metodu, jak je znázorněno v následujícím kódu.

     [!code-csharp[VbExpressTutorial4Step8#11](../ide/codesnippet/CSharp/step-8-add-a-method-to-verify-whether-the-player-won_2.cs)]
     [!code-vb[VbExpressTutorial4Step8#11](../ide/codesnippet/VisualBasic/step-8-add-a-method-to-verify-whether-the-player-won_2.vb)]

3.  Program uložte a spusťte jej. Zahrajte si hru a spárujte všechny ikony. Když vyhrajete, program zobrazí gratulací **MessageBox** (jak ukazuje následující obrázek) a potom jej zavře.

     ![Porovnávací hra s ovládacím prvkem MessageBox](../ide/media/express_tut4step8.png)
**Porovnávací hra** s **MessageBox**

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

-   Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 9: Vyzkoušejte další funkce](../ide/step-9-try-other-features.md).

-   Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 7: Zachování dvojic viditelných](../ide/step-7-keep-pairs-visible.md).
