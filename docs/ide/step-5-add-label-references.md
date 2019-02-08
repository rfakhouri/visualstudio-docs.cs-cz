---
title: 'Krok 5: Přidejte odkazy na jmenovky'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d418350c-0396-494e-8149-71fa61b395c5
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5b9d6e2786b2d917348818134c9e1cbe2767f7fb
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55934338"
---
# <a name="step-5-add-label-references"></a>Krok 5: Přidejte odkazy na jmenovky
Program je potřeba sledovat, jaké ovládací prvky popisku hráč zvolí. Nyní program zobrazí všechny popisky, které hráč zvolí. Ale to změníme. Po výběru prvního popisku by program měl zobrazit ikonu popisku. Po výběru druhého popisku by program měl krátce zobrazit obě ikony a pak je opět skrýt. Váš program bude nyní sledovat, který ovládací prvek popisku je vybrán jako první a který jako druhý pomocí *referenční proměnné*.

## <a name="to-add-label-references"></a>Přidání odkazů popisků

1.  Pomocí následujícího kódu přidejte do formuláře odkazy popisku.

     [!code-vb[VbExpressTutorial4Step5#5](../ide/codesnippet/VisualBasic/step-5-add-label-references_1.vb)]
     [!code-csharp[VbExpressTutorial4Step5#5](../ide/codesnippet/CSharp/step-5-add-label-references_1.cs)]

     Tyto referenční proměnné vypadají podobně jako příkazy, které jste použili dříve k přidání objektů (například <xref:System.Windows.Forms.Timer> objekty, <xref:System.Collections.Generic.List%601> objekty, a <xref:System.Random> objekty) do svého formuláře. Tyto příkazy však nezpůsobí dvě další ovládací prvky Label zobrazí ve formuláři, protože neexistuje žádný `new` klíčové slovo používané v obou dvou příkazech. Bez `new` – klíčové slovo, není vytvořen žádný objekt. To je důvod, proč `firstClicked` a `secondClicked` nazývají referenční proměnné: Jsou pouze sledovat (nebo odkazovat na) označovat objekty.

     Pokud proměnná není udržování přehledu o objektu, je nastavena na speciální vyhrazenou hodnotu: `null` v jazyce Visual C# a `Nothing` v jazyce Visual Basic. Proto při spuštění programu, obě `firstClicked` a `secondClicked` jsou nastaveny na `null` nebo `Nothing`, což znamená, že proměnné neudržují přehled o ničem.

2.  Upravit vaše <xref:System.Windows.Forms.Control.Click> obslužné rutiny události s novým `firstClicked` odkaz na proměnnou. Odebrat poslední příkaz v `label_Click()` metoda obslužné rutiny události (`clickedLabel.ForeColor = Color.Black;`) a nahraďte ho hodnotou `if` příkazu, který následuje. (Nezapomeňte zahrnout komentář a celý `if` příkazu.)

     [!code-vb[VbExpressTutorial4Step5#6](../ide/codesnippet/VisualBasic/step-5-add-label-references_2.vb)]
     [!code-csharp[VbExpressTutorial4Step5#6](../ide/codesnippet/CSharp/step-5-add-label-references_2.cs)]

3.  Uložte program a spusťte jej. Vyberte jeden z ovládacích prvků popisku a zobrazí se jeho ikona.

4.  Vyberte další ovládací prvek popisku a všimněte si, že se nic nestane. Program je již udržuje přehled o prvním popisku, který hráč vybral, takže `firstClicked` není roven `null` v jazyce Visual C# nebo `Nothing` v jazyce Visual Basic. Při vaší `if` příkaz kontroly `firstClicked` k určení, zda je rovna `null` nebo `Nothing`, zjistí, že není a neprovede příkazy v `if` příkazu. Takže pouze první ikona, která je vybrána, zčerná a další ikony jsou skryté, jak je znázorněno na následujícím obrázku.

     ![Odpovídající hra zobrazující jednu ikonu](../ide/media/express_tut4step5.png)
**Porovnávací hra** zobrazující jednu ikonu

     Můžete tuto situaci opravíte v dalším kroku kurzu tak, že přidáte **časovače** ovládacího prvku.

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

-   Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 6: Přidejte časovač](../ide/step-6-add-a-timer.md).

-   Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 4: Přidejte k jednotlivým jmenovkám obslužnou rutinu události Click](../ide/step-4-add-a-click-event-handler-to-each-label.md).
