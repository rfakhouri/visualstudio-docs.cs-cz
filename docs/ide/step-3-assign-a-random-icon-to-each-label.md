---
title: 'Krok 3: Přiřaďte jednotlivým jmenovkám náhodné ikony'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 0ba5ed7a-9aaa-41f4-95d2-e3c2d567bc79
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e8aac613f4fe8a93ebd31127e26bcd92218b6300
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34748241"
---
# <a name="step-3-assign-a-random-icon-to-each-label"></a>Krok 3: Přiřaďte jednotlivým jmenovkám náhodné ikony
Pokud se ikony každou hru zobrazí ve stejných buňkách, není to zrovna náročné. Abyste tomu předešli, přiřadit ikony náhodně popisek ovládacích prvků na formuláři pomocí `AssignIconsToSquares()` metoda.

## <a name="to-assign-a-random-icon-to-each-label"></a>Přiřazení náhodné ikony každému popisku

1.  Před přidáním následujícího kódu se zamyslete nad tím, jak metoda funguje. New – klíčové slovo je: `foreach` v jazyce Visual C# a `For Each` v jazyce Visual Basic. (Jeden z řádků je záměrně jako komentář, což je vysvětleno na konci této procedury.)

     [!code-csharp[VbExpressTutorial4Step2_3_4#2](../ide/codesnippet/CSharp/step-3-assign-a-random-icon-to-each-label_1.cs)]
     [!code-vb[VbExpressTutorial4Step2_3_4#2](../ide/codesnippet/VisualBasic/step-3-assign-a-random-icon-to-each-label_1.vb)]

2.  Přidat `AssignIconsToSquares()` metoda, jak je znázorněno v předchozím kroku. Můžete ji umístit pod kód, který jste přidali v [krok 2: přidejte náhodný objekt a seznam ikon](../ide/step-2-add-a-random-object-and-a-list-of-icons.md).

     Jak už bylo zmíněno dříve, není něco nového ve vaší `AssignIconsToSquares()` metoda: `foreach` smyčky v jazyce Visual C# a `For Each` v jazyce Visual Basic. Můžete použít `For Each` cykly kdykoli chcete provádět stejné akce vícekrát. V takovém případě chcete spustit stejné příkazy pro každý štítek na vaše <xref:System.Windows.Forms.TableLayoutPanel>, jak je popsáno v následujícím kódu. První řádek vytvoří proměnné s názvem `control` , ukládá každý ovládací prvek, jeden v době při že ovládací prvek má příkazy ve smyčce provedeny na něm.

     [!code-csharp[VbExpressTutorial4Step2_3_4#14](../ide/codesnippet/CSharp/step-3-assign-a-random-icon-to-each-label_2.cs)]
     [!code-vb[VbExpressTutorial4Step2_3_4#14](../ide/codesnippet/VisualBasic/step-3-assign-a-random-icon-to-each-label_2.vb)]

    > [!NOTE]
    >  Názvy „iconLabel“ a „ovládací prvek“ se používají, protože jsou popisné. Tyto názvy můžete nahradit libovolnými názvy a kód by měl pracovat přesně stejně, dokud nezměníte název v každém výroku uvnitř smyčky.

     `AssignIconsToSquares()` Metoda iteruje každý popisek – ovládací prvek v kontejneru TableLayoutPanel a provede stejné příkazy pro každý z nich. Tyto příkazy vyžádají náhodné ikony ze seznamu, kterou jste přidali v [krok 2: přidejte náhodný objekt a seznam ikon](../ide/step-2-add-a-random-object-and-a-list-of-icons.md). (To je důvod, proč dvě z každé ikony uveden v seznamu, aby pár ikony přiřazené k náhodnému ovládací prvky popisek.)

     Podívejte se na kód, který běží v rámci přesněji `foreach` nebo `For Each` smyčky. Tento kód je reprodukován zde.

     [!code-csharp[VbExpressTutorial4Step2_3_4#16](../ide/codesnippet/CSharp/step-3-assign-a-random-icon-to-each-label_3.cs)]
     [!code-vb[VbExpressTutorial4Step2_3_4#16](../ide/codesnippet/VisualBasic/step-3-assign-a-random-icon-to-each-label_3.vb)]

     Převede první řádek **řízení** proměnné na štítek s názvem **iconLabel**. Na řádku, po který je `if` příkaz, který kontroluje, abyste měli jistotu, převod fungovala. Pokud převod, příkazy v funguje `if` příkaz spustit. (Jak může Vzpomínáte z předchozí kurzy `if` příkaz slouží k vyhodnocení, ať je zadaná podmínka.) V prvním řádku `if` příkaz vytvoří proměnné s názvem **nahodneCislo** obsahující náhodné číslo, které odpovídá jedné z položek v seznamu ikon. K tomu použije <xref:System.Random.Next> metodu <xref:System.Random> objekt, který jste vytvořili dříve. `Next` Metoda vrátí náhodné číslo. Také používá tento řádek <xref:System.Collections.Generic.List%601.Count> vlastnost **ikony** seznamu k určení rozsahu pro výběr náhodné číslo. Na další řádek mezi ikonu přiřadí položky seznamu na <xref:System.Windows.Forms.Label.Text> vlastnost popisku. Komentovaný řádek je vysvětlen později v tomto tématu. Nakonec na posledním řádku `if` příkaz odebere ze seznamu ikonu, která byla přidána do formuláře.

     Nezapomeňte, že pokud si nejste jisti, co dělá některá část kódu, můžete umístit ukazatel myši nad prvek kódu a přečíst si zobrazený popisek. Můžete také krokovat po řádcích kódu, zatímco je program spuštěn pomocí ladicího programu sady Visual Studio. V tématu [jak proveďte krok I: pomocí ladicího programu v sadě Visual Studio?](http://msdn.microsoft.com/vstudio/ee672313.aspx) nebo [přejděte prostřednictvím kódu s ladicím programem](../debugger/navigating-through-code-with-the-debugger.md) Další informace.

3.  Vyplnit herní panelu s ikonami, je třeba volat `AssignIconsToSquares()` metoda při spuštění programu. Pokud používáte Visual C#, přidejte příkaz pod volání `InitializeComponent()` metoda v **Form1 *** konstruktor*, tak formulář zavolá metodu nové samotné nastavit dříve, než je zobrazen. Konstruktory jsou volány při vytváření nového objektu, například třídy nebo struktury. V tématu [konstruktory (C# programovací průvodce)](http://msdn.microsoft.com/library/ace5hbzh.aspx) nebo [pomocí konstruktorů a destruktorů](http://msdn.microsoft.com/library/2z08e49e.aspx) v jazyce Visual Basic pro další informace.

     [!code-csharp[VbExpressTutorial4Step2_3_4#13](../ide/codesnippet/CSharp/step-3-assign-a-random-icon-to-each-label_4.cs)]

     V jazyce Visual Basic, přidejte `AssignIconsToSquares()` volání metody `Form1_Load` metoda tak, aby kód vypadá jako následující.

    ```vb
    Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
        AssignIconsToSquares()
    End Sub
    ```

4.  Uložte program a spusťte jej. Měl by se zobrazit formulář s náhodnými ikonami přiřazenými každému popisku.

5.  Ukončete program a znovu jej spusťte. Všimněte si, že každému popisku jsou přiřazeny jiné ikony, viz následující obrázek.

     ![Odpovídající hru s náhodné ikony](../ide/media/express_tut4step3.png) odpovídající hru s náhodné ikony

     Ikony jsou nyní viditelné, protože jste je neskryli. Skryjete z přehrávače, můžete nastavit každý popisek **ForeColor** vlastnost, která má stejnou barvu jako jeho **BackColor** vlastnost.

    > [!TIP]
    >  Dalším způsobem skrytí ovládacích prvků jako popisky je nastavit jejich **viditelný** vlastnost **False**.

6.  Pokud chcete skrýt ikony, zastavte program a odebrat komentář označí komentáři řádku kódu do `For Each` smyčky.

     [!code-csharp[VbExpressTutorial4Step2_3_4#15](../ide/codesnippet/CSharp/step-3-assign-a-random-icon-to-each-label_5.cs)]
     [!code-vb[VbExpressTutorial4Step2_3_4#15](../ide/codesnippet/VisualBasic/step-3-assign-a-random-icon-to-each-label_5.vb)]

7.  Na řádku nabídek zvolte **Uložit vše** tlačítko Uložit program a potom ho spusťte. Ikony zdánlivě zmizely – zobrazí se pouze modré pozadí. Ikony jsou ale náhodně přiřazeny a stále existují. Vzhledem k tomu, že ikony mají stejnou barvu jako pozadí, hráč je nevidí. Přece by to byla velmi jednoduchá hra, kdyby hráč hned viděl všechny ikony!

## <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat

-   Chcete-li přejít k dalšímu kroku kurzu, přečtěte si téma [krok 4: přidejte k jednotlivým jmenovkám obslužnou rutinu události kliknutí](../ide/step-4-add-a-click-event-handler-to-each-label.md).

-   Chcete-li vrátit k předchozímu kroku kurzu, přečtěte si téma [krok 2: přidejte náhodný objekt a seznam ikon](../ide/step-2-add-a-random-object-and-a-list-of-icons.md).
