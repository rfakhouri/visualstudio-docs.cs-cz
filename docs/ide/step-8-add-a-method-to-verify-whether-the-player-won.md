---
title: 'Krok 8: Přidání metody k ověření, jestli hráč vyhrál'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- csharp
- vb
ms.assetid: 6e317f6e-ba4c-4306-8924-300b0c2f65c6
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9daa4d939eb1cd5c03d3811337f258fc3ef3c70c
ms.sourcegitcommit: 59e5758036223ee866f3de5e3c0ab2b6dbae97b6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2019
ms.locfileid: "68415633"
---
# <a name="step-8-add-a-method-to-verify-whether-the-player-won"></a>Krok 8: Přidání metody k ověření, jestli hráč vyhrál
Vytvořili jste zábavnou hru, která však potřebuje ještě něco. Hra by měla skončit, když je přehrávač WINS, takže potřebujete přidat `CheckForWinner()` metodu pro ověření, zda hráč zvítězil.

## <a name="to-add-a-method-to-verify-whether-the-player-won"></a>Přidání metody k ověření, zda hráč zvítězil

1. Přidejte metodu do dolní části kódu `timer1_Tick()` pod obslužnou rutinou události, jak je znázorněno v následujícím kódu. `CheckForWinner()`

     [!code-csharp[VbExpressTutorial4Step8#10](../ide/codesnippet/CSharp/step-8-add-a-method-to-verify-whether-the-player-won_1.cs)]
     [!code-vb[VbExpressTutorial4Step8#10](../ide/codesnippet/VisualBasic/step-8-add-a-method-to-verify-whether-the-player-won_1.vb)]

     Metoda používá jinou `foreach` smyčku v vizuálu C# nebo `For Each` smyčce v Visual Basic <xref:System.Windows.Forms.TableLayoutPanel>k procházení každého popisku v. Používá operátor rovnosti (`==` v jazyce Visual C# a `=` v Visual Basic) ke kontrole barvy ikony jednotlivých popisků a k ověření, zda odpovídá pozadí. Pokud se barvy shodují, zůstane ikona skryta a hráč nespároval všechny zbývající ikony. V takovém případě program používá `return` příkaz k přeskočení zbytku metody. Pokud smyčka projde všemi štítky bez provedení `return` příkazu, znamená to, že všechny ikony ve formuláři byly spárovány. Program zobrazí MessageBox, aby congratulate přehrávač při výhrě, a potom zavolá `Close()` metodu formuláře pro ukončení hry.

2. Dále má obslužná rutina <xref:System.Windows.Forms.Control.Click> události popisku zavolat novou `CheckForWinner()` metodu. Ujistěte se, že váš program kontroluje vítěze ihned po tom, co zobrazí druhou ikonu, kterou hráč vybere. Vyhledejte řádek, kde jste nastavili barvu druhé zvolené ikony, a potom zavolejte `CheckForWinner()` metodu hned po tom, jak je znázorněno v následujícím kódu.

     [!code-csharp[VbExpressTutorial4Step8#11](../ide/codesnippet/CSharp/step-8-add-a-method-to-verify-whether-the-player-won_2.cs)]
     [!code-vb[VbExpressTutorial4Step8#11](../ide/codesnippet/VisualBasic/step-8-add-a-method-to-verify-whether-the-player-won_2.vb)]

3. Program uložte a spusťte jej. Zahrajte si hru a spárujte všechny ikony. Když nahrajete, program zobrazí congratulatory **MessageBox** (jak je znázorněno na následujícím obrázku) a pak pole zavře.

     ![Porovnávací hra s](../ide/media/express_tut4step8.png)
MessageBox, která**odpovídá hře** s **MessageBox**

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Pokud chcete přejít na další krok kurzu, přečtěte si [krok 9: Vyzkoušejte jiné funkce](../ide/step-9-try-other-features.md).

- Pokud se chcete vrátit k předchozímu kroku kurzu [, přečtěte si krok 7: Zachovat páry viditelné](../ide/step-7-keep-pairs-visible.md)
