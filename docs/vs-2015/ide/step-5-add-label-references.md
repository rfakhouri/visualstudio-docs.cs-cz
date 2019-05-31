---
title: 'Krok 5: Přidejte odkazy na jmenovky | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: d418350c-0396-494e-8149-71fa61b395c5
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 3f062b48edfbe87fb97d94b3ea852486f66a19d1
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60041870"
---
# <a name="step-5-add-label-references"></a>Krok 5: Přidání odkazů popisků
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Program potřebuje udržovat přehled o tom, který ovládací prvek popisku hráč zvolil. Nyní program zobrazí všechny popisky, které hráč zvolí. Ale to změníme. Po výběru prvního popisku by program měl zobrazit ikonu popisku. Po výběru druhého popisku by program měl krátce zobrazit obě ikony a pak je opět skrýt. Váš program bude nyní sledovat, který ovládací prvek popisku je vybrán jako první a který jako druhý pomocí *referenční proměnné*.  
  
### <a name="to-add-label-references"></a>Přidání odkazů popisků  
  
1. Pomocí následujícího kódu přidejte do formuláře odkazy popisku.  
  
     [!code-csharp[VbExpressTutorial4Step5#5](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial4step5/cs/form1.cs#5)]
     [!code-vb[VbExpressTutorial4Step5#5](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial4step5/vb/form1.vb#5)]  
  
     Tyto referenční proměnné vypadají podobně jako příkazy, které jste použili dříve k přidání objektů (například `Timer` objekty, `List` objekty, a `Random` objekty) do svého formuláře. Tyto příkazy však nezpůsobí dva další ovládací prvky label zobrazí ve formuláři, protože neexistuje žádný `new` klíčové slovo používané v obou dvou příkazech. Bez `new` – klíčové slovo, není vytvořen žádný objekt. To je důvod, proč `firstClicked` a `secondClicked` nazývají referenční proměnné: Jsou pouze sledovat (nebo odkazovat na) `Label` objekty.  
  
     Pokud proměnná není udržování přehledu o objektu, je nastavena na speciální vyhrazenou hodnotu: `null` v jazyce Visual C# a `Nothing` v jazyce Visual Basic. Proto při spuštění programu, obě `firstClicked` a `secondClicked` jsou nastaveny na `null` nebo `Nothing`, což znamená, že proměnné neudržují přehled o ničem.  
  
2. Upravit vaší obslužné rutiny události kliknutí na použití nové `firstClicked` odkaz na proměnnou. Odebrat poslední příkaz v `label_Click()` metoda obslužné rutiny události (`clickedLabel.ForeColor = Color.Black;`) a nahraďte ho hodnotou `if` příkazu, který následuje. (Nezapomeňte zahrnout komentář a celý `if` příkazu.)  
  
     [!code-csharp[VbExpressTutorial4Step5#6](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial4step5/cs/form1.cs#6)]
     [!code-vb[VbExpressTutorial4Step5#6](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial4step5/vb/form1.vb#6)]  
  
3. Uložte program a spusťte jej. Vyberte jeden z ovládacích prvků popisku a zobrazí se jeho ikona.  
  
4. Vyberte další ovládací prvek popisku a všimněte si, že se nic nestane. Program je již udržuje přehled o prvním popisku, který hráč vybral, takže `firstClicked` není roven `null` v jazyce Visual C# nebo `Nothing` v jazyce Visual Basic. Při vaší `if` příkaz kontroly `firstClicked` k určení, zda je rovna `null` nebo `Nothing`, zjistí, že není a neprovede příkazy v `if` příkazu. Takže pouze první ikona, která je vybrána, zčerná a další ikony jsou skryté, jak je znázorněno na následujícím obrázku.  
  
     ![Porovnávací hra zobrazující jednu ikonu](../ide/media/express-tut4step5.png "Express_Tut4Step5")  
Porovnávací hra zobrazující jednu ikonu  
  
     Můžete tuto situaci opravíte v dalším kroku kurzu tak, že přidáte **časovače** ovládacího prvku.  
  
### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
- Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 6: Přidejte časovač](../ide/step-6-add-a-timer.md).  
  
- Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 4: Přidejte k jednotlivým jmenovkám obslužnou rutinu události Click](../ide/step-4-add-a-click-event-handler-to-each-label.md).
