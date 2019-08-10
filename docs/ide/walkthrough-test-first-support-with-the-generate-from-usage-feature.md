---
title: Vývoj pro první test pomocí funkce generovat z využití
ms.date: 10/09/2017
dev_langs:
- VB
- CSharp
ms.topic: conceptual
helpviewer_keywords:
- Generate From Usage
- Test-First Development
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 039c022cc5a8883e5687630f5243d8652ff036e7
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68925837"
---
# <a name="walkthrough-test-first-development-with-the-generate-from-usage-feature"></a>Návod: Vývoj pro první test pomocí funkce generovat z využití

Toto téma ukazuje, jak použít funkci [Generovat z použití](../ide/visual-csharp-intellisense.md#generate-from-usage) , která podporuje vývoj na prvním testu.

 *Vývoj pro první test* je přístup k návrhu softwaru, ve kterém jste nejprve zapisovali testy jednotek na základě specifikací produktu, a pak napíšete zdrojový kód, který je požadován k úspěšnému provedení testů. Visual Studio podporuje vývoj na prvním testu tím, že generuje nové typy a členy ve zdrojovém kódu při jejich prvním odkazování v testovacích případech před jejich definováním.

Visual Studio vygeneruje nové typy a členy s minimálním přerušením pracovního postupu. Můžete vytvořit zástupné procedury pro typy, metody, vlastnosti, pole nebo konstruktory, aniž byste opustili aktuální umístění v kódu. Když otevřete dialogové okno pro zadání možností pro generování typů, při zavření dialogového okna se fokus vrátí hned na aktuální otevřený soubor.

Funkci **Generovat z použití** lze použít s testovacími architekturami, které jsou integrovány se sadou Visual Studio. V tomto tématu je znázorněno rozhraní testování částí společnosti Microsoft.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="create-a-windows-class-library-project-and-a-test-project"></a>Vytvoření projektu knihovny tříd Windows a testovacího projektu

1. V C# nebo Visual Basic vytvořte nový projekt **knihovny tříd systému Windows** . `GFUDemo_VB` Pojmenujte `GFUDemo_CS`ji nebo, podle toho, který jazyk používáte.

2. V **Průzkumník řešení**klikněte pravým tlačítkem myši na ikonu řešení v horní části, vyberte možnost **Přidat** > **Nový projekt**.

3. Vytvořte nový projekt **testu jednotek (.NET Framework)** .

   ::: moniker range="vs-2017"

   Na následujícím obrázku je znázorněno dialogové okno **Nový projekt** pro C# šablony.

   ![Šablona projektu testování částí](../ide/media/newproject_test.png)

   ::: moniker-end

### <a name="add-a-reference-to-the-class-library-project"></a>Přidat odkaz na projekt knihovny tříd

1. V **Průzkumník řešení**v rámci projektu testování částí klikněte pravým tlačítkem myši na položku **odkazy** a vyberte možnost **Přidat odkaz**.

2. V dialogovém okně **Správce odkazů** vyberte **projekty** a potom vyberte projekt knihovny tříd.

3. Kliknutím na **tlačítko OK** zavřete dialogové okno **Správce odkazů** .

4. Uložte své řešení. Teď jste připraveni začít psát testy.

### <a name="generate-a-new-class-from-a-unit-test"></a>Generovat novou třídu z testu jednotek

1. Testovací projekt obsahuje soubor s názvem *UnitTest1*. Dvojím kliknutím na tento soubor v **Průzkumník řešení** otevřete v editoru kódu. Byla vygenerována testovací třída a testovací metoda.

2. Vyhledejte deklaraci třídy `UnitTest1` a přejmenujte ji `AutomobileTest`na.

   > [!NOTE]
   > Technologie IntelliSense nyní nabízí dvě alternativy dokončování příkazů technologie IntelliSense: *režim dokončování* a *režim návrhu*. Režim návrhu použijte pro situace, ve kterých se třídy a členy používají předtím, než budou definovány. Když je okno **IntelliSense** otevřené, můžete stisknout **CTRL**+ **+** +**MEZERNÍK** pro přepínání mezi režimem dokončení a režimem návrhu. Další informace najdete v tématu [použití technologie IntelliSense](../ide/using-intellisense.md) . Režim návrhu vám pomůže při psaní `Automobile` v dalším kroku.

3. Vyhledejte metodu a přejmenujte ji `DefaultAutomobileIsInitializedCorrectly()`na. `TestMethod1()` V rámci této metody vytvořte novou instanci třídy s názvem `Automobile`, jak je znázorněno na následujících snímcích obrazovky. Zobrazí se vlnové podtržení, které indikuje chybu při kompilaci, a v levém horním rohu se objeví chybová žárovka Chyba [rychlé akce](../ide/quick-actions.md) , která se zobrazí na levém okraji, nebo přímo pod vlnovkou, pokud na ni najedete myší.

    ![Rychlé akce v Visual Basic](../ide/media/genclass_underlinevb.png)

    ![Rychlé akce v jazyce C&#35;](../ide/media/genclass_underline.png)

4. Vyberte nebo klikněte na žárovku **rychlé akce** . Zobrazí se chybová zpráva s oznámením, že typ `Automobile` není definován. Zobrazí se také některá řešení.

5. Kliknutím na **generovat nový typ** otevřete dialogové okno **generovat typ** . Toto dialogové okno obsahuje možnosti, které zahrnují generování typu v jiném projektu.

6. V seznamu **projekt** klikněte na **GFUDemo\_VB** nebo **GFUDemo_CS** a řekněte aplikaci Visual Studio, aby přidala soubor do projektu knihovny tříd namísto testovacího projektu. Pokud ještě není vybraná, vyberte **vytvořit nový soubor** a pojmenujte ho *Automobile.cs* nebo *automobil. vb*.

     ![Dialogové okno generovat nový typ](../ide/media/genotherdialog.png)

7. Kliknutím na tlačítko **OK** zavřete dialogové okno a vytvořte nový soubor.

8. V **Průzkumník řešení**vyhledejte v uzlu projektu **GFUDemo_VB** nebo **GFUDemo_CS** , zda je k dispozici nový soubor *automobil. vb* nebo *Automobile.cs* . V editoru kódu je fokus stále v, což vám `AutomobileTest.DefaultAutomobileIsInitializedCorrectly`umožní pokračovat v psaní testu s minimálním přerušením.

### <a name="generate-a-property-stub"></a>Vygenerování provizorního kódu vlastnosti
Předpokládat, že specifikace produktu uvádí, že `Automobile` třída má dvě veřejné vlastnosti s `Model` názvem `TopSpeed`a. Tyto vlastnosti musí být inicializovány s výchozími `"Not specified"` hodnotami `-1` a výchozím konstruktorem. Následující test jednotek ověří, zda výchozí konstruktor nastaví vlastnosti na jejich správné výchozí hodnoty.

1. Do `DefaultAutomobileIsInitializedCorrectly` testovací metody přidejte následující řádek kódu.

     [!code-csharp[VbTDDWalkthrough#1](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_1.cs)]
     [!code-vb[VbTDDWalkthrough#1](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_1.vb)]

2. Vzhledem k tomu, že kód odkazuje na `Automobile`dvě nedefinované vlastnosti, zobrazí se vlnové podtržení v oblasti `Model` a `TopSpeed`. Najeďte myší azvoltežárovkuchybarychléakceapakzvolteGenerovatvlastnost'automobil.model`Model` **'** .

3. Vygenerujte zástupnou proceduru vlastnosti pro `TopSpeed` vlastnost stejným způsobem.

     `Automobile` Ve třídě jsou typy nových vlastností správně odvozeny z kontextu.

### <a name="generate-a-stub-for-a-new-constructor"></a>Vygenerovat zástupnou proceduru pro nový konstruktor
Nyní vytvoříme testovací metodu, která bude generovat zástupnou proceduru konstruktoru pro `Model` inicializaci `TopSpeed` vlastností a. Později přidáte další kód pro dokončení testu.

1. Přidejte do `AutomobileTest` třídy následující další metodu testu.

     [!code-csharp[VbTDDWalkthrough#2](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_2.cs)]
     [!code-vb[VbTDDWalkthrough#2](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_2.vb)]

2. V červené vlnovce klikněte na žárovku Chyba **rychlých akcí** a pak klikněte na **vytvořit konstruktor v automobilu**.

     V souboru `Automobile` třídy si všimněte, že nový konstruktor zkontroloval názvy místních proměnných, které se používají ve volání konstruktoru, nalezené vlastnosti, které mají stejné názvy ve třídě, a dodaný kód v těle konstruktoru do `Automobile` uložte hodnoty argumentů do `Model` vlastností a. `TopSpeed`

3. Po vygenerování nového konstruktoru se zobrazí podtržení vlnovkou pod voláním výchozího konstruktoru v `DefaultAutomobileIsInitializedCorrectly`. Chybová zpráva uvádí, že `Automobile` třída nemá žádný konstruktor, který přebírá nula argumentů. Pokud chcete vygenerovat explicitní výchozí konstruktor, který nemá parametry, klikněte na žárovku chyby **rychlých akcí** a pak klikněte na **vytvořit konstruktor v automobilu**.

### <a name="generate-a-stub-for-a-method"></a>Generování zástupné procedury pro metodu
Předpokládá, že specifikace, která je nová `Automobile` , může být vložena `IsRunning` do stavu, `Model` Pokud `TopSpeed` jsou vlastnosti a vlastností nastaveny na jinou hodnotu než výchozí hodnoty.

1. Do `AutomobileWithModelNameCanStart` metody přidejte následující řádky.

     [!code-csharp[VbTDDWalkthrough#3](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_3.cs)]
     [!code-vb[VbTDDWalkthrough#3](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_3.vb)]

2. Klikněte na žárovku chyby **rychlých akcí** pro `myAuto.Start` volání metody a pak klikněte na **vygenerovat metodu ' automobil. Start '** .

3. Klikněte na žárovku **rychlých akcí** pro `IsRunning` vlastnost a pak klikněte na **vygenerovat vlastnost ' automobil. derunning '** .

     Třída nyní obsahuje metodu s názvem `Start()` a vlastnost s názvem `IsRunning`. `Automobile`

### <a name="run-the-tests"></a>Spustit testy

1. V nabídce **test** vyberte možnost **Spustit** > **všechny testy**.

     Příkaz **Spustit** > **všechny testy** spustí všechny testy v jakémkoli testovacím rozhraní, které jsou zapsány pro aktuální řešení. V tomto případě existují dvě testy a obě selžou, podle očekávání. Test `DefaultAutomobileIsInitializedCorrectly` se nezdařil, `Assert.IsTrue` protože podmínka `False`se vrátí. Test `AutomobileWithModelNameCanStart` se nezdařil, `Start` protože metoda ve `Automobile` třídě vyvolá výjimku.

     Následující obrázek ukazuje **výsledky testů** okno.

     ![Výsledky testů, které selhaly](../ide/media/testsfailed.png)

2. V okně **výsledky testů** dvakrát klikněte na každý řádek výsledku testu, abyste přešli do umístění každého testu.

### <a name="implement-the-source-code"></a>Implementace zdrojového kódu

1. Do výchozího konstruktoru přidejte `Model`následující kód tak, `TopSpeed` aby byly vlastnosti a `-1` `"Not specified"` `IsRunning` všechny inicializovány na jejich správné výchozí hodnoty, a `False` (nebo `false` pro C#).

     [!code-csharp[VbTDDWalkthrough#5](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_5.cs)]
     [!code-vb[VbTDDWalkthrough#5](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_5.vb)]

2. Při volání `IsRunning` `Model` metody by měl příznak nastavit na hodnotu true, pouze pokud jsou vlastnosti nebo `TopSpeed` nastaveny na jinou hodnotu než výchozí hodnota. `Start` `NotImplementedException` Odeberte z těla metody a přidejte následující kód.

     [!code-csharp[VbTDDWalkthrough#6](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_6.cs)]
     [!code-vb[VbTDDWalkthrough#6](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_6.vb)]

### <a name="run-the-tests-again"></a>Spustit testy znovu

- V nabídce **test** přejděte na příkaz **Spustit**a potom klikněte na možnost **všechny testy**.

     Tentokrát testy proběhnou. Následující obrázek ukazuje **výsledky testů** okno.

     ![Výsledky testů, které byly úspěšné](../ide/media/testspassed.png)

## <a name="see-also"></a>Viz také:

- [Generovat z využití](../ide/visual-csharp-intellisense.md#generate-from-usage)
- [Funkce editoru kódu](../ide/writing-code-in-the-code-and-text-editor.md)
- [Používání technologie IntelliSense](../ide/using-intellisense.md)
- [Testování částí kódu](../test/unit-test-your-code.md)
- [Rychlé akce](../ide/quick-actions.md)