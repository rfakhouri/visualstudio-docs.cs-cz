---
title: "Izolace testovaného kódu pomocí zástupného rozhraní Microsoft | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
dev.langs:
- VB
- CSharp
ms.topic: article
ms.author: douge
manager: douge
ms.workload: multiple
ms.openlocfilehash: 35189a94ca0cd1bd9bd9b0aa91349fffd847c22b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="isolating-code-under-test-with-microsoft-fakes"></a>Izolace testovaného kódu pomocí zástupného rozhraní Microsoft

Microsoft Fakes slouží k oddělení kód testujete nahrazením dalších částí aplikace pomocí *zástupných procedur* nebo *překrytí*. Jedná se o malé části kódu, které jsou pod kontrolou testů. Díky izolaci testovacího kódu víte, že pokud se test nezdaří, příčina je zde a ne někde jinde. Zástupné procedury a překrytí také umožňují testování kódu, i když jiné části aplikace ještě nefungují.

Jsou dva typy napodobenin:

-   A [se zakázaným inzerováním](#stubs) nahradí třída malé substitute, který implementuje rozhraní stejné.  Pro použití zástupných procedur je nutné navrhnout aplikaci tak, aby jednotlivé součásti závisely pouze na rozhraních a nikoli na ostatních součástech. („Součást“ představuje třídu nebo skupinu tříd, které jsou navrženy a aktualizovány společně a obvykle obsaženy v sestavení.)

-   A [shim](#shims) upraví zkompilovaný kód aplikace za běhu, tak, aby místo provedení volání zadanou metodu, běžel shim kód, který poskytuje svůj test. Překrytí lze použít k nahrazení volání na sestavení, které nelze upravit, například sestavení .NET.

![Fakes nahradit ostatní součásti](../test/media/fakes-2.png "Fakes-2")  

**Požadavky**

-   Visual Studio Enterprise

## <a name="choosing-between-stub-and-shim-types"></a>Volba mezi zástupnou procedurou a překrytím  
Obvykle byste měli považovat projekt sady Visual Studio za součást, protože vytváříte a aktualizujete tyto třídy současně. Měli byste zvážit použití zástupných procedur a překrytí pro volání, která projekt provádí do jiných projektů v rámci vašeho řešení nebo do jiných sestavení, na která projekt odkazuje.  
  
Jako obecné vodítko použijte zástupné procedury pro volání v rámci řešení sady Visual Studio a překrytí použijte pro volání do jiných odkazovaných sestavení. Je to proto, že u vašeho vlastního řešení je vhodné oddělit součásti definováním rozhraní tak, jak vyžaduje vytváření zástupných procedur. Ale externí sestavení, jako například System.dll, nejsou obvykle vybavena samostatnými definicemi rozhraní, takže je nutné místo toho použít překrytí.  
  
Ostatní úvahy:  
  
**Výkon.** Překrytí pracují pomaleji, protože přepisují kód za běhu. Zástupné procedury nemají takové nároky na výkon a jsou stejně rychlé jako virtuální metody.  
  
**Statické metody zapečetěná typy.** Zástupné procedury můžete použít pouze k implementaci rozhraní. Proto nelze použít typy zástupných procedur pro statické metody, nevirtuální metody, zapečetěné virtuální metody, metody v zapečetěných typech atd.  
  
**Vnitřní typy.** S vnitřní typy, které jsou zpřístupněny pomocí atributu sestavení můžete použít zástupných procedur i překrytí <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>.  
  
**Privátní metody.** Překrytí mohou nahradit volání do soukromých metod, pokud jsou viditelné všechny typy v podpisu metody. Zástupné procedury mohou nahradit pouze viditelné metody.  
  
**Rozhraní a abstraktní metody.** Zástupné procedury poskytují implementace rozhraní a abstraktní metody, které lze použít při testování. Překrytí nelze instrumentace rozhraní a abstraktní metody, protože nemají těla metody.  
  
Obecně doporučujeme používat typy zástupných procedur k izolaci od závislostí v rámci vašeho základu kódu. To lze provést skrytím součástí za rozhraní. Typy překrytí lze použít k izolaci od součástí třetích stran, které neposkytují testovatelné rozhraní API.  
  
##  <a name="stubs"></a>Začínáme s zástupných procedur  
Podrobnější popis najdete v tématu [pomocí zástupných procedury za izolace částí aplikace od sebe navzájem pro testování částí](../test/using-stubs-to-isolate-parts-of-your-application-from-each-other-for-unit-testing.md).  
  
1.  **Vložit rozhraní**  
  
     Chcete-li použít zástupné procedury, musíte kód, který chcete otestovat, napsat takovým způsobem, aby explicitně nezmiňoval třídy v jiné součásti aplikace. „Součást“ představuje třídu nebo třídy, které jsou vyvíjeny a aktualizovány společně a obvykle jsou obsaženy v jednom projektu sady Visual Studio. Proměnné a parametry by měly být deklarovány pomocí rozhraní a instance ostatních součástí by měly být předány nebo vytvořeny pomocí továrny. Například pokud je součást StockFeed třídou v jiné součásti aplikace, pak toto bude považováno za chybné:  
  
     `return (new StockFeed()).GetSharePrice("COOO"); // Bad`  
  
     Namísto toho definujte rozhraní, které lze implementovat jinou součástí a které může být také implementováno pomocí zástupné procedury pro testovací účely:  
  
    ```csharp  
    public int GetContosoPrice(IStockFeed feed)  
    { return feed.GetSharePrice("COOO"); }  
  
    ```  
  
    ```vb  
    Public Function GetContosoPrice(feed As IStockFeed) As Integer  
     Return feed.GetSharePrice("COOO")  
    End Function  
  
    ```  
  
2.  **Přidat Fakes sestavení**  
  
    1.  V Průzkumníku řešení rozbalte seznam odkazů k testovacímu projektu. Pokud pracujete v jazyce Visual Basic, musíte zvolit **zobrazit všechny soubory** Chcete-li zobrazit seznam odkazů.  
  
    2.  Vyberte odkaz na sestavení, ve kterém je definováno rozhraní (například IStockFeed). V místní nabídce tohoto odkazu, zvolte **přidat Fakes sestavení**.  
  
    3.  Znovu sestavte řešení.  
  
3.  Ve vašich testech vytvořte instance zástupné procedury a zadejte kód pro jeho metody:  
  
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
  
    Speciální druhem magic tady je třída `StubIStockFeed`. Pro každé rozhraní v odkazovaném sestavení generuje mechanismus rozhraní Microsoft Fakes zástupnou třídu. Název třídy se zakázaným inzerováním je odvozený od názvu rozhraní, s "`Fakes.Stub`" jako předpony a názvy typů parametr, který se připojí.  
  
    Zástupné procedury jsou také generovány pro mechanismy získání a nastavení vlastností, pro události a pro obecné metody. Další informace najdete v tématu [pomocí zástupných procedury za izolace částí aplikace od sebe navzájem pro testování částí](../test/using-stubs-to-isolate-parts-of-your-application-from-each-other-for-unit-testing.md).  
  
##  <a name="shims"></a>Začínáme s překrytí  
(Podrobnější popis najdete v tématu [pomocí překrytí účelem izolace aplikace od ostatních sestavení pro testování částí](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md).)  
  
Předpokládejme, že obsahuje příslušné součásti volání `DateTime.Now`:  
  
```csharp  
// Code under test:  
    public int GetTheCurrentYear()  
    {  
       return DateTime.Now.Year;  
    }  
  
```  
  
Během testování, byste chtěli kód shim `Now` vlastnost, protože skutečná verze inconveniently vrátí jinou hodnotu u každé volání.  
  
Pokud chcete používat překrytí, nemáte upravit kód aplikace nebo zapisují určitým způsobem.  
  
1.  **Přidat Fakes sestavení**  
  
     V Průzkumníku řešení otevřete odkazy vašeho projektu testování částí a vyberte odkaz na sestavení, které obsahuje metodu, kterou chcete zfalšovat. V tomto příkladu `DateTime` třída je v **System.dll**.  Chcete-li zobrazit odkazů v projektu jazyka Visual Basic, zvolte **zobrazit všechny soubory**.  
  
     Zvolte **přidat Fakes sestavení**.  
  
2.  **Vložte doplňkový kód ShimsContext**  
  
    ```csharp  
    [TestClass]  
    public class TestClass1  
    {   
            [TestMethod]  
            public void TestCurrentYear()  
            {  
                int fixedYear = 2000;  
  
                // Shims can be used only in a ShimsContext:  
                using (ShimsContext.Create())  
                {  
                  // Arrange:  
                    // Shim DateTime.Now to return a fixed date:  
                    System.Fakes.ShimDateTime.NowGet =   
                    () =>  
                    { return new DateTime(fixedYear, 1, 1); };  
  
                    // Instantiate the component under test:  
                    var componentUnderTest = new MyComponent();  
  
                  // Act:  
                    int year = componentUnderTest.GetTheCurrentYear();  
  
                  // Assert:   
                    // This will always be true if the component is working:  
                    Assert.AreEqual(fixedYear, year);  
                }  
            }  
    }
    ```

    ```vb  
    <TestClass()> _  
    Public Class TestClass1  
        <TestMethod()> _  
        Public Sub TestCurrentYear()  
            Using s = Microsoft.QualityTools.Testing.Fakes.ShimsContext.Create()  
                Dim fixedYear As Integer = 2000  
                ' Arrange:  
                ' Detour DateTime.Now to return a fixed date:  
                System.Fakes.ShimDateTime.NowGet = _  
                    Function() As DateTime  
                        Return New DateTime(fixedYear, 1, 1)  
                    End Function  
  
                ' Instantiate the component under test:  
                Dim componentUnderTest = New MyComponent()  
                ' Act:  
                Dim year As Integer = componentUnderTest.GetTheCurrentYear  
                ' Assert:   
                ' This will always be true if the component is working:  
                Assert.AreEqual(fixedYear, year)  
            End Using  
        End Sub  
    End Class  
    ```  

    Názvy tříd Shim jsou vytvořeny pomocí prefixu `Fakes.Shim` na původní název typu. Názvy parametrů jsou připojeny k názvu metody. (Nemusíte přidávat žádné sestavení odkaz na System.Fakes.)  

Předchozí příklad používá překrytí pro statickou metodu. Chcete-li použít doplňkový kód pro metodu instance, napište `AllInstances` mezi název typu a název metody:  

```  
System.IO.Fakes.ShimFile.AllInstances.ReadToEnd = ...  
```  

(Neexistuje žádné sestavení 'System.IO.Fakes' Chcete-li. Obor názvů je generován shim procesu vytváření. Ale můžete použít 'pomocí' nebo 'Importovat' obvyklým způsobem.)  

Můžete také vytvořit překrytí pro konkrétní instance, konstruktory a vlastnosti. Další informace najdete v tématu [pomocí překrytí účelem izolace aplikace od ostatních sestavení pro testování částí](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md).  

## <a name="in-this-section"></a>V tomto oddílu  
 [Vzájemná izolace částí aplikace pomocí zástupných procedury za účelem testování jednotek](../test/using-stubs-to-isolate-parts-of-your-application-from-each-other-for-unit-testing.md)  
  
 [Izolace aplikace od ostatních sestavení pomocí překrytí za účelem testování jednotek](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md)  
  
 [Vytváření, kompilace a konvence pojmenování kódu v Napodobeniny Microsoft](../test/code-generation-compilation-and-naming-conventions-in-microsoft-fakes.md)
