---
title: 'Krok 7: Zachování dvojic viditelných'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 42e1d08c-7b2e-4efd-9f47-85d6206afe35
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 05baa302c2ead99c5c337f4cde71c3d2e025bfb0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62996299"
---
# <a name="step-7-keep-pairs-visible"></a>Krok 7: Zachování dvojic viditelných
Hra funguje dobře tak dlouho, dokud hráč vybírá pouze dvojice ikon, které neodpovídají. Ale zvažte, co by mělo nastat, pokud hráč vybere shodnou dvojici. Namísto nastavení zmizení ikon zapnutím časovače (pomocí <xref:System.Windows.Forms.Timer.Start> metoda), hra měla resetovat sama tak, aby ho je už neudržují přehled o popisky pomocí `firstClicked` a `secondClicked` referenční proměnné bez resetování barev dvou popisků, které byly vybrány.

## <a name="to-keep-pairs-visible"></a>Zachování dvojic viditelných

1. Přidejte následující `if` příkazu `label_Click()` metoda obslužné rutiny události poblíž konce kódu těsně nad příkazem, kde spouštíte časovač. Při přidávání do programu si kód pořádně prohlédněte. Zamyslete se nad tím, jak kód funguje.

     [!code-csharp[VbExpressTutorial4Step7#9](../ide/codesnippet/CSharp/step-7-keep-pairs-visible_1.cs)]
     [!code-vb[VbExpressTutorial4Step7#9](../ide/codesnippet/VisualBasic/step-7-keep-pairs-visible_1.vb)]

     První řádek `if` jste právě přidali zkontroluje, zda v první popisek, který hráč vybere ikonu je stejná jako ikona druhého popisku. Pokud jsou ikony shodné, program provede tři příkazy mezi složenými závorkami v jazyce C# nebo tři příkazy v rámci `if` v sadě Visual Studio. První dva příkazy resetují `firstClicked` a `secondClicked` referenční proměnné tak, aby se už udržovat přehled o žádném popisku. (Můžete rozpoznat tyto dva příkazy z časovače <xref:System.Windows.Forms.Timer.Tick> obslužné rutiny události.) Třetí příkaz je `return` příkaz, který říká programu, aby přeskočil zbytek příkazů v metodě bez jejich spuštění.

     Pokud programujete v jazyce Visual C#, mohli jste si všimnout, že některý kód používá jediný symbol rovnítka (`=`), zatímco jiné příkazy používají dva symboly rovná se (`==`). Zvažte, proč `=` se používá v některých místech, ale `==` je použit na dalších místech.

     Toto je typický příklad, který ukazuje rozdíl. Pozorně se podívejte na kód mezi závorkami v `if` příkazu.

    ```vb
    firstClicked.Text = secondClicked.Text
    ```

    ```csharp
    firstClicked.Text == secondClicked.Text
    ```

     Zkontrolujte pečlivě první příkaz v bloku kódu po `if` příkazu.

    ```vb
    firstClicked = Nothing
    ```

    ```csharp
    firstClicked = null;
    ```

     První z těchto dvou příkazů ověří, zda jsou dvě ikony stejné. Protože se porovnávají dvě hodnoty, program Visual C# používá `==` operátor rovnosti. Druhý výpis skutečně změní hodnotu (volá *přiřazení*) a nastavte `firstClicked` referenční proměnnou rovna `null` resetovat ho. To je důvod, proč používá `=` operátor přiřazení místo. Visual C# používá `=` nastavit hodnoty, a `==` k jejich porovnání. Jazyk Visual Basic používá `=` pro přiřazení proměnné a porovnání.

2. Uložte a spusťte program a začněte vybírat ikony ve formuláři. Pokud zvolíte dvojici, která neodpovídá, událost časovače Tick se aktivuje a obě ikony zmizí. Pokud zvolíte odpovídající dvojici, nový `if` provede příkaz a návratový příkaz způsobí, že metoda vynechá kód, který spustí časovač, takže ikony zůstanou viditelné, jak je znázorněno na následujícím obrázku.

     ![Hra, kterou vytvoříte v tomto kurzu](../ide/media/express_finishedgame.png)
**Porovnávací hra** se zobrazenými dvojicemi ikon

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

- Přechod k dalšímu kroku výukového programu naleznete v tématu [krok 8: Přidejte metodu k ověření, zda hráč zvítězil](../ide/step-8-add-a-method-to-verify-whether-the-player-won.md).

- Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 6: Přidejte časovač](../ide/step-6-add-a-timer.md).
