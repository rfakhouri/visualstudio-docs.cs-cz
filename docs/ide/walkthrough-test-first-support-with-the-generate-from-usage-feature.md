---
title: 'Návod: Vývoj včasného testování s funkcí generování před využitím | Microsoft Docs'
ms.custom: ''
ms.date: 10/09/2017
ms.technology: vs-ide-general
dev_langs:
- VB
- CSharp
ms.topic: conceptual
helpviewer_keywords:
- Generate From Usage
- Test-First Development
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8bf7a4a4f78ca0de8594a95681c6a5118f1083cc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-test-first-development-with-the-generate-from-usage-feature"></a>Návod: Vývoj včasného testování s funkcí generování před využitím

Toto téma ukazuje, jak používat [generování před využitím](../ide/visual-csharp-intellisense.md#generate-from-usage) funkci, která podporuje vývoj včasného testování.  
  
 *Včasného testování vývoj* je přístup k softwaru návrh, ve kterém nejprve zápis testů částí podle specifikace produktů a pak zapsat zdrojový kód, který je potřeba provést testy úspěšné. Visual Studio podporuje vývoj s včasným testovací tak, že při první odkazu je v testovacích případů, než jsou definovány generuje nové typy a členy ve zdrojovém kódu.  
  
 Visual Studio generuje nové typy a členy s minimálním vlivem na pracovní postup. Můžete vytvořit zástupných procedur pro typy, metody, vlastnosti, pole nebo konstruktory bez opuštění vaše aktuální umístění v kódu. Otevřete dialogové okno pro určení možností pro generování typu, pak se fokus vrátí okamžitě aktuální otevřete soubor zavře dialogové okno.  
  
 Funkce generování před využitím můžete použít s systémů testů, které se integrují s Visual Studio. V tomto tématu je ukázán Microsoft Unit Testing Framework.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-create-a-windows-class-library-project-and-a-test-project"></a>Vytvoření projektu knihovny tříd Windows a testovacího projektu  
  
1.  V [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] nebo [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], vytvořte novou **knihovny tříd Windows** projektu. Pojmenujte ji `GFUDemo_VB` nebo `GFUDemo_CS`, v závislosti na jazyk, který používáte.  
  
2.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na ikonu řešení v horní části, zvolte **přidat**a potom zvolte **nový projekt**. V levém podokně **nový projekt** dialogovém okně vyberte **Test**.  
  
3.  V prostředním podokně vyberte **projektu testování částí** a přijměte výchozí název UnitTestProject1. Následující obrázek znázorňuje dialogové okno, když se objeví v [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]. V [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)], dialogové okno bude vypadat podobně jako.  
  
     ![Dialogové okno Nový projekt Test](../ide/media/newproject_test.png "NewProject_Test")  
  
4.  Zvolte **OK** zavřete **nový projekt** dialogové okno.  

### <a name="to-add-a-reference-to-the-class-library-project"></a>Chcete-li přidat odkaz na projekt knihovny tříd

1.  V **Průzkumníku řešení**, v rámci vaší jednotky testování projektu, klikněte pravým tlačítkem myši **odkazy** položku a zvolte **přidat odkaz na**.

2.  V **správce odkazů** dialogové okno, vyberte **projekty** a pak vyberte projektu knihovny tříd.

3.  Zvolte **OK** zavřete **správce odkazů** dialogové okno.  
    
4.  Řešení uložte. Teď jste připravení Zahájit zápis testů.  
  
### <a name="to-generate-a-new-class-from-a-unit-test"></a>Vygenerujte novou třídu z testování částí  
  
1.  Testovací projekt obsahuje soubor s názvem UnitTest1. Dvakrát klikněte na tento soubor **Průzkumníku řešení** a otevře se v editoru kódu. Vygenerování testu třídy a metoda testovací.  
  
2.  Vyhledejte deklaraci pro třídu `UnitTest1` a přejmenujte ji na `AutomobileTest`.  
  
 > [!NOTE]
 >  IntelliSense pro dokončování IntelliSense nyní poskytuje dvě alternativy: *režim dokončení* a *režim návrhu*. Použijte režim návrhu pro situace, ve kterých se používají třídy a členové předtím, než jsou definovány. Pokud je otevřené okno technologie IntelliSense, můžete stisknout **Ctrl + Alt + mezerník** k přepnutí mezi dokončení režim a režim návrhu. V tématu [pomocí IntelliSense](../ide/using-intellisense.md) Další informace. Režim návrhu vám pomůže při psaní `Automobile` v dalším kroku.  
  
3.  Vyhledejte `TestMethod1()` metoda a přejmenujte ji na `DefaultAutomobileIsInitializedCorrectly()`. Uvnitř této metody vytvořit novou instanci třídy s názvem `Automobile`, jak je vidět na následujících snímcích obrazovky. Podtržení vlnovkou se zobrazí, což značí chybu kompilace a [rychlé akce](../ide/quick-actions.md) žárovky se zobrazí na levém okraji (C# pouze) nebo přímo pod vlnovka při umístění nad ním.  
  
     ![Rychlé akce v jazyce Visual Basic](../ide/media/genclass_underlinevb.png "GenClass_UnderlineVB")  

     ![Rychlé akce v jazyce C&#35;](../ide/media/genclass_underline.png "GenClass_Underline")  
  
4.  Zvolte nebo klikněte na tlačítko žárovky rychlé akce. Zobrazí se chybová zpráva, která uvádí, že typ `Automobile` není definován. Také se zobrazí některá řešení.  
  
5. Klikněte na tlačítko **vygenerovat nový typ...**  otevřete **generovat typ** dialogové okno. Toto dialogové okno obsahuje možnosti, které zahrnují generování typ v na jiný projekt.  

6. V **projektu** seznamu, klikněte na tlačítko **GFUDemo\_VB** nebo **GFUDemo_CS** dáte pokyn, aby soubor přidat do projektu knihovny tříd místo testu sady Visual Studio projekt. Pokud již není vybrána, vyberte **vytvořit nový soubor** a pojmenujte ji **Automobile.cs** nebo **Automobile.vb**.  
  
     ![Generovat dialogové okno Nový typ](../ide/media/genotherdialog.png "GenOtherDialog")  
  
6.  Klikněte na tlačítko **OK** zavřete dialogové okno a vytvořte nový soubor.  
  
7.  V **Průzkumníku**, podívejte se do části GFUDemo_VB nebo GFUDemo_CS uzel projektu a ověřte, zda nový Automobile.vb nebo Automobile.cs souboru je k dispozici. V editoru kódu zaměřuje se pořád ještě v `AutomobileTest.DefaultAutomobileIsInitializedCorrectly`, což umožňuje dál zapisovat svůj test s minimální přerušení.  
  
### <a name="to-generate-a-property-stub"></a>Generování zástupných procedur vlastnost  
Předpokládejme, že specifikaci stavů, které `Automobile` třída má dvě veřejné vlastnosti s názvem `Model` a `TopSpeed`. Tyto vlastnosti musí být inicializovaný s výchozí hodnoty `"Not specified"` a `-1` ve výchozí konstruktor. Následující testování částí ověří, že výchozí konstruktor nastaví vlastnosti na správné výchozí hodnoty.  
  
1. Přidejte následující řádek kódu `DefaultAutomobileIsInitializedCorrectly` test metody.  
  
     [!code-csharp[VbTDDWalkthrough#1](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_1.cs)]
     [!code-vb[VbTDDWalkthrough#1](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_1.vb)]  
  
2. Protože kód odkazuje na dvě vlastnosti nedefinované `Automobile`, vlnovkou se zobrazí pod `Model` a `TopSpeed`. Pozastavte ukazatel myši nad `Model` a zvolte žárovky rychlé akce, a potom vyberte **generovat vlastnost 'Automobile.Model'**.  

3. Vlastnost zástupnou proceduru pro generování `TopSpeed` vlastnost stejným způsobem.  
  
     V `Automobile` třída, typy nové vlastnosti jsou správně odvodit z kontextu.  
  
### <a name="to-generate-a-stub-for-a-new-constructor"></a>Generování zástupných procedur pro nový konstruktor  
Teď vytvoříme testovací metodu, která způsobí vygenerování konstruktor zástupnou proceduru k chybě při inicializaci `Model` a `TopSpeed` vlastnosti. Později přidáte další kód pro dokončení testu.  

1. Přidat další metody pro vaše `AutomobileTest` třídy.  
  
     [!code-csharp[VbTDDWalkthrough#2](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_2.cs)]
     [!code-vb[VbTDDWalkthrough#2](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_2.vb)]  
  
2.  Klikněte na tlačítko žárovky rychlé akce v rámci červenou vlnovkou a potom klikněte na **konstruktor generovat v 'Auto'**.  

     V `Automobile` třídy souboru, Všimněte si, že má nové konstruktor zkontrolován názvy místní proměnné, které se používají ve volání konstruktoru, nalezeny vlastnosti, které mají stejné názvy v `Automobile` třídy a zadaný kód v těle konstruktor na ukládání hodnot argumentů v `Model` a `TopSpeed` vlastnosti.
  

3.  Po vygenerování nového konstruktor vlnovkou se zobrazí pod volání výchozí konstruktor v `DefaultAutomobileIsInitializedCorrectly`. Chybová zpráva uvádí, že `Automobile` třída nemá žádný konstruktor, který nepřijímá žádné argumenty. Pokud chcete vygenerovat explicitní výchozí konstruktor, který nemá žádné parametry, klikněte na žárovky rychlé akce a potom klikněte na **konstruktor generovat v 'Auto'**.  
  
### <a name="to-generate-a-stub-for-a-method"></a>Generování zástupných procedur pro metodu  
Předpokládejme, že specifikace uvádí, že nový `Automobile` můžou být přepnuté do stavu spuštění, pokud jeho `Model` a `TopSpeed` něco jiného než výchozí hodnoty jsou nastaveny vlastnosti.  

1. Přidejte následující řádky, které se `AutomobileWithModelNameCanStart` metoda.
  
     [!code-csharp[VbTDDWalkthrough#3](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_3.cs)]
     [!code-vb[VbTDDWalkthrough#3](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_3.vb)]  
  
2.  Klikněte na tlačítko žárovky rychlé akce pro `myAuto.Start` metoda volání a pak klikněte na tlačítko **generovat metoda 'Automobile.Start'**.  
  
3.  Klikněte na tlačítko žárovky rychlé akce pro `IsRunning` vlastnost a potom klikněte na **generovat vlastnost 'Automobile.IsRunning'**.  

     `Automobile` Třída teď obsahuje metodu s názvem `Start()` a vlastnost s názvem `IsRunning`.  
  
### <a name="to-run-the-tests"></a>Pokud chcete spustit testy  
  
1.  Na **Test** nabídce zvolte **spustit**, **všechny testy**.  

     **Spustit**, **všechny testy** příkaz spustí všechny testy v žádné test rozhraní, které jsou napsané pro aktuální řešení. V takovém případě jsou dva testy a obě selžou, podle očekávání. `DefaultAutomobileIsInitializedCorrectly` Test se nezdaří, protože `Assert.IsTrue` podmínka vrátí `False`. `AutomobileWithModelNameCanStart` Test se nezdaří, protože `Start` metoda v `Automobile` třída vyvolá výjimku.  
  
     **Výsledky testů** okno je znázorněno na následujícím obrázku.  
  
     ![Výsledky testu, který selhal](../ide/media/testsfailed.png "TestsFailed")  
  
2.  V **výsledky testu** okno, dvakrát klikněte na každý řádek výsledků testu do přejděte do umístění každého testu.  
  
### <a name="to-implement-the-source-code"></a>K implementaci zdrojový kód  
  
1.  Přidejte následující kód do výchozí konstruktor, který `Model`, `TopSpeed` a `IsRunning` vlastnosti jsou inicializovány na správné výchozí hodnoty z `"Not specified"`, `-1`, a `False` (nebo `false` pro jazyk C#).  
  
     [!code-csharp[VbTDDWalkthrough#5](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_5.cs)]
     [!code-vb[VbTDDWalkthrough#5](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_5.vb)]  
  
2.  Když `Start` metoda je volána, je potřeba nastavit `IsRunning` příznak na hodnotu true, pouze pokud `Model` nebo `TopSpeed` něco jiného než jejich výchozí hodnoty jsou nastaveny vlastnosti. Odeberte `NotImplementedException` z metody textu a přidejte následující kód.  
  
     [!code-csharp[VbTDDWalkthrough#6](../ide/codesnippet/CSharp/walkthrough-test-first-support-with-the-generate-from-usage-feature_6.cs)]
     [!code-vb[VbTDDWalkthrough#6](../ide/codesnippet/VisualBasic/walkthrough-test-first-support-with-the-generate-from-usage-feature_6.vb)]  
  
### <a name="to-run-the-tests-again"></a>Pokud chcete znovu spustit testy  
  
- Na **Test** nabídky, přejděte na příkaz **spustit**a potom klikněte na **všechny testy**.  

     Tentokrát jsou testy úspěšné. **Výsledky testů** okno je znázorněno na následujícím obrázku.  
  
     ![Výsledky testu, který předává](../ide/media/testspassed.png "TestsPassed")
  
## <a name="see-also"></a>Viz také  
 [Generování před využitím](../ide/visual-csharp-intellisense.md#generate-from-usage)   
 [Psaní kódu](../ide/writing-code-in-the-code-and-text-editor.md)   
 [Používání atributu IntelliSense](../ide/using-intellisense.md)   
 [Testování částí kódu](../test/unit-test-your-code.md)  
 [Rychlé akce](../ide/quick-actions.md)  