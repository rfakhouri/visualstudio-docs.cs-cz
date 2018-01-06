---
title: "Krok 5: Přidejte obslužné rutiny události pro ovládací prvky NumericUpDown | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45a99a5d-c881-4298-b74d-adb481dec5ee
caps.latest.revision: "18"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a3d205dae6dd00ec5d763b9fb36f9c48041438ce
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="step-5-add-enter-event-handlers-for-the-numericupdown-controls"></a>Krok 5: Přidejte obslužné rutiny události pro ovládací prvky NumericUpDown
V páté části tohoto kurzu přidáte obslužné rutiny událostí Enter trochu usnadnění vstup odpovědi kvízu s časovým limitem problémů. Tento kód bude vyberte a zrušte aktuální hodnota v každém NumericUpDown – ovládací prvek, jakmile kvízu s časovým limitem příjemce rozhodne se a začne zadejte jinou hodnotu.  
  
> [!NOTE]
>  Toto téma je součástí série, kurz o základních konceptech kódování. Přehled kurzu, najdete v tématu [kurzu 2: vytvoření vypršel časový limit matematického kvízu](../ide/tutorial-2-create-a-timed-math-quiz.md).  
  
### <a name="to-verify-the-default-behavior"></a>Chcete-li ověřit výchozí chování  
  
1.  Spusťte svůj program a spusťte kvízu.  
  
     V ovládacím prvku NumericUpDown pro přidání problém bliká kurzor vedle **0** (nula).  
  
2.  Zadejte `3`a Všimněte si, že zobrazuje prvek **30**.  
  
3.  Zadejte `5`a Všimněte si, že **350** se zobrazí, ale změny **100** po druhé.  
  
     Než tento problém vyřešit, rozmyslete si, co se děje. Vezměte v úvahu důvod, proč **0** nebyla při jste zadali zmizí `3` a proč **350** změnit tak, aby **100** , ale ne hned.  
  
     Toto chování se může zdát liché, ale má smysl zadané logiku kódu. Pokud vyberete **spustit** tlačítko jeho **povoleno** je nastavena na **False**, a na tlačítko se zobrazí šedě a není k dispozici. Váš program změny ovládací prvek, který obsahuje další nejnižší hodnotu pořadové číslo prvku, která je pro problém přidání ovládacího prvku NumericUpDown aktuální výběr (aktivní). Při použití klávesy Tab přejdete do ovládacího prvku NumericUpDown, kurzor je automaticky nastavený na začátku ovládací prvek, který je důvod, proč čísla, která zadáte zobrazují na levé straně a není pravé straně. Pokud zadáte číslo, je vyšší než hodnota **MaximumValue** vlastnost, která je nastavena na hodnotu 100, číslo, které jste zadali se nahradí hodnotu této vlastnosti.  
  
### <a name="to-add-an-enter-event-handler-for-a-numericupdown-control"></a>Přidání obslužné rutiny události Enter ovládacího prvku NumericUpDown  
  
1.  Vyberte první NumericUpDown – ovládací prvek (s názvem "sum") na formuláři a potom v **vlastnosti** dialogovém okně vyberte **události** ikonu na panelu nástrojů.  
  
     **Události** ve **vlastnosti** dialogovém okně zobrazí všechny události, které mohou reagovat (zpracovat) pro položku, který zvolíte na formuláři. Protože jste zvolili ovládacího prvku NumericUpDown, všechny události uvedené týkají k němu.  
  
2.  Vyberte **Enter** událostí, zadejte `answer_Enter`a potom vyberte klávesu Enter.  
  
     ![Dialogové okno Vlastnosti](../ide/media/express_answerenter.png "Express_AnswerEnter")  
Dialogové okno Vlastnosti  
  
     Obslužné rutiny události Enter jste právě přidali pro součet NumericUpDown – ovládací prvek a jste s názvem obslužná rutina **answer_Enter**.  
  
3.  V metodě pro **answer_Enter** obslužné rutiny události, přidejte následující kód.  
  
     [!code-vb[VbExpressTutorial3Step5_6#11](../ide/codesnippet/VisualBasic/step-5-add-enter-event-handlers-for-the-numericupdown-controls_1.vb)]
     [!code-csharp[VbExpressTutorial3Step5_6#11](../ide/codesnippet/CSharp/step-5-add-enter-event-handlers-for-the-numericupdown-controls_1.cs)]  
  
     Tento kód bude vypadat složité, ale můžete porozumět, když se podíváte na jeho krok za krokem. Nejprve se podívejte na horní části metody: `object sender` v jazyce C# nebo `sender As System.Object` v jazyce Visual Basic. Tento parametr odkazuje na objekt, jehož událost se aktivuje, která se označuje jako odesílatele. V takovém případě objekt odesílatele je NumericUpDown – ovládací prvek. Ano v prvním řádku metody, určíte, že odesílatel není jen maskou pro jakýkoli obecný objekt ale konkrétně ovládacího prvku NumericUpDown. (Každých NumericUpDown – ovládací prvek je objekt, ale ne každý objekt je ovládacího prvku NumericUpDown.) Název ovládacího prvku NumericUpDown **answerBox** v této metodě, protože se použije pro všechny ovládací prvky NumericUpDown na formuláři, nejen součet NumericUpDown řízení. Protože je deklarovat proměnnou answerBox v této metodě, jeho obor platí pouze pro tuto metodu. Jinými slovy proměnné lze použít pouze v rámci této metody.  
  
     Na další řádek ověřuje, zda byl úspěšně převeden answerBox (cast) z objektu do ovládacího prvku NumericUpDown. Pokud byl převod úspěšné, proměnná by mít hodnotu `null` (C#) nebo `Nothing` (Visual Basic). Ve třetím řádku získá délku odpovědí, který se zobrazí v ovládacím prvku NumericUpDown a čtvrtý řádek vybere aktuální hodnota v ovládacím prvku podle této délky. Teď když příjemce kvízu s časovým limitem vybere ovládací prvek, Visual Studio aktivuje tuto událost, což způsobí, že aktuální odpovědí, aby byl vybrán. Jakmile příjemce kvízu s časovým limitem spustí k zadání odpovědi na jiný, předchozí odpověď, nahradí s novou odpověď.  
  
4.  V Návrháři formulářů zvolte rozdíl NumericUpDown – ovládací prvek.  
  
5.  V **události** stránky **vlastnosti** dialogové okno, posuňte se dolů **Enter** událostí, zvolte na šipku rozevíracího seznamu na konci řádku a pak `answer_Enter`obslužné rutiny události, kterou jste právě přidali.  
  
6.  Opakujte předchozí krok pro ovládací prvky NumericUpDown produktu a podílu.  
  
7.  Uložte program a potom ho spusťte.  
  
     Když zvolíte ovládacího prvku NumericUpDown, stávající hodnotu se vybere automaticky a pak vymazat při spuštění zadat jinou hodnotu.  
  
### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
-   Chcete-li přejít k dalšímu kroku kurzu, přečtěte si téma [krok 6: přidejte problém odečtení](../ide/step-6-add-a-subtraction-problem.md).  
  
-   Chcete-li vrátit k předchozímu kroku kurzu, přečtěte si téma [krok 4: Přidejte metodu CheckTheAnswer()](../ide/step-4-add-the-checktheanswer-parens-method.md).