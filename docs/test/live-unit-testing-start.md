---
title: Zjistěte, jak k testování kódu s Live jednotkové testování v Visual Studio 2017 | Microsoft Docs
ms.date: 08/31/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio ALM
- Live Unit Testing
author: rpetrusha
ms.author: ronpet
ms.workload:
- dotnet
ms.openlocfilehash: 794f3aeab023d6b6c5c606a4c1fb8f706a4a7989
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="get-started-with-live-unit-testing-in-visual-studio"></a>Začínáme s Live jednotkové testování v sadě Visual Studio

Když povolíte Live testování částí v řešení sady Visual Studio, Live testování částí vizuálně znázorňuje pokrytí test a stav testy. Vždy, když upravíte kód testy, provede se také dynamicky. Poskytuje okamžité odeslání oznámení, když změny mají poškozen kódu a uvádí oblasti, pro které jsou potřeba další testy.

Za provozu jednotkové testování dá použít k testování řešení, která cílí na rozhraní .NET Framework nebo .NET Core. V tomto kurzu získáte informace používat za provozu jednotkové testování pomocí vytvoření knihovny tříd jednoduché s cílem .NET Standard a vytvoříte projekt Mstestu s cílem .NET Core to vyzkoušíte.

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
Úplné řešení C# lze stáhnout z [MicrosoftDocs nebo Visual Studio – dokumentace](https://github.com/MicrosoftDocs/visualstudio-docs/tree/master/docs/test/samples/csharp/UtilityLibraries/) úložišti na Githubu.
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
Úplné řešení Visual Basic si můžete stáhnout z [MicrosoftDocs nebo Visual Studio – dokumentace](https://github.com/MicrosoftDocs/visualstudio-docs/tree/master/docs/test/samples/visual-basic/UtilityLibraries/) úložišti na Githubu.

---

## <a name="prerequisites"></a>Požadavky

Tento kurz vyžaduje, že jste nainstalovali Visual Studio 2017 Enterprise Edition verze 15.3 se zatížením, rozhraní .NET 2.0 jádra.

## <a name="create-the-solution-and-the-class-library-project"></a>Vytvoření řešení a projektu knihovny tříd

Začněte tím, že vytváření řešení sady Visual Studio s názvem `UtilityLibraries` , se skládá z jedné .NET Standard projektu knihovny tříd, `StringLibrary`. Můžete napsat `StringLibrary` v C# nebo Visual Basic.

Řešení je kontejner pro jeden nebo více projektů. Pokud chcete vytvořit řešení, otevřete Visual Studio 2017 a proveďte následující kroky:

1. Vyberte **soubor**, **nový**, **projektu** nejvyšší úrovně nabídce sady Visual Studio.

1. V **nový projekt** dialogové okno, rozbalte **jiné typy projektů** uzel a vyberte možnost **řešení sady Visual Studio**. Vyberte **prázdného řešení** šablony v pravém podokně a zadejte `UtilityLibraries` v **název** textového pole, jak ukazuje následující obrázek:

   ![** Dialogové okno Nový projekt **](./media/lut-start/new-solution.png)

1. Vyberte **OK** k vytvoření řešení.

Teď, když jste vytvořili řešení, vytvoříte knihovny tříd s názvem `StringLibrary` obsahující počet rozšiřující metody pro práci s řetězci.

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na `UtilityLibraries` řešení a vyberte **přidat**, **nový projekt**.

1. V **přidat nový projekt** dialogovém okně, vyberte jazyka C# uzlu, pak vyberte **.NET Standard**.

   > [!NOTE]
   > Protože naše knihovna cílí na Standard .NET spíše než konkrétní implementace rozhraní .NET, může být volána z žádnou implementaci rozhraní .NET, která podporuje tuto verzi .NET Standard. Další informace najdete v tématu [.NET Standard](/dotnet/standard/net-standard).

1. Vyberte **knihovny tříd (.NET Standard)** šablony v pravém podokně a zadejte `StringLibrary` v **název** textového pole, jak ukazuje následující obrázek:

   ![** Dialogové okno Přidat nový projekt **](./media/lut-start/add-project-cs.png)

1. Vyberte **OK** a vytvořte tak projekt.

1. Všechny existující kód v okně kódu nahraďte následujícím kódem:

   [!code-csharp[StringLibrary source code](samples/csharp/utilitylibraries/stringlibrary/class1.cs)]

   `StringLibrary` má tři statických metod:

      - `StartsWithUpper` Vrátí `true` Pokud řetězec začíná velké písmeno; jinak vrátí `false`.

      - `StartsWithLower`Vrátí `true` Pokud řetězec začíná malé písmeno; jinak vrátí `false`.

      - `HasEmbeddedSpaces` Vrátí `true` Pokud řetězec obsahuje znak embedded prázdné; jinak vrátí `false`.

1.  Vyberte **sestavení**, **sestavit řešení** nejvyšší úrovně nabídce sady Visual Studio. Visual Studio má úspěšně sestavit knihovnu.

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na `UtilityLibraries` řešení a vyberte **přidat**, **nový projekt**.

1. V **přidat nový projekt** dialogovém okně, vyberte uzel jazyka Visual Basic a pak vyberte **.NET Standard**.

   > [!NOTE]
   > Protože naše knihovna cílí na Standard .NET spíše než konkrétní implementace rozhraní .NET, může být volána z žádnou implementaci rozhraní .NET, která podporuje tuto verzi .NET Standard. Další informace najdete v tématu [.NET Standard](/dotnet/standard/net-standard).

1. Vyberte **knihovny tříd (.NET Standard)** šablony v pravém podokně a zadejte `StringLibrary` v **název** textového pole, jak ukazuje následující obrázek:

   ![** Dialogové okno Přidat nový projekt **](./media/lut-start/add-project-vb.png)

1. Vyberte **OK** a vytvořte tak projekt.

1. Všechny existující kód v okně kódu nahraďte následujícím kódem:

   [!code-vb[StringLibrary source code](samples/visual-basic/utilitylibraries/stringlibrary/class1.vb)]

   `StringLibrary` má tři statických metod:

      - `StartsWithUpper` Vrátí `true` Pokud řetězec začíná velké písmeno; jinak vrátí `false`.

      - `StartsWithLower`Vrátí `true` Pokud řetězec začíná malé písmeno; jinak vrátí `false`.

      - `HasEmbeddedSpaces` Vrátí `true` Pokud řetězec obsahuje znak embedded prázdné; jinak vrátí `false`.

1. Klikněte pravým tlačítkem na projekt StringLibrary v **Průzkumníku řešení** a vyberte **vlastnosti**. V **aplikace** kartě, odstraňte text v **kořenový obor názvů** textového pole, jak ukazuje následující obrázek. Kořenového oboru názvů je definována [příkaz Namespace](/dotnet/visual-basic/language-reference/statements/namespace-statement) ve zdrojovém kódu.

   ![Dialogové okno vlastností projektu projektu jazyka Visual Basic](./media/lut-start/vb-properties.png)

1.  Vyberte **sestavení**, **sestavit řešení** nejvyšší úrovně nabídce sady Visual Studio. Visual Studio má úspěšně sestavit knihovnu.

---

## <a name="create-the-test-project"></a>Vytvoření projektu testů

Dalším krokem je vytvoření projektu testů jednotek pro testování `StringLibrary` knihovny. Vytvořte testy částí provedením následujících kroků:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na `UtilityLibraries` řešení a vyberte **přidat**, **nový projekt**.

1. V **přidat nový projekt** dialogovém okně, vyberte jazyka C# uzlu, pak vyberte **.NET Core**.

   > [!NOTE]
   > Zápis testů částí ve stejném jazyce jako knihovny tříd nemáte.

1. Vyberte **projektu testování částí (.NET Core)** šablony v pravém podokně a zadejte `StringLibraryTests` v **název** textového pole, jak ukazuje následující obrázek:

   ![** Dialogové okno Přidat nový projekt ** projektu testování částí](./media/lut-start/add-unit-test-cs.png)

1. Vyberte **OK** a vytvořte tak projekt.

   > [!NOTE]
   > Tento úvodní kurz používá Live testování částí s použitím Mstestu test framework. Můžete také použít xUnit a NUnit test rozhraní.

1. Projektu testů jednotek nemůže získat přístup automaticky knihovny tříd, které je testování. Přístup ke knihovně testovací dáváte tak, že přidáte odkaz na projekt knihovny tříd. Chcete-li to provést, klikněte pravým tlačítkem na `StringLibraryTests` projektu a vyberte **přidat**, **odkaz**. V **správce odkazů** dialogové okno, zajistěte, aby **řešení** karta je vybrané a vyberte `StringLibrary` projektu, jak je znázorněno na následujícím obrázku.

   ![** Odkaz Manager ** dialogové okno](./media/lut-start/add-reference.png)

1. Nahraďte kód testu jednotek standardní poskytované šablony s následujícím kódem:

   [!code-csharp[StringLibraryTest source code](samples/snippets/csharp/lut-start/unittest1.cs)]

1. Uložte projekt tak, že vyberete **Uložit** ikonu na panelu nástrojů.

1. Vzhledem k tomu, že jednotka otestovat kód obsahuje některé jiné znaky než ASCII, Visual Studio zobrazí dialog následující do us upozornit, že některé znaky budou ztraceny, pokud jsme uložit soubor ve formátu ASCII jeho výchozí. Vyberte **uložit s další kódování** tlačítko.

   ![Zvolte kódování souborů](media/lut-start/ascii-encoding.png)

1. V **kódování** rozevírací seznam **možnosti uložit zálohy** dialogové okno, zvolte **Unicode (UTF-8 bez podpisu) - Codepage 65001**, jak ukazuje následující obrázek:

   ![Výběr kódování UTF-8](media/lut-start/utf8-encoding.png)

1. Kompilace projektu testů jednotek tím **sestavení**, **znovu sestavit řešení** nejvyšší úrovně nabídce sady Visual Studio.

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)

1. V **Průzkumníku řešení**, klikněte pravým tlačítkem na `UtilityLibraries` řešení a vyberte **přidat**, **nový projekt**.

1. V **přidat nový projekt** dialogovém okně, vyberte uzel jazyka Visual Basic a pak vyberte **.NET Core**.

   > [!NOTE]
   > Zápis testů částí ve stejném jazyce jako knihovny tříd nemáte.

1. Vyberte **projektu testování částí (.NET Core)** šablony v pravém podokně a zadejte `StringLibraryTests` v **název** textového pole, jak ukazuje následující obrázek:

   ![** Dialogové okno Přidat nový projekt ** pro testování částí](./media/lut-start/add-unit-test-vb.png)

1. Vyberte **OK** a vytvořte tak projekt.

   > [!NOTE]
   > Tento úvodní kurz používá Live testování částí s použitím Mstestu test framework. Můžete také použít xUnit a NUnit test rozhraní.

1. Projektu testů jednotek nemůže získat přístup automaticky knihovny tříd, které je testování. Přístup ke knihovně testovací dáváte tak, že přidáte odkaz na projekt knihovny tříd. Chcete-li to provést, klikněte pravým tlačítkem na `StringLibraryTests` projektu a vyberte **přidat**, **odkaz**. V **správce odkazů** dialogové okno, zajistěte, aby **řešení** karta je vybrané a vyberte `StringLibrary` projektu, jak je znázorněno na následujícím obrázku.

   ![** Odkaz Manager ** dialogové okno](./media/lut-start/add-reference.png)

1. Nahraďte kód testu jednotek standardní poskytované šablony s následujícím kódem:

   [!code-vb[StringLibraryTest source code](samples/snippets/visual-basic/lut-start/unittest1.vb)]

1. Uložte projekt tak, že vyberete **Uložit** ikonu na panelu nástrojů.

1. Vzhledem k tomu, že jednotka otestovat kód obsahuje některé jiné znaky než ASCII, Visual Studio zobrazí dialog následující do us upozornit, že některé znaky budou ztraceny, pokud jsme uložit soubor ve formátu ASCII jeho výchozí. Vyberte **uložit s další kódování** tlačítko.

   ![Zvolte kódování souborů](media/lut-start/ascii-encoding.png)

1. V **kódování** rozevírací seznam **možnosti uložit zálohy** dialogové okno, zvolte **Unicode (UTF-8 bez podpisu) - Codepage 65001**, jak ukazuje následující obrázek:

   ![Výběr kódování UTF-8](media/lut-start/utf8-encoding.png)

1. Kompilace projektu testů jednotek tím **sestavení**, **znovu sestavit řešení** nejvyšší úrovně nabídce sady Visual Studio.

---

Vytvoření knihovny tříd a také některé testy částí pro ni. Nyní jste dokončili nezbytné úkony potřeba k použití za provozu testování jednotky.

## <a name="enable-live-unit-testing"></a>Povolit za provozu testování částí

Proto úplně, i když jste vytvořili testy pro `StringLibrary` knihovny tříd, nebyly provedení je. Testování částí za provozu je spouští automaticky po jeho povolení. To lze provést, postupujte takto:

1. Volitelně vyberte okno kódu, který obsahuje kód pro `StringLibrary`. Toto je buď class1.cs pro projekt C# nebo Class1.vb pro projektu jazyka Visual Basic. (Tento krok vám umožní vizuálně zkontrolovat výsledky testů a rozsah vašeho pokrytí kódu, jakmile povolíte Live testování částí.)

1. Vyberte **Test**, **Live testování částí**, **spustit** nejvyšší úrovně nabídce sady Visual Studio.

1. Visual Studio spustí testování částí za provozu, který se automaticky spouští všechny testy.

Po dokončení spuštění testů, **Průzkumníka testů** zobrazí celkové výsledky a výsledky jednotlivých testů. Kromě toho okno kódu graficky zobrazí vaše testovací pokrytí kódu a výsledků testů. Jak ukazuje následující obrázek, všechny tři testy proběhlo úspěšně. Také ukazuje, že naše testy mít zahrnuté všechny cesty kódu v `StartsWithUpper` metoda tyto testy a všechny byl úspěšně proveden (které je indikován zelená značka zaškrtnutí, "✓"). Nakonec se ukazuje, že žádná z jiné metody v `StringLibrary` mít pokrytí kódu (která je označena pomocí modré linky, "➖").

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
![Okno Průzkumníka testů a kód po spuštění testování částí za provozu](media/lut-start/lut-results-cs.png)

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
![Okno Průzkumníka testů a kód po spuštění testování částí za provozu](media/lut-start/lut-results-vb.png)

---

Také získáte podrobnější informace o nástroji pro testování pokrytí a testovací výsledky výběrem ikonou pokrytí kódu pro konkrétní v okně kód. Pro zjištění této podrobností, postupujte takto:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Kliknutím na zelené značky zaškrtnutí na řádek, který čte `if (String.IsNullOrWhiteSpace(s))` v `StartsWithUpper` metoda. Jak ukazuje následující obrázek, Live testování částí označuje, že tři testy zahrnují tohoto řádku kódu a že všechny provedli úspěšně.

   ![Pokrytí kódu pro příkaz podmíněného 'if'](media/lut-start/code-coverage-cs1.png)

1. Kliknutím na zelené značky zaškrtnutí na řádek, který čte `return Char.IsUpper(s[0])` v `StartsWithUpper` metoda. Jak ukazuje následující obrázek, Live testování částí označuje, že pouze dva testy zahrnují tohoto řádku kódu a že všechny provedli úspěšně.

   ![Pokrytí kódu pro příkaz return](media/lut-start/code-coverage-cs2.png)

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Kliknutím na zelené značky zaškrtnutí na řádek, který čte `If (String.IsNullOrWhiteSpace(s)) Then` v `StartsWithUpper` metoda. Jak ukazuje následující obrázek, Live testování částí označuje, že tři testy zahrnují tohoto řádku kódu a že všechny provedli úspěšně.

   ![Pokrytí kódu pro příkaz podmíněného 'If'](media/lut-start/code-coverage-vb1.png)

1. Kliknutím na zelené značky zaškrtnutí na řádek, který čte `Return Char.IsUpper(s(0))` v `StartsWithUpper` metoda. Jak ukazuje následující obrázek, Live testování částí označuje, že pouze dva testy zahrnují tohoto řádku kódu a že všechny provedli úspěšně.

   ![Pokrytí kódu pro příkaz return](media/lut-start/code-coverage-vb2.png)

---

Hlavní problém, který identifikuje Live testování částí je pokrytí kódu neúplné. Budete ho adres v další části.

## <a name="expand-test-coverage"></a>Rozbalte pokrytí testu

V této části budete rozšířit vaše testů jednotek pro `StartsWithLower` metoda. Zatímco můžete udělat, Live testování částí dynamicky bude Otestujte svůj kód.

Pokrytí kódu k rozšíření `StartsWithLower` metoda, postupujte takto:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Přidejte následující `TestStartsWithLower` a `TestDoesNotStartWithLower` metody k souboru zdrojového kódu vašeho projektu testu:

    [!code-csharp[StringLibraryTest source code](samples/snippets/csharp/lut-start/unittest2.cs#1)]

1. Změnit `DirectCallWithNullOrEmpty` metoda přidáním následující kód ihned po volání [ `Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse` ](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.isfalse) metoda.

    [!code-csharp[StringLibraryTest source code](samples/snippets/csharp/lut-start/unittest2.cs#2)]

1. Za provozu testování částí provede testy nových a upravených automaticky, když upravíte vašeho zdrojového kódu. Jako na následujícím obrázku z **Průzkumníka testů** ukazuje, všechny testy, včetně dvou jste přidali a jeden jste změnili, proběhlo úspěšně.

   ![Průzkumník testů po rozbalení pokrytí testu.](media/lut-start/test-dynamic.png)

1. Přejít do okna, který obsahuje zdrojový kód `StringLibrary` třídy. Testování částí nyní zobrazuje, které je rozšířit naše pokrytí kódu pro za provozu `StartsWithLower` metoda.

    ![Pokrytí kódu pro metodu StartsWithLower](media/lut-start/lut-extended-cs.png)

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Přidejte následující `TestStartsWithLower` a `TestDoesNotStartWithLower` metody k souboru zdrojového kódu vašeho projektu testu:

    [!code-vb[StringLibraryTest source code](samples/snippets/visual-basic/lut-start/unittest2.vb#1)]

1. Změnit `DirectCallWithNullOrEmpty` metoda přidáním následující kód ihned po volání [ `Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse` ](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.isfalse) metoda.

    [!code-vb[StringLibraryTest source code](samples/snippets/visual-basic/lut-start/unittest2.vb#2)]

1. Za provozu testování částí provede testy nových a upravených automaticky, když upravíte vašeho zdrojového kódu. Jako na následujícím obrázku z **Průzkumníka testů** ukazuje, všechny testy, včetně dvou jste přidali a jeden jste změnili, proběhlo úspěšně.

   ![Průzkumník testů po rozbalení pokrytí testu.](media/lut-start/test-dynamic.png)

1. Přejít do okna, který obsahuje zdrojový kód `StringLibrary` třídy. Testování částí nyní zobrazuje, které je rozšířit naše pokrytí kódu pro za provozu `StartsWithLower` metoda.

    ![Pokrytí kódu pro StartsWithLower](media/lut-start/lut-extended-vb.png)

---

V některých případech úspěšné testů v **Průzkumníka testů** může být šedě. Určující, zda testu je aktuálně spuštěné, nebo že test nebyl znovu spustit, protože byly provedeny změny žádný kód, který by ovlivnit test vzhledem k tomu, že poslední spuštění.

Pokud máte úspěšné všechny naše testy. V další části podíváme, jak zpracovávat zkušební selhání.

## <a name="handling-a-test-failure"></a>Zpracování selhání testu

V této části budete zjistit, jak můžete za provozu testování částí identifikovat, odstraňování a vyřešit selhání při testu. Můžete to udělat rozšířením testovací pokrytí k `HasEmbeddedSpaces` metoda.

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Přidejte následující metodu do testovacího souboru:

    [!code-csharp[The TestHasEmbeddedSpaces test method](samples/snippets/csharp/lut-start/unittest2.cs#3)]

1. Když provede test, Live testování částí znamená, že `TestHasEmbeddedSpaces` metoda se nezdařila, jak ukazuje následující obrázek: ![Průzkumníku testování reporting testu se nezdařila.](media/lut-start/test-failure.png)

1. Vyberte okně, které se zobrazí kód knihovny. Všimněte si, že Live testování částí se rozšířila pokrytí kódu k `HasEmbeddedSpaces` metoda. Také sestavy zkušební selhání přidáním zobrazí červený "🞩" řádcích předmětem selhání testy.

1. Pozastavte ukazatel myši nad řádek s `HasEmbeddedSpaces` podpis metody. Za provozu testování částí zobrazí popis, který hlásí, že metoda je popsaná v jeden test, jak ukazuje následující obrázek:

   ![Živé informace testování částí v testu se nezdařila.](media/lut-start/test-failure-info-cs.png)

1. Vyberte chybných **TestHasEmbeddedSpaces** otestovat. Všimněte si, že zobrazuje Live testování částí nabízí řadu možností, jako je například spouštění všech testů, vyberte testů, ladění všechny testy a ladění vyberete testy, jako na následujícím obrázku:

   ![Živé možnosti testování částí pro testu se nezdařila.](media/lut-start/test-failure-options.png)

1. Vyberte **ladění vybrané** k ladění selhání testu.

1. Visual Studio provede test v režimu ladění. Naše testovací přiřadí proměnné s názvem každý řetězec v matici `phrase` a předává jej do `HasEmbeddedSpaces` metoda. Spuštění programu pozastaví a vyvolá čas ladicí program první výraz assert `false`. Dialogové okno výjimka, která je výsledkem Neočekávaná hodnota v [ `Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue` ](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.istrue) volání metody, které je znázorněno na následujícím obrázku.

   ![Za provozu dialogu výjimka testování jednotky.](media/lut-start/exception-dialog-cs.png)

   Všechny ladicí nástroje, které Visual Studio poskytuje kromě toho jsou k dispozici a pomoci tak řešení potíží s naše neúspěšných testů, jak ukazuje následující obrázek:

   ![Ladění nástrojů Visual Studio.](media/lut-start/debugging-tools-cs.png)

   Poznámka: v **automobily** okno, hodnota `phrase` proměnné je "Name\tDescription", což je druhý prvkem pole. Test metoda očekává `HasEmbeddedSpaces` vrátit `true` při je předán tento řetězec; místo toho vrátí `false`. Je zřejmé nerozpozná "\t", karta znak, jako vložené místo.

1. Vyberte **ladění**, **pokračovat**, stiskněte klávesu F5, nebo klikněte na tlačítko **pokračovat** tlačítka na panelu nástrojů Chcete pokračovat v provádění programu test. Vzhledem k tomu, že došlo k neošetřené výjimce, test se ukončí.

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Přidejte následující metodu do testovacího souboru:

    [!code-vb[The TestHasEmbeddedSpaces test method](samples/snippets/visual-basic/lut-start/unittest2.vb#3)]

1. Když provede test, Live testování částí znamená, že `TestHasEmbeddedSpaces` metoda se nezdařila, jak ukazuje následující obrázek:

   ![Průzkumník testování reporting testu se nezdařila.](media/lut-start/test-failure.png)

1. Vyberte okně, které se zobrazí kód knihovny. Všimněte si, že Live testování částí se rozšířila pokrytí kódu k `HasEmbeddedSpaces` metoda. Také sestavy zkušební selhání přidáním zobrazí červený "🞩" řádcích předmětem selhání testy.

1. Pozastavte ukazatel myši nad řádek s `HasEmbeddedSpaces` podpis metody. Za provozu testování částí zobrazí popis, který hlásí, že metoda je popsaná v jeden test, jak ukazuje následující obrázek:

   ![Živé informace testování částí v testu se nezdařila.](media/lut-start/test-failure-info-vb.png)

1. Vyberte chybných **TestHasEmbeddedSpaces** otestovat. Všimněte si, že zobrazuje Live testování částí nabízí řadu možností, jako je například spouštění všech testů, vyberte testů, ladění všechny testy a ladění vyberete testy, jako na následujícím obrázku:

   ![Živé možnosti testování částí pro testu se nezdařila.](media/lut-start/test-failure-options.png)

1. Vyberte **ladění vybrané** k ladění selhání testu.

1. Visual Studio provede test v režimu ladění. Naše testovací přiřadí proměnné s názvem každý řetězec v matici `phrase` a předává jej do `HasEmbeddedSpaces` metoda. Spuštění programu pozastaví a vyvolá čas ladicí program první výraz assert `false`. Dialogové okno výjimka, která je výsledkem Neočekávaná hodnota v [ `Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue` ](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.istrue) volání metody, které je znázorněno na následujícím obrázku.

   ![Za provozu dialogu výjimka testování jednotky.](media/lut-start/exception-dialog-vb.png)

   Všechny ladicí nástroje, které Visual Studio poskytuje kromě toho jsou k dispozici a pomoci tak řešení potíží s naše neúspěšných testů, jak ukazuje následující obrázek:

   ![Ladění nástrojů Visual Studio.](media/lut-start/debugging-tools-vb.png)

   Poznámka: v **automobily** okno, hodnota `phrase` je proměnná "Název" + vbTab + "Popis", což je druhý prvkem pole. Test metoda očekává `HasEmbeddedSpaces` vrátit `true` při je předán tento řetězec; místo toho vrátí `false`. Je zřejmé nerozpozná znak tabulátoru jako vložené místo.

1. Vyberte **ladění**, **pokračovat**, stiskněte klávesu F5, nebo klikněte na tlačítko **pokračovat** tlačítka na panelu nástrojů Chcete pokračovat v provádění programu test. Vzhledem k tomu, že došlo k neošetřené výjimce, test se ukončí.

---

To poskytuje dostatek informací pro předběžné šetření o chybě. Buď `TestHasEmbeddedSpaces`, rutina testu, provedené nesprávný předpokládá, nebo `HasEmbeddedSpaces` správně nerozpoznává všechny mezery. K určení a vyřešení problému, začínat `StringLibrary.HasEmbeddedSpaces` metoda:

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
1. Podívejte se na porovnání v `HasEmbeddedSpaces` metoda. Považuje vložené místo jako U + 0020. Ale obsahuje standardu Unicode a počet dalších znaků místa. To naznačuje, že kód knihovny testovala nesprávně pro prázdný znak.

1. Porovnání rovnosti nahraďte volání <xref:System.Char.IsWhiteSpace%2A?displayProperty=fullName> metoda:

    [!code-csharp[The TestHasEmbeddedSpaces test method](samples/snippets/csharp/lut-start/program2.cs#1)]

1. Za provozu jednotkové testování automaticky opakovaně metodu neúspěšných testů a výsledky v okně kódu a v aktualizací **testování Explorer**, jak je vidět na následujícím obrázku:

    ![Úspěšné HasEmbeddedSpaces test.](media/lut-start/test-success-cs.png)

# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
1. Podívejte se na porovnání v `HasEmbeddedSpaces` metoda. Považuje vložené místo jako U + 0020. Ale obsahuje standardu Unicode a počet dalších znaků místa. To naznačuje, že kód knihovny testovala nesprávně pro prázdný znak.

1. Porovnání rovnosti nahraďte volání <xref:System.Char.IsWhiteSpace%2A?displayProperty=fullName> metoda:

    [!code-vb[The TestHasEmbeddedSpaces test method](samples/snippets/visual-basic/lut-start/class2.vb#1)]

1. Za provozu jednotkové testování automaticky znovu spustí metodu neúspěšných testů a výsledky v okně kódu a v aktualizací **testování Explorer**, jak je vidět na následujícím obrázku:

    ![Úspěšné HasEmbeddedSpaces test.](media/lut-start/test-success-vb.png)

---

## <a name="see-also"></a>Viz také
[Live testování v sadě Visual Studio částí](live-unit-testing.md)
[za provozu jednotky testování často kladené dotazy](live-unit-testing-faq.md)
