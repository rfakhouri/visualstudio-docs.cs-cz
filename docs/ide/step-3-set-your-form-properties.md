---
title: 'Krok 3: Nastavení vlastností formuláře'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 634ef037-1525-48c8-ac7f-abf04be69376
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4e2742103585321b4f752a74e53253409e449bcf
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68918828"
---
# <a name="step-3-set-your-form-properties"></a>Krok 3: Nastavení vlastností formuláře
Dále pomocí okna **vlastnosti** změníte vzhled formuláře.

![odkaz na video](../data-tools/media/playvideo.gif)ve verzi videa tohoto tématu najdete v [kurzu 1: Vytvoření prohlížeče obrázků v Visual Basic-video 1](http://go.microsoft.com/fwlink/?LinkId=205209) nebo [kurz 1: Vytvoření prohlížeče obrázků ve C# videu 1.](http://go.microsoft.com/fwlink/?LinkId=205199) Tato videa používají starší verzi sady Visual Studio, takže existují mírné rozdíly v některých příkazech nabídky a dalších prvcích uživatelského rozhraní. Koncepty a postupy však fungují podobně v aktuální verzi sady Visual Studio.

## <a name="to-set-your-form-properties"></a>Nastavení vlastností formuláře

1. Ujistěte se, že se díváte na **Návrhář formulářů**. V integrovaném vývojovém prostředí (IDE) sady Visual Studio vyberte kartu **Form1.cs [Design]** (nebo kartu **Form1. vb [design]** v Visual Basic).

2. Zvolte libovolné místo uvnitř formuláře **Form1** a vyberte ho. Podívejte se na okno **vlastnosti** , ve kterém by se teď měly zobrazovat vlastnosti formuláře. Formuláře mají různé vlastnosti. Například můžete nastavit barvu popředí a pozadí, text nadpisu, který se zobrazí v horní části formuláře, velikost formuláře a další vlastnosti.

   > [!NOTE]
   > Pokud se okno **vlastnosti** nezobrazí, ukončete program výběrem čtvercového tlačítka **Zastavit ladění** na panelu nástrojů nebo pouze zavřít okno. Pokud je program zastaven a stále nevidíte okno **vlastnosti** , v řádku nabídek vyberte možnost **Zobrazit** > **okno vlastností**.

3. Po výběru formuláře vyhledejte vlastnost **text** v okně **vlastnosti** . V závislosti na tom, jak je seznam seřazený, se možná budete muset posunout dolů. Zvolte **text**, zadejte **Prohlížeč obrázků**a pak zvolte **ENTER**.  Formulář by měl mít nyní v záhlaví text **Viewer** a okno **vlastnosti** by mělo vypadat podobně jako na následujícím obrázku.

    ![Okno](../ide/media/express_edittextproperty.png)
   **vlastností** okno Vlastnosti

   > [!NOTE]
   > Vlastnosti lze seřadit podle **kategorií** nebo zobrazení podle **abecedy** . Mezi těmito dvěma zobrazeními můžete přepínat pomocí tlačítek v okně **vlastnosti** . V tomto kurzu je snazší najít vlastnosti pomocí abecedního zobrazení.

4. Vraťte se na **Návrhář formulářů**. Vyberte táhlo v pravém dolním rohu formuláře, což je malé bílé čtverce v pravém dolním rohu formuláře a zobrazí se takto.

    ![Úchyt pro](../ide/media/express_bottomrt_drag.png) přetažení úchytu

    Přetažením úchytu můžete změnit velikost formuláře, takže je formulář širší a trochu vyšší.

5. Podívejte se na okno **vlastnosti** a Všimněte si, že se změnila vlastnost **Size** . Vlastnost **Size** se změní pokaždé, když změníte velikost formuláře. Zkuste přetáhnout táhlo formuláře, aby se změnila velikost formuláře přibližně **550, 350** (není potřeba přesně), což by mělo pro tento projekt dobře fungovat. Alternativně můžete zadat hodnoty přímo do vlastnosti **Size** a pak zvolit klávesu **ENTER** .

6. Spusťte program znovu. Nezapomeňte, že ke spuštění programu můžete použít kteroukoli z následujících metod.

   - Klikněte na klávesu **F5** .

   - Na panelu nabídek vyberte **ladit** > **Spustit ladění**.

   - Na panelu nástrojů klikněte na tlačítko **Spustit ladění** , které se zobrazí takto.

      ![Spustit ladění – tlačítko](../ide/media/express_icondebug.png)
     panelu nástrojů**Spustit ladění** – tlačítko panelu nástrojů

     Stejně jako předtím, rozhraní IDE sestaví a spustí program a zobrazí se okno.

7. Než budete pokračovat k dalšímu kroku, zastavte program, protože rozhraní IDE vám neumožní změnit program, pokud je spuštěný. Nezapomeňte, že k zastavení programu můžete použít kteroukoli z následujících metod.

   - Na panelu nástrojů klikněte na tlačítko **Zastavit ladění** .

   - Na řádku nabídek klikněte na položku **ladit** > **Zastavit ladění**.

   - Klikněte na tlačítko **X** v horním rohu okna **Form1** .

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Pokud chcete přejít na další krok kurzu, přečtěte si [krok 4: Rozložte formulář pomocí ovládacího prvku](../ide/step-4-lay-out-your-form-with-a-tablelayoutpanel-control.md)TableLayoutPanel.

- Pokud se chcete vrátit k předchozímu kroku kurzu [, přečtěte si článek krok 2: Spusťte program](../ide/step-2-run-your-program.md).
