---
title: 'Krok 3: Nastavení vlastností formuláře'
ms.date: 08/30/2019
ms.assetid: 634ef037-1525-48c8-ac7f-abf04be69376
ms.topic: tutorial
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
ms.devlang:
- csharp
- vb
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 123a843676a7562478710bf607f62c92743c462d
ms.sourcegitcommit: 9c07ae6fb18204ea080c8248994a683fa12e5c82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/04/2019
ms.locfileid: "70293580"
---
# <a name="step-3-set-your-form-properties"></a>Krok 3: Nastavení vlastností formuláře

Dále pomocí okna **vlastnosti** změníte vzhled formuláře.

## <a name="how-to-set-your-form-properties"></a>Nastavení vlastností formuláře

1. Ujistěte se, že se díváte na **Návrhář formulářů**. V integrovaném vývojovém prostředí (IDE) sady Visual Studio vyberte kartu **Form1.cs [Design]** (nebo kartu **Form1. vb [design]** v Visual Basic).

1. Zvolte libovolné místo uvnitř formuláře **Form1** a vyberte ho. Podívejte se na okno **vlastnosti** , ve kterém by se teď měly zobrazovat vlastnosti formuláře. Formuláře mají různé vlastnosti. Například můžete nastavit barvu popředí a pozadí, text nadpisu, který se zobrazí v horní části formuláře, velikost formuláře a další vlastnosti.

   > [!NOTE]
   > Pokud se okno **vlastnosti** nezobrazí, ukončete program výběrem čtvercového tlačítka **Zastavit ladění** na panelu nástrojů nebo pouze zavřít okno. Pokud je program zastaven a stále nevidíte okno **vlastnosti** , v řádku nabídek vyberte možnost **Zobrazit** > **okno vlastností**.

1. Po výběru formuláře vyhledejte vlastnost **text** v okně **vlastnosti** . V závislosti na tom, jak je seznam seřazený, se možná budete muset posunout dolů. Zvolte **text**, zadejte **Prohlížeč obrázků**a pak zvolte **ENTER**.  Formulář by měl mít nyní v záhlaví text **Viewer** a okno **vlastnosti** by mělo vypadat podobně jako na následujícím snímku obrazovky.

    ![okno Vlastnosti](../ide/media/express_edittextproperty.png)<br>
   ***Vlastnosti*** *okno*

   > [!NOTE]
   > Vlastnosti lze seřadit podle **kategorií** nebo zobrazení podle **abecedy** . Mezi těmito dvěma zobrazeními můžete přepínat pomocí tlačítek v okně **vlastnosti** . V tomto kurzu je snazší najít vlastnosti pomocí **abecedního** zobrazení.

1. Vraťte se na **Návrhář formulářů**. Vyberte táhlo v pravém dolním rohu formuláře, což je malé bílé čtverce v pravém dolním rohu formuláře a zobrazí se takto.

    ![Přetáhněte popisovač](../ide/media/express_bottomrt_drag.png)<br>
   *Přetáhněte popisovač*

    Přetažením úchytu můžete změnit velikost formuláře, takže je formulář širší a trochu vyšší.

1. Podívejte se na okno **vlastnosti** a Všimněte si, že se změnila vlastnost **Size** . Vlastnost **Size** se změní pokaždé, když změníte velikost formuláře. Zkuste přetáhnout táhlo formuláře, aby se změnila velikost formuláře přibližně **550, 350** (není potřeba přesně), což by mělo pro tento projekt dobře fungovat. Alternativně můžete zadat hodnoty přímo do vlastnosti **Size** a pak zvolit klávesu **ENTER** .

1. Spusťte program znovu. Nezapomeňte, že ke spuštění programu můžete použít kteroukoli z následujících metod.

   - Klikněte na klávesu **F5** .

   - Na panelu nabídek vyberte **ladit** > **Spustit ladění**.

   - Na panelu nástrojů klikněte na tlačítko **Spustit ladění** , které se zobrazí takto.

      ![Spustit ladění – tlačítko panelu nástrojů](../ide/media/express_icondebug.png)<br>
     ***Spustit ladění*** *tlačítko panelu nástrojů*

     Stejně jako předtím, rozhraní IDE sestaví a spustí program a zobrazí se okno.

1. Než budete pokračovat k dalšímu kroku, zastavte program, protože rozhraní IDE vám neumožní změnit program, pokud je spuštěný. Nezapomeňte, že k zastavení programu můžete použít kteroukoli z následujících metod.

   - Na panelu nástrojů klikněte na tlačítko **Zastavit ladění** .

   - Na řádku nabídek klikněte na položku **ladit** > **Zastavit ladění**.

   - Použijte klávesnici a stiskněte **SHIFT**+**F5**.

   - V horním rohu okna **Prohlížeč obrázků** klikněte na tlačítko **X** .

## <a name="next-steps"></a>Další postup

* Pokud chcete přejít na další krok kurzu, přečtěte si [krok 4: Rozložte formulář pomocí ovládacího prvku](../ide/step-4-lay-out-your-form-with-a-tablelayoutpanel-control.md)TableLayoutPanel.

* Pokud se chcete vrátit k předchozímu kroku kurzu [, přečtěte si článek krok 2: Spusťte program](../ide/step-2-run-your-program.md).

## <a name="see-also"></a>Viz také:

* [Kurz 2: Vytvoření časovaného matematického kvízu](tutorial-2-create-a-timed-math-quiz.md)
* [Kurz 3: Vytvořit porovnávací hru](tutorial-3-create-a-matching-game.md)
