---
title: 'Krok 7: Uchovejte páry ve viditelném stavu'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 42e1d08c-7b2e-4efd-9f47-85d6206afe35
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0373a4d51c6da6685d3fc837b569607daa059854
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="step-7-keep-pairs-visible"></a>Krok 7: Uchovejte páry ve viditelném stavu
Hra funguje dobře tak dlouho, dokud hráč vybírá pouze dvojice ikon, které neodpovídají. Ale zvažte, co by mělo nastat, pokud hráč vybere shodnou dvojici. Namísto provádění ikony zmizí zapnutím časovač (pomocí `Start()` metoda), hra musí resetovat, tak, aby ho je už udržování přehledu o štítků, které používají `firstClicked` a `secondClicked` referenční proměnné, bez resetování barvy pro dva popisky, které byly.  

### <a name="to-keep-pairs-visible"></a>Zachování dvojic viditelných  

1.  Přidejte následující `if` příkaz, který má `label_Click()` metoda obslužné rutiny události u konce kód nad příkaz, kde spustit časovač. Při přidávání do programu si kód pořádně prohlédněte. Zamyslete se nad tím, jak kód funguje.  

     [!code-csharp[VbExpressTutorial4Step7#9](../ide/codesnippet/CSharp/step-7-keep-pairs-visible_1.cs)]
     [!code-vb[VbExpressTutorial4Step7#9](../ide/codesnippet/VisualBasic/step-7-keep-pairs-visible_1.vb)]  

     První řádek `if` příkaz jste právě přidali zkontroluje, zda na ikonu v první štítek, který vybere přehrávač je stejné jako na ikonu v druhé popisku. Pokud jsou identické ikony, program provede tři příkazy ve složených závorkách v C# nebo tři příkazy v `if` v jazyce Visual Basic. První dva příkazy resetují `firstClicked` a `secondClicked` referenční proměnné tak, aby se už udržování přehledu o štítků. (Tyto dva příkazy si možná pamatujete z obslužné rutiny události časovače Tick.) Je třetí příkaz `return` příkaz, který říká přeskočte zbytek příkazy v metodě bez jejich spuštění programu.  

     Pokud programování v jazyce Visual C#, může dojít k tomu, že některé kód používá jeden symbol rovná se (`=`), zatímco jiné příkazy používají dva symboly rovná se (`==`). Vezměte v úvahu důvod, proč `=` se používá v některých místech, ale `==` se používá v jiných míst.  

     Toto je typický příklad, který ukazuje rozdíl. Pozor, prohlédněte si kód v závorkách v `if` příkaz.  

    ```vb  
    firstClicked.Text = secondClicked.Text  
    ```  

    ```csharp  
    firstClicked.Text == secondClicked.Text  
    ```  

     Zkontrolujte pečlivě první příkaz v bloku kódu po `if` příkaz.  

    ```vb  
    firstClicked = Nothing  
    ```  

    ```csharp  
    firstClicked = null;  
    ```  

     První z těchto dvou příkazů ověří, zda jsou dvě ikony stejné. Vzhledem k tomu, že se porovnání dvou hodnot, používá programu Visual C# `==` operátor rovnosti. Druhý příkaz skutečně změní hodnotu (nazývá *přiřazení*), nastavení `firstClicked` odkaz na proměnnou rovna `null` ho resetovat. To je důvod, proč se používá `=` operátor přiřazení místo. Visual C# používá `=` nastavit hodnoty, a `==` k porovnání je. Visual Basic používá `=` pro porovnání a přiřazení proměnné.  

2.  Uložte a spusťte program a začněte vybírat ikony ve formuláři. Pokud zvolíte dvojici, která neodpovídá, událost časovače Tick se aktivuje a obě ikony zmizí. Pokud se rozhodnete pár odpovídající nové `if` příkaz provede, a příkaz return způsobí, že metoda přeskočit kód, který spustí časovač, takže ikony zůstanou viditelné, jak je znázorněno na následujícím obrázku.  

     ![Herní, který vytvoříte v tomto kurzu](../ide/media/express_finishedgame.png "Express_FinishedGame")  
Porovnávací hra se zobrazenými dvojicemi ikon  

### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  

-   Chcete-li přejít k dalšímu kroku kurzu, přečtěte si téma [krok 8: Přidejte metodu k ověřte, zda hráč vyhrál](../ide/step-8-add-a-method-to-verify-whether-the-player-won.md).  

-   Chcete-li vrátit k předchozímu kroku kurzu, přečtěte si téma [krok 6: přidejte časovač](../ide/step-6-add-a-timer.md).
