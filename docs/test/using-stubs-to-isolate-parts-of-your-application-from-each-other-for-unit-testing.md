---
title: Pomocí zástupných procedury za izolace částí aplikace pro testování v sadě Visual Studio jednotky
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
dev_langs:
- CSharp
- VB
ms.openlocfilehash: 68ee12b330d6b82307de7d590c09259a559716b7
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="use-stubs-to-isolate-parts-of-your-application-from-each-other-for-unit-testing"></a>Izolace částí aplikace od sebe navzájem pro testování částí pomocí zástupných procedur

*Zóny se zakázaným inzerováním* jsou jedním z dvě technologie, které poskytuje umožňují snadno izolovat součást testujete z ostatních komponent, které zavolá rozhraní Microsoft Fakes. Zástupná procedura představuje malou část kódu, která během testování zaujímá místo jiné součásti. Výhodou použití zástupné procedury je to, že vrací konzistentní výsledky, čímž usnadňuje psaní testu. A testy můžete spustit i v případě, že ostatní součásti ještě nefungují.

Přehled a rychlé spuštění Průvodce Fakes, najdete v části [izolace kódu v rámci testu s Microsoft Fakes](../test/isolating-code-under-test-with-microsoft-fakes.md).

Chcete-li použít zástupné procedury, musíte napsat součást tak, aby pro odkazování na ostatní části aplikace používala pouze rozhraní, a nikoliv třídy. To je dobrý postup při návrhu, protože je méně pravděpodobné, že změny v jedné části budou vyžadovat provedení změn i v jiné části. Při testování to umožňuje nahradit zástupnou proceduru reálnou součástí.

Chceme otestovat součást StockAnalyzer uvedenou na obrázku. Obvykle používá další součást RealStockFeed. Ale součást RealStockFeed vrací při každém volání svých metod jiné výsledky, což znesnadňuje testování součásti StockAnalyzer.  Během testování ji nahradíme jinou třídou, StubStockFeed.

![Real a třídy se zakázaným inzerováním požadavkům jedno rozhraní.](../test/media/fakesinterfaces.png)

Vzhledem k tomu, že zástupné procedury závisí na vaší schopnosti strukturovat váš kód tímto způsobem, můžete použít zástupné procedury k izolování jedné části vaší aplikace od jiné. Chcete-li ji izolovat od ostatních sestavení, která nejsou pod vaší kontrolou, jako je například sestavení System.dll, obvykle zřejmě použijete překrytí. V tématu [pomocí překrytí účelem izolace aplikace od ostatních sestavení pro testování částí](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md).

## <a name="how-to-use-stubs"></a>Jak používat zástupné procedury

### <a name="design-for-dependency-injection"></a>Návrh pro vkládání závislostí

Abyste mohli používat zástupné procedury, musí být vaše aplikace navržena tak, aby různé součásti nebyly závislé navzájem, ale byly závislé pouze na definicích rozhraní. Místo toho, aby byly součásti vázány v době kompilace, jsou propojeny v době běhu. Tento způsob napomáhá vytvářet software, který je robustní a snadno aktualizovatelný, protože změny nejsou obvykle přenášeny přes hranice součástí. Doporučujeme následující ho i v případě, že nepoužíváte zástupných procedur. Pokud vytváříte nový kód, je snadné provést [vkládání závislostí](http://en.wikipedia.org/wiki/Dependency_injection) vzor. Při psaní testů pro stávající software jej můžete chtít refaktorovat. V případě, že by to bylo nepraktické, můžete místo toho zvážit použití překrytí.

Začněme toto pojednání motivačních příklad, jeden v diagramu. Třída StockAnalyzer čte ceny akcií a vytváří některé zajímavé výsledky. Má některé veřejné metody, které chceme otestovat. Pro zjednodušení právě podívejme na jednu z těchto metod, velmi jednoduché ten, který hlásí aktuální cena konkrétní sdílenou složku. Chceme napsat jednotkový test této metody. Tady je první koncept testu:

```csharp
[TestMethod]
public void TestMethod1()
{
    // Arrange:
    var analyzer = new StockAnalyzer();
    // Act:
    var result = analyzer.GetContosoPrice();
    // Assert:
    Assert.AreEqual(123, result); // Why 123?
}
```

```vb
<TestMethod()> Public Sub TestMethod1()
    ' Arrange:
    Dim analyzer = New StockAnalyzer()
    ' Act:
    Dim result = analyzer.GetContosoPrice()
    ' Assert:
    Assert.AreEqual(123, result) ' Why 123?
End Sub
```

Jeden problém s tímto testem je okamžitě zřejmý: ceny akcií se liší a výraz tudíž obvykle selže.

Dalším problémem může být, že součást StockFeed, která je použita součástí StockAnalyzer, je stále ve vývoji. Tady je první koncept metody testovaného kódu:

```csharp
public int GetContosoPrice()
{
    var stockFeed = new StockFeed(); // NOT RECOMMENDED
    return stockFeed.GetSharePrice("COOO");
}
```

```vb
Public Function GetContosoPrice()
    Dim stockFeed = New StockFeed() ' NOT RECOMMENDED
    Return stockFeed.GetSharePrice("COOO")
End Function
```

Ve stávající podobě se nemusí tato metoda kompilovat nebo může vyvolat výjimku, protože práce na třídě StockFeed není ještě dokončena. Vložení rozhraní řeší oba tyto problémy. Vložení rozhraní používá následující pravidlo:

Kód žádné součásti aplikace by měla odkazovat nikdy explicitně třídu v jiné součásti, v deklaraci nebo v `new` příkaz. Místo toho by měly být proměnné a parametry deklarovány pomocí rozhraní. Součást instance měly by být vytvořeny pouze součásti kontejneru.

- "Součástí" jsme znamenat třídu nebo skupinu třídy, které jste sami vyvinuli a aktualizovat společně. Součást obvykle představuje kód v jednom projektu sady Visual Studio. Je méně důležité oddělit tříd v rámci jedna součást, protože nejsou aktualizovány ve stejnou dobu.

- Také není tak důležité oddělit součásti od třídy relativně stabilní platformy, jako *System.dll*. Vytvoření rozhraní pro všechny tyto třídy by zbytečně zatěžovalo váš kód.

Kód StockAnalyzer z StockFeed můžete oddělit pomocí rozhraní takto:

```csharp
public interface IStockFeed
{
    int GetSharePrice(string company);
}

public class StockAnalyzer
{
    private IStockFeed stockFeed;
    public StockAnalyzer(IStockFeed feed)
    {
        stockFeed = feed;
    }
    public int GetContosoPrice()
    {
        return stockFeed.GetSharePrice("COOO");
    }
}
```

```vb
Public Interface IStockFeed
    Function GetSharePrice(company As String) As Integer
End Interface

Public Class StockAnalyzer
    ' StockAnalyzer can be connected to any IStockFeed:
    Private stockFeed As IStockFeed
    Public Sub New(feed As IStockFeed)
        stockFeed = feed
    End Sub
    Public Function GetContosoPrice()
        Return stockFeed.GetSharePrice("COOO")
    End Function
End Class
```

V tomto příkladu je součásti StockAnalyzer předána implementace součásti IStockFeed, jakmile je vytvořena. U dokončené aplikace by inicializační kód provedl připojení:

```csharp
analyzer = new StockAnalyzer(new StockFeed());
```

Existují flexibilnější způsoby provedení tohoto připojení. Součást StockAnalyzer by například mohla přijmout objekt factory, který může vytvořit instanci různými implementacemi součásti IStockFeed v různých podmínkách.

### <a name="generate-stubs"></a>Generování zástupných procedur

Jste odpojené třídy, na kterou chcete testovat z jiné součásti, které používá. Oddělení umožňuje vytvořit robustnější a flexibilnější aplikaci a také propojit testovanou součást s implementacemi zástupných procedur rozhraní pro testovací účely.

Můžete jednoduše zapsat zástupné procedury jako třídy obvyklým způsobem. Ale rozhraní Microsoft Fakes vám nabízí dynamičtější způsob vytváření nejvhodnější zástupné procedury pro každý test.

Chcete-li použít zástupné procedury, musíte nejdříve vygenerovat typy zástupných procedur z definic rozhraní.

#### <a name="add-a-fakes-assembly"></a>Přidat Fakes sestavení

1. V Průzkumníku řešení rozbalte vašeho projektu testování částí **odkazy**.

   Pokud pracujete v jazyce Visual Basic, je nutné vybrat **zobrazit všechny soubory** v panelu nástrojů Průzkumníka řešení, chcete-li zobrazit seznam odkazů.

2. Vyberte sestavení, které obsahuje definice rozhraní, pro které chcete vytvořit zástupné procedury.

3. V místní nabídce vyberte **přidat Fakes sestavení**.

### <a name="write-your-test-with-stubs"></a>Psaní testu se zástupnými procedurami

```csharp
[TestClass]
class TestStockAnalyzer
{
    [TestMethod]
    public void TestContosoStockPrice()
    {
      // Arrange:

        // Create the fake stockFeed:
        IStockFeed stockFeed =
             new StockAnalysis.Fakes.StubIStockFeed() // Generated by Fakes.
                 {
                     // Define each method:
                     // Name is original name + parameter types:
                     GetSharePriceString = (company) => { return 1234; }
                 };

        // In the completed application, stockFeed would be a real one:
        var componentUnderTest = new StockAnalyzer(stockFeed);

        // Act:
        int actualValue = componentUnderTest.GetContosoPrice();

        // Assert:
        Assert.AreEqual(1234, actualValue);
    }
    ...
}
```

```vb
<TestClass()> _
Class TestStockAnalyzer

    <TestMethod()> _
    Public Sub TestContosoStockPrice()
        ' Arrange:
        ' Create the fake stockFeed:
        Dim stockFeed As New StockAnalysis.Fakes.StubIStockFeed
        With stockFeed
            .GetSharePriceString = Function(company)
                                       Return 1234
                                   End Function
        End With
        ' In the completed application, stockFeed would be a real one:
        Dim componentUnderTest As New StockAnalyzer(stockFeed)
        ' Act:
        Dim actualValue As Integer = componentUnderTest.GetContosoPrice
        ' Assert:
        Assert.AreEqual(1234, actualValue)
    End Sub
End Class
```

Speciální druhem magic tady je třída `StubIStockFeed`. Pro každý veřejný typ v odkazovaném sestavení generuje mechanismus rozhraní Microsoft Fakes zástupnou třídu. Název třídy se zakázaným inzerováním je odvozený od názvu rozhraní, s "`Fakes.Stub`" jako předpony a názvy typů parametr, který se připojí.

Zástupné procedury jsou také generovány pro mechanismy získání a nastavení vlastností, pro události a pro obecné metody.

### <a name="verify-parameter-values"></a>Ověřte hodnoty parametru

Můžete ověřit, že pokud vaše součást volá jinou součást, jsou předány správné hodnoty. Výraz můžete přidat buď do zástupné procedury, nebo můžete hodnotu uložit a ověřit ji v hlavní části testu. Příklad:

```csharp
[TestClass]
class TestMyComponent
{
    [TestMethod]
    public void TestVariableContosoPrice()
    {
        // Arrange:
        int priceToReturn;
        string companyCodeUsed;
        var componentUnderTest = new StockAnalyzer(new StubIStockFeed()
            {
               GetSharePriceString = (company) =>
                  {
                     // Store the parameter value:
                     companyCodeUsed = company;
                     // Return the value prescribed by this test:
                     return priceToReturn;
                  };
            };
        // Set the value that will be returned by the stub:
        priceToReturn = 345;

        // Act:
        int actualResult = componentUnderTest.GetContosoPrice();

        // Assert:
        // Verify the correct result in the usual way:
        Assert.AreEqual(priceToReturn, actualResult);

        // Verify that the component made the correct call:
        Assert.AreEqual("COOO", companyCodeUsed);
    }
...
}
```

```vb
<TestClass()> _
Class TestMyComponent
    <TestMethod()> _
    Public Sub TestVariableContosoPrice()
        ' Arrange:
        Dim priceToReturn As Integer
        Dim companyCodeUsed As String = ""
        Dim stockFeed As New StockAnalysis.Fakes.StubIStockFeed()
        With stockFeed
            ' Implement the interface's method:
            .GetSharePriceString = _
                Function(company)
                    ' Store the parameter value:
                    companyCodeUsed = company
                    ' Return a fixed result:
                    Return priceToReturn
                End Function
        End With
        ' Create an object to test:
        Dim componentUnderTest As New StockAnalyzer(stockFeed)
        ' Set the value that will be returned by the stub:
        priceToReturn = 345

        ' Act:
        Dim actualResult As Integer = componentUnderTest.GetContosoPrice()

        ' Assert:
        ' Verify the correct result in the usual way:
        Assert.AreEqual(priceToReturn, actualResult)
        ' Verify that the component made the correct call:
        Assert.AreEqual("COOO", companyCodeUsed)
    End Sub
...
End Class
```

## <a name="stubs-for-different-kinds-of-type-members"></a>Zástupné procedury pro různé druhy členů typu

### <a name="methods"></a>Metody

Jak je popsáno v příkladu, mohou být metody zastoupeny připojením delegáta k instanci zástupné třídy. Název typu zástupné procedury je odvozen z názvu metody a parametrů. Například uděleno následující `IMyInterface` rozhraní a metoda `MyMethod`:

```csharp
// application under test
interface IMyInterface
{
    int MyMethod(string value);
}
```

Nemůžeme připojit zástupnou proceduru pro `MyMethod` které vždy vrátí hodnotu 1:

```csharp
// unit test code
var stub = new StubIMyInterface ();
stub.MyMethodString = (value) => 1;
```

Pokud neposkytnete zástupnou proceduru pro funkci, vygeneruje rozhraní Fakes funkci, která vrátí výchozí hodnotu návratového typu. Pro čísla, výchozí hodnota je 0 a pro typy tříd je `null` (C#) nebo `Nothing` (Visual Basic).

### <a name="properties"></a>Vlastnosti

Funkce pro nastavení a získání vlastnosti jsou vystaveny jako samostatní delegáti a mohou být samostatně zastoupeny. Představte si třeba `Value` vlastnost `IMyInterface`:

```csharp
// code under test
interface IMyInterface
{
    int Value { get; set; }
}
```

Jsme přiřadit delegáty metody getter a setter z `Value` k simulaci auto vlastnost:

```csharp
// unit test code
int i = 5;
var stub = new StubIMyInterface();
stub.ValueGet = () => i;
stub.ValueSet = (value) => i = value;
```

Pokud neposkytnete metody zástupných procedur pro funkci nastavení nebo získání vlastnosti, vygeneruje rozhraní Fakes zástupnou proceduru, která ukládá hodnoty, takže zástupná vlastnost funguje jako jednoduchá proměnná.

### <a name="events"></a>Události

Události jsou vystaveny jako pole delegáta. Výsledkem je, že jakoukoli zastoupenou událost lze jednoduše aktivovat vyvoláním pole zálohování události. Zvažte následující rozhraní pro zóny se zakázaným inzerováním:

```csharp
// code under test
interface IWithEvents
{
    event EventHandler Changed;
}
```

Chcete zvýšit `Changed` událostí, můžeme jednoduše vyvolání delegáta zálohování:

```csharp
// unit test code
  var withEvents = new StubIWithEvents();
  // raising Changed
  withEvents.ChangedEvent(withEvents, EventArgs.Empty);
```

### <a name="generic-methods"></a>Obecné metody

Je možné díky delegáta pro každý požadovaný konkretizaci metody zóny se zakázaným inzerováním obecné metody. Mějme například následující rozhraní obsahující obecnou metodu:

```csharp
// code under test
interface IGenericMethod
{
    T GetValue<T>();
}
```

můžete napsat test, který zástupných procedur `GetValue<int>` vytváření instancí:

```csharp
// unit test code
[TestMethod]
public void TestGetValue()
{
    var stub = new StubIGenericMethod();
    stub.GetValueOf1<int>(() => 5);

    IGenericMethod target = stub;
    Assert.AreEqual(5, target.GetValue<int>());
}
```

Kdyby došlo k volání kód `GetValue<T>` s další vytváření instancí, zástupná procedura jednoduše volají chování.

### <a name="stubs-of-virtual-classes"></a>Zástupné procedury virtuálních tříd

V předchozích příkladech byly zástupné procedury vytvořeny z rozhraní. Můžete také vygenerovat zástupné procedury z třídy, která má virtuální nebo abstraktní členy. Příklad:

```csharp
// Base class in application under test
    public abstract class MyClass
    {
        public abstract void DoAbstract(string x);
        public virtual int DoVirtual(int n)
        { return n + 42; }
        public int DoConcrete()
        { return 1; }
    }
```

V zástupné proceduře vygenerované z této třídy můžete nastavit metody delegáta pro DoAbstract() a DoVirtual(), ale nikoliv pro DoConcrete().

```csharp
// unit test
  var stub = new Fakes.MyClass();
  stub.DoAbstractString = (x) => { Assert.IsTrue(x>0); };
  stub.DoVirtualInt32 = (n) => 10 ;
```

Pokud nezadáte delegáta pro virtuální metodu, může rozhraní Fakes zadat buď výchozí chování, nebo může volat metodu v základní třídě. Chcete-li mít základní metoda volána, nastavte `CallBase` vlastnost:

```csharp
// unit test code
var stub = new Fakes.MyClass();
stub.CallBase = false;
// No delegate set - default delegate:
Assert.AreEqual(0, stub.DoVirtual(1));

stub.CallBase = true;
// No delegate set - calls the base:
Assert.AreEqual(43,stub.DoVirtual(1));
```

## <a name="debug-stubs"></a>Ladění zástupných procedur

Typy zástupných procedur jsou navrženy pro zajištění plynulého ladění. Standardně má ladicí program pokyn, aby přešel přes jakýkoli generovaný kód. Měl by tedy vstoupit přímo do vlastních implementací člena, které byly připojeny k zástupné proceduře.

## <a name="stub-limitations"></a>Omezení zástupných procedur

1. Metoda podpisy ukazateli nejsou podporovány.

2. Zapečetěné třídy nebo statické metody nelze prázdná, protože se zakázaným inzerováním typy využívají virtuální metoda odesílání. Pro tyto případy použití shim typy způsobem popsaným v [pomocí překrytí účelem izolace aplikace od ostatních sestavení pro testování částí](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md)

## <a name="change-the-default-behavior-of-stubs"></a>Změnit výchozí chování zástupných procedur

Každý typ generovaného kódu obsahuje instanci `IStubBehavior` rozhraní (prostřednictvím `IStub.InstanceBehavior` vlastnost). Chování je voláno pokaždé, když klient volá člen bez připojeného vlastního delegáta. Pokud chování nebyla nastavena, bude používat instanci vrácený `StubsBehaviors.Current` vlastnost. Ve výchozím nastavení, tato vlastnost vrací chování, které vyvolá `NotImplementedException` výjimka.

Chování lze změnit kdykoli nastavením `InstanceBehavior` vlastnost na jakoukoli instanci se zakázaným inzerováním. Například následující fragment kódu změní chování, neprovede se žádná nebo výchozí hodnotu návratový typ vrátí: `default(T)`:

```csharp
// unit test code
var stub = new StubIFileSystem();
// return default(T) or do nothing
stub.InstanceBehavior = StubsBehaviors.DefaultValue;
```

Chování lze také změnit globálně pro všechny objekty, pro které nebyla nastavena chování nastavením zóny se zakázaným `StubsBehaviors.Current` vlastnost:

```csharp
// Change default behavior for all stub instances
// where the behavior has not been set.
StubBehaviors.Current = BehavedBehaviors.DefaultValue;
```

## <a name="see-also"></a>Viz také

- [Izolace testovaného kódu pomocí zástupného rozhraní Microsoft](../test/isolating-code-under-test-with-microsoft-fakes.md)