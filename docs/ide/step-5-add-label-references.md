---
title: "Krok 5: Přidejte odkazy na jmenovky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d418350c-0396-494e-8149-71fa61b395c5
caps.latest.revision: "20"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: f353693fe407600b7ed009e611600a8b42c7713d
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="step-5-add-label-references"></a>Krok 5: Přidejte odkazy na jmenovky
Program potřebuje udržovat přehled o tom, který ovládací prvek popisku hráč zvolil. Nyní program zobrazí všechny popisky, které hráč zvolí. Ale to změníme. Po výběru prvního popisku by program měl zobrazit ikonu popisku. Po výběru druhého popisku by program měl krátce zobrazit obě ikony a pak je opět skrýt. Váš program bude nyní uchovávání informací o které popisek – ovládací prvek je zvolen nejprve a který je zvolen sekundu pomocí *referenční proměnné*.  
  
### <a name="to-add-label-references"></a>Přidání odkazů popisků  
  
1.  Pomocí následujícího kódu přidejte do formuláře odkazy popisku.  
  
     [!code-vb[VbExpressTutorial4Step5#5](../ide/codesnippet/VisualBasic/step-5-add-label-references_1.vb)]
     [!code-csharp[VbExpressTutorial4Step5#5](../ide/codesnippet/CSharp/step-5-add-label-references_1.cs)]  
  
     Tyto proměnné odkaz vypadat podobně jako příkazy, které jste použili předtím přidat objekty (například `Timer` objekty, `List` objekty, a `Random` objekty) do svého formuláře. Ale tyto příkazy nezpůsobí dvou ovládacích prvků popisek navíc se objevily na formulář, protože není žádná `new` klíčové slovo používané v některém ze dvou příkazů. Bez `new` – klíčové slovo, je vytvořen žádný objekt. To je důvod, proč `firstClicked` a `secondClicked` nazývají referenční proměnné: se právě zaznamenávat (nebo, prostudujte si) `Label` objekty.  
  
     Když proměnné není udržování přehledu o objekt, je nastavena na hodnotu speciální vyhrazené: `null` v jazyce Visual C# a `Nothing` v jazyce Visual Basic. Ano, při spuštění programu, i `firstClicked` a `secondClicked` jsou nastaveny na `null` nebo `Nothing`, což znamená, že proměnné neudržují přehled o ničem.  
  
2.  Upravit vaše obslužnou rutinu události kliknutí použití nového `firstClicked` odkaz na proměnnou. Odebrat poslední příkaz v `label_Click()` metoda obslužné rutiny události (`clickedLabel.ForeColor = Color.Black;`) a nahraďte ho `if` příkaz, který následuje dále. (Ujistěte se, zahrnete komentář a veškeré `if` příkaz.)  
  
     [!code-vb[VbExpressTutorial4Step5#6](../ide/codesnippet/VisualBasic/step-5-add-label-references_2.vb)]
     [!code-csharp[VbExpressTutorial4Step5#6](../ide/codesnippet/CSharp/step-5-add-label-references_2.cs)]  
  
3.  Uložte program a spusťte jej. Vyberte jeden z ovládacích prvků popisku a zobrazí se jeho ikona.  
  
4.  Vyberte další ovládací prvek popisku a všimněte si, že se nic nestane. Tento program je již udržování přehledu o první štítek, pro který zvolili přehrávač, tak `firstClicked` není rovno `null` v jazyce Visual C# nebo `Nothing` v jazyce Visual Basic. Při vaší `if` příkaz kontroly `firstClicked` Chcete-li zjistit, jestli je rovno `null` nebo `Nothing`, se zjistí, že není a neprovede příkazy v `if` příkaz. Takže pouze první ikona, která je vybrána, zčerná a další ikony jsou skryté, jak je znázorněno na následujícím obrázku.  
  
     ![Odpovídající herní zobrazující jednu ikonu](../ide/media/express_tut4step5.png "Express_Tut4Step5")  
Porovnávací hra zobrazující jednu ikonu  
  
     Tuto situaci v dalším kroku kurzu budete opravte přidáním **časovače** ovládacího prvku.  
  
### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
-   Chcete-li přejít k dalšímu kroku kurzu, přečtěte si téma [krok 6: přidejte časovač](../ide/step-6-add-a-timer.md).  
  
-   Pokud chcete vrátit do předchozího kroku kurzu, najdete v části [krok 4: přidejte obslužné rutiny události Click na každý štítek](../ide/step-4-add-a-click-event-handler-to-each-label.md).