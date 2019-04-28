---
title: 'Krok 5: Přidání obslužné rutiny událostí Enter pro ovládací prvky NumericUpDown'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 45a99a5d-c881-4298-b74d-adb481dec5ee
author: TerryGLee
ms.author: tglee
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 194988a3d21078ebb712afee52d9106659b65b14
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62997312"
---
# <a name="step-5-add-enter-event-handlers-for-the-numericupdown-controls"></a>Krok 5: Přidání obslužné rutiny událostí Enter pro ovládací prvky NumericUpDown

V páté části tohoto tutoriálu přidáte <xref:System.Windows.Forms.Control.Enter> obslužných rutin událostí k zadávání odpovědi pro kvíz trochu snazší. Tento kód vybere a vymaže aktuální hodnotu v každém <xref:System.Windows.Forms.NumericUpDown> řízení co nejdříve, kvízu vybere a začne zadávat jinou hodnotu.

> [!NOTE]
> Toto téma je součástí série kurzů o základních principech kódování. Přehled kurzu, naleznete v tématu [kurz 2: Vytvoření matematického kvízu](../ide/tutorial-2-create-a-timed-math-quiz.md).

## <a name="to-verify-the-default-behavior"></a>Ověření výchozího chování

1. Spusťte program a spusťte kvíz.

     V **NumericUpDown** ovládací prvek pro úlohu sčítání, bliká kurzor vedle **0** (nula).

2. Zadejte **3**a Všimněte si, že ovládací prvek zobrazuje **30**.

3. Zadejte **5**a Všimněte si, že **350** se zobrazí, ale změny **100** po druhém.

     Než vyřešíte tento problém, rozmyslete si, co se děje. Zvažte, proč **0** nezmizela poté zadáte **3** a proč **350** změněn na **100** , ale nikoliv okamžitě.

     Toto chování se může zdát neobvyklé, ale dává smysl s ohledem logiku kódu. Při výběru možnosti **Start** tlačítko, jeho **povoleno** je nastavena na **False**, a tlačítko se zobrazí šedě a není k dispozici. Váš program změní aktuální výběr (Přepne fokus) na ovládací prvek s další nejnižší hodnotou TabIndex, což je ovládací prvek NumericUpDown pro úlohu sčítání. Při použití **kartu** klíče go na ovládací prvek NumericUpDown, se automaticky kurzor na začátek ovládacího prvku, což je důvod, proč čísla, která zadáte budou zobrazovat v levé straně a nikoli vpravo. Pokud zadáte číslo vyšší než hodnota **MaximumValue** vlastnost, která je nastavena na hodnotu 100, číslo, které jste zadali je nahrazena hodnotou této vlastnosti.

## <a name="to-add-an-enter-event-handler-for-a-numericupdown-control"></a>Chcete-li přidat obslužné rutiny událostí Enter pro ovládací prvek NumericUpDown

1. Zvolte první **NumericUpDown** ovládací prvek (s názvem "SUMA") ve formuláři a potom v **vlastnosti** dialogového okna zvolte **události** ikonu na panelu nástrojů.

   ![Události tlačítko v panelu nástrojů Vlastnosti](media/control-properties-events.png)

   **Události** kartu **vlastnosti** dialogové okno zobrazí všechny události, které můžete reagovat (zpracovat) pro položku, kterou zvolíte ve formuláři. Vzhledem k tomu, že jste zvolili ovládací prvek NumericUpDown, přísluší všechny uvedené události k němu.

2. Zvolte **Enter** událost, typ `answer_Enter`a potom stiskněte klávesu **Enter** klíč.

   ![Zadejte název metody obslužné rutiny události](media/enter-event.png)

   Právě jste přidali obslužné rutiny událostí Enter pro součtový ovládací prvek NumericUpDown a pojmenovali jste obslužnou rutinu **answer_Enter**.

3. V metodě pro **answer_Enter** obslužná rutina události, přidejte následující kód:

     [!code-vb[VbExpressTutorial3Step5_6#11](../ide/codesnippet/VisualBasic/step-5-add-enter-event-handlers-for-the-numericupdown-controls_1.vb)]
     [!code-csharp[VbExpressTutorial3Step5_6#11](../ide/codesnippet/CSharp/step-5-add-enter-event-handlers-for-the-numericupdown-controls_1.cs)]

     Tento kód může vypadat složité, ale lze jej pochopit, když se podíváte na něj krok za krokem. Nejprve se podívejte na horní část metody: `object sender` v jazyce C# nebo `sender As System.Object` v jazyce Visual Basic. Tento parametr odkazuje na objekt, jehož událost je vyvolávána, který je znám jako odesílatel. V takovém případě objekt odesílatel je ovládací prvek NumericUpDown. V prvním řádku metody, tedy zadáte, že odesílatel není pouze obecný objekt, ale specificky ovládací prvek NumericUpDown. (Každý ovládací prvek NumericUpDown je objekt, ale ne každý objekt je ovládací prvek NumericUpDown.) NumericUpDown – ovládací prvek má název **answerBox** v této metodě, protože se použije pro všechny ovládací prvky NumericUpDown ve formuláři, nikoli pouze pro součtový ovládací prvek. Vzhledem k tomu, že deklarujete proměnnou answerBox v této metodě, její obor platí pouze pro tuto metodu. Jinými slovy proměnné lze použít pouze v rámci této metody.

     Další řádek ověří, zda byl answerBox úspěšně převeden (přetypován) z objektu na NumericUpDown ovládací prvek. Pokud převod neúspěšný, proměnné by mít hodnotu `null` (C#) nebo `Nothing` (Visual Basic). Třetí řádek získá délku odpovědi, která se zobrazí v ovládacím prvku NumericUpDown, a čtvrtý řádek vybere aktuální hodnotu v ovládacím prvku v závislosti na této délce. Nyní když kvízu vybere ovládací prvek, sady Visual Studio vyvolá tuto událost, což způsobí, že aktuální odpovědi má být vybrán. Jakmile kvízu začne zadávat různé odpovědi, předchozí odpověď je vymazána a nahrazena novou odpovědí.

4. V **Návrháře formulářů Windows**, tlačítko rozdíl **NumericUpDown** ovládacího prvku.

5. V **události** stránce **vlastnosti** dialogové okno, posuňte se dolů **Enter** události, klikněte na šipku rozevíracího seznamu na konci řádku a klikněte na tlačítko `answer_Enter`obslužná rutina události, který jste právě přidali.

6. Opakujte předchozí krok pro násobící a podílové ovládací prvky NumericUpDown.

7. Uložte program a spusťte jej.

     Při výběru **NumericUpDown** je ovládací prvek, existující hodnota automaticky vybrána a potom vymazána po spuštění zadat jiné hodnoty.

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 6: Přidejte problém odečtení](../ide/step-6-add-a-subtraction-problem.md).

- Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 4: Přidejte metodu CheckTheAnswer()](../ide/step-4-add-the-checktheanswer-parens-method.md).
