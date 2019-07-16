---
title: 'Krok 8: Přidejte metodu k ověření, zda hráč zvítězil | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 6e317f6e-ba4c-4306-8924-300b0c2f65c6
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d4198d9a575f4ab2add48d08994d5d48392f23a1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68178613"
---
# <a name="step-8-add-a-method-to-verify-whether-the-player-won"></a>Krok 8: Přidání metody k ověření, jestli hráč vyhrál
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Vytvořili jste zábavnou hru, která však potřebuje ještě něco. Hra by měla skončit vítězstvím hráče, takže budete muset přidat `CheckForWinner()` metodu k ověření, zda hráč zvítězil.  
  
### <a name="to-add-a-method-to-verify-whether-the-player-won"></a>Přidání metody k ověření, zda hráč zvítězil  
  
1. Přidat `CheckForWinner()` metoda do dolní části kódu, níže `timer1_Tick()` obslužná rutina události, jak je znázorněno v následujícím kódu.  
  
     [!code-csharp[VbExpressTutorial4Step8#10](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial4step8/cs/form1.cs#10)]
     [!code-vb[VbExpressTutorial4Step8#10](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial4step8/vb/form1.vb#10)]  
  
     Metoda používá další `foreach` smyčky v jazyce Visual C# nebo `For Each` smyčky v jazyce Visual Basic k projití každého popisku v kontejneru TableLayoutPanel. Používá operátor rovnosti (`==` v jazyce Visual C# a `=` v jazyce Visual Basic) ke kontrole barvy ikony každého popisku k ověření, zda odpovídá pozadí. Pokud se barvy shodují, zůstane ikona skryta a hráč nespároval všechny zbývající ikony. V takovém případě program použije `return` příkaz k vynechání zbývající metody. Pokud smyčka projde přes všechny popisky bez spuštění `return` příkazu, to znamená, že všechny ikony ve formuláři byly spárovány. Program zobrazí prvek MessageBox s blahopřáním k vítězství a pak zavolá formuláře `Close()` metoda k ukončení hry.  
  
2. Dále nechejme popisku klikněte na tlačítko zavolat novou obslužnou rutinu události `CheckForWinner()` metody. Ujistěte se, že váš program kontroluje vítěze ihned po tom, co zobrazí druhou ikonu, kterou hráč vybere. Vyhledejte řádek, kde jste nastavili barvu druhé vybrané ikony a poté zavolejte `CheckForWinner()` metodu, jak je znázorněno v následujícím kódu.  
  
     [!code-csharp[VbExpressTutorial4Step8#11](../snippets/csharp/VS_Snippets_VBCSharp/vbexpresstutorial4step8/cs/form1.cs#11)]
     [!code-vb[VbExpressTutorial4Step8#11](../snippets/visualbasic/VS_Snippets_VBCSharp/vbexpresstutorial4step8/vb/form1.vb#11)]  
  
3. Program uložte a spusťte jej. Zahrajte si hru a spárujte všechny ikony. Když vyhrajete, program zobrazí prvek MessageBox s blahopřáním (jak je ukázáno na následujícím obrázku) a potom jej zavře.  
  
     ![Porovnávací hra s ovládacím prvkem MessageBox](../ide/media/express-tut4step8.png "Express_Tut4Step8")  
Porovnávací hra s ovládacím prvkem MessageBox  
  
### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
- Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 9: Vyzkoušejte další funkce](../ide/step-9-try-other-features.md).  
  
- Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 7: Zachování dvojic viditelných](../ide/step-7-keep-pairs-visible.md).
