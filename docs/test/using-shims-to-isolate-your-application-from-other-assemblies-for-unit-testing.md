---
title: "Izolace aplikace od ostatních sestavení pro testování částí pomocí překrytí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d2a34de2-6527-4c21-8b93-2f268ee894b7
caps.latest.revision: "12"
ms.author: douge
manager: douge
ms.openlocfilehash: b95b4754af66c39d741b7df8a74a433ff812f834
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing"></a>Izolace aplikace od ostatních sestavení pomocí překrytí za účelem testování částí
**Kód Shim typy** jsou jedním z dvě technologie, které systém Fakes Microsoft použije k vám umožní snadno izolovat součásti testovaného z prostředí. Překrytí přesměrovat volání konkrétní metody kód, který zapisuje jako součást svůj test. Mnoho způsobů vrátí odlišné výsledky závislé na externí podmínkách, ale doplňkový kód je pod kontrolou svůj test a konzistentní výsledky při každém volání můžete vrátit. Jednodušší testů k zápisu.  
  
 Izolace kódu ze sestavení, které nejsou součástí vašeho řešení pomocí překrytí. Součástí řešení od sebe navzájem izolovat, doporučujeme použít zástupných procedur.  
  
 Přehled a rychle začít pokyny, najdete v části [izolace kódu v rámci testu s Microsoft Fakes](../test/isolating-code-under-test-with-microsoft-fakes.md)  
  
 **Požadavky**  
  
-   Visual Studio Enterprise  
  
 V tématu [Video (1 hod 16): testování zrušení možností intenzivního testování kódu pomocí zástupného rozhraní v sadě Visual Studio 2012](http://go.microsoft.com/fwlink/?LinkId=261837)  
  
## <a name="in-this-topic"></a>V tomto tématu  
 Je zde získáte informace v tomto tématu:  
  
 [Příklad: Určená chyb](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md#BKMK_Example__The_Y2K_bug)  
  
 [Jak používat překrytí](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md#BKMK_Fakes_requirements)  
  
-   [Přidat Fakes sestavení](#AddFakes)  
  
-   [Použití ShimsContext](#ShimsContext)  
  
-   [Zápis testů s překrytí](#WriteTests)  
  
 [Překrytí pro různé druhy metody](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md#BKMK_Shim_basics)  
  
-   [Statické metody](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md#BKMK_Static_methods)  
  
-   [Instance metody (pro všechny instance)](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md#BKMK_Instance_methods__for_all_instances_)  
  
-   [Instance metody (pro jednu instanci modulu runtime)](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md#BKMK_Instance_methods__for_one_instance_)  
  
-   [Konstruktory](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md#BKMK_Constructors)  
  
-   [Základní členy](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md#BKMK_Base_members)  
  
-   [Statické konstruktory](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md#BKMK_Static_constructors)  
  
-   [Finalizační metody](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md#BKMK_Finalizers)  
  
-   [Privátní metody](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md#BKMK_Private_methods)  
  
-   [Rozhraní vazby](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md#BKMK_Binding_interfaces)  
  
 [Změna výchozího chování](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md#BKMK_Changing_the_default_behavior)  
  
 [Přistupuje k zjišťuje prostředí](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md#BKMK_Detecting_environment_accesses)  
  
 [Souběžnosti](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md#BKMK_Concurrency)  
  
 [Volání metody původní z metody shim](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md#BKMK_Calling_the_original_method_from_the_shim_method)  
  
 [Omezení](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md#BKMK_Limitations)  
  
##  <a name="BKMK_Example__The_Y2K_bug"></a>Příklad: Určená chyb  
 Pojďme se metoda, která vyvolá výjimku na 1. ledna 2000:  
  
```csharp  
// code under test  
public static class Y2KChecker {  
    public static void Check() {  
        if (DateTime.Now == new DateTime(2000, 1, 1))  
            throw new ApplicationException("y2kbug!");  
    }  
}  
  
```  
  
 Testování tato metoda je obzvláště problematické, protože program závisí na `DateTime.Now`, metodu, která závisí na počítači je taktovací, prostředí závislé metoda není deterministický. Kromě toho `DateTime.Now` je pomocí statické vlastnosti, takže se zakázaným inzerováním typu nelze použít v tomto poli. Tento problém je symptomatických problému izolace v testování částí: programy, které přímo volání do databáze rozhraní API, komunikovat s webovými službami a tak dále se obtížně testů jednotek, protože jejich logiku závisí na prostředí.  
  
 To je, kde má být použito shim typy. Typy Shim poskytují mechanismus obcházejí libovolné .NET metody delegáta definované uživatelem. Shim typy jsou kód vygenerovaná generátorem Fakes a delegáti, které typy shim nazýváme, používají k určení nového implementace metody.  
  
 Následující test ukazuje, jak chcete použít typ shim `ShimDateTime`, aby vlastní implementaci DateTime.Now:  
  
```csharp  
//unit test code  
// create a ShimsContext cleans up shims   
using (ShimsContext.Create()  
    // hook delegate to the shim method to redirect DateTime.Now  
    // to return January 1st of 2000  
    ShimDateTime.NowGet = () => new DateTime(2000, 1, 1);  
    Y2KChecker.Check();  
}  
  
```  
  
##  <a name="BKMK_Fakes_requirements"></a>Jak používat překrytí  
  
###  <a name="AddFakes"></a>Přidat Fakes sestavení  
  
1.  V Průzkumníku řešení rozbalte vašeho projektu testování částí **odkazy**.  
  
    -   Pokud pracujete v jazyce Visual Basic, je nutné vybrat **zobrazit všechny soubory** v panelu nástrojů Průzkumníka řešení, chcete-li zobrazit seznam odkazů.  
  
2.  Vyberte sestavení, které obsahuje definice třídy, pro které chcete vytvořit překrytí. Například pokud chcete na kód shim data a času, vyberte System.dll  
  
3.  V místní nabídce vyberte **přidat Fakes sestavení**.  
  
###  <a name="ShimsContext"></a>Použití ShimsContext  
 Při použití shim typy v částí unit test framework, musíte zabalit testovacího kódu v `ShimsContext` k řízení životnost vaší překrytí. Pokud jsme to nebyla vyžadují, by vaše překrytí poslední dokud vypnout domény aplikace. Nejjednodušší způsob, jak vytvořit `ShimsContext` je pomocí statické `Create()` metoda, jak je znázorněno v následujícím kódu:  
  
```csharp  
//unit test code  
[Test]  
public void Y2kCheckerTest() {  
  using(ShimsContext.Create()) {  
    ...  
  } // clear all shims  
}  
  
```  
  
 Je důležité k správně uvolnění každý shim kontext. Jak pravidlo, vždy volání `ShimsContext.Create` uvnitř `using` příkaz zajistit správné mažou registrované překrytí. Například může zaregistrovat shim pro metodu test, který nahrazuje `DateTime.Now` metoda s delegáta, který vždy vrátí hodnotu první z ledna 2000. Pokud zapomenete vymazat shimu registrované v metodě test, zbytek testovacím běhu by vždy vrátí hodnotu první z ledna 2000 jako DateTime.Now. To může být suprising a složitá.  
  
###  <a name="WriteShims"></a>Zápis testu s překrytí  
 V testovacího kódu, vložte *detour* pro metodu, kterou chcete zfalšovat. Příklad:  
  
```csharp  
[TestClass]  
public class TestClass1  
{   
        [TestMethod]  
        public void TestCurrentYear()  
        {  
            int fixedYear = 2000;  
  
            using (ShimsContext.Create())  
            {  
              // Arrange:  
                // Detour DateTime.Now to return a fixed date:  
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
  
 Názvy tříd Shim jsou vytvořeny pomocí prefixu `Fakes.Shim` na původní název typu.  
  
 Překrytí práce vložením *detours* do kódu aplikace v rámci testu. Bez ohledu na dojde k volání metody původní, provede systém Fakes detour, tak, aby namísto volání skutečné metoda, se nazývá kód shim.  
  
 Všimněte si, že jsou detours vytvořena a odstranit v době běhu. Vždy je nutné vytvořit detour v rámci dobu životnosti `ShimsContext`. Při uvolnění, budou odebrány všechny překrytí, kterou jste vytvořili, zatímco byla aktivní. Nejlepší způsob, jak to udělat je uvnitř `using` příkaz.  
  
 Můžete se setkat sestavení chyba oznamující, že Fakes obor názvů neexistuje. Tato chyba se zobrazí někdy, když existují další chyby kompilace. Odstraňte ostatní chyby a bude zmizí.  
  
##  <a name="BKMK_Shim_basics"></a>Překrytí pro různé druhy metody  
 Typy Shim umožňují nahraďte jakoukoli metodou .NET, včetně statické metody nebo bez virtuální metody s vlastními delegáti.  
  
###  <a name="BKMK_Static_methods"></a>Statické metody  
 Vlastnosti, které chcete přiřadit statické metody překrytí jsou umístěny v typu shim. Každou vlastnost obsahuje pouze nastavení, která slouží k připojení k cílové metody delegáta. Například zadána třída `MyClass` s statickou metodu `MyMethod`:  
  
```csharp  
//code under test  
public static class MyClass {  
    public static int MyMethod() {  
        ...  
    }  
}  
```  
  
 Jsme můžete připojit shim k `MyMethod` které vždy vrátí hodnotu 5:  
  
```csharp  
// unit test code  
ShimMyClass.MyMethod = () =>5;  
```  
  
###  <a name="BKMK_Instance_methods__for_all_instances_"></a>Instance metody (pro všechny instance)  
 Podobně jako na statické metody instance metody můžete shimmed pro všechny instance. Vlastnosti připojení těchto překrytí jsou umístěny v vnořené typ s názvem AllInstances k zamezení nejasnostem. Například zadána třída `MyClass` s metodou instance `MyMethod`:  
  
```csharp  
// code under test  
public class MyClass {  
    public int MyMethod() {  
        ...  
    }  
}  
```  
  
 Je možné připojit shim k `MyMethod` které vždy vrátí hodnotu 5, bez ohledu na instanci:  
  
```csharp  
// unit test code  
ShimMyClass.AllInstances.MyMethod = () => 5;  
```  
  
 Vygenerovaný typ strukturu ShimMyClass vypadá následující kód:  
  
```csharp  
// Fakes generated code  
public class ShimMyClass : ShimBase<MyClass> {  
    public static class AllInstances {  
        public static Func<MyClass, int>MyMethod {  
            set {  
                ...  
            }  
        }  
    }  
}  
```  
  
 Všimněte si, že Fakes v takovém případě předá runtime instance jako první argument delegáta.  
  
###  <a name="BKMK_Instance_methods__for_one_instance_"></a>Instance metody (pro jednu instanci modulu runtime)  
 Instance metody lze také shimmed podle různých delegáti, podle příjemce volání. To umožňuje stejnou metodu instance do mají různé chování na instanci typu. Vlastnosti, které chcete nastavit tyto překrytí způsoby instance samotného typu shim. Každý typ instancí shim je taky přiřazený k nezpracované instanci shimmed typu.  
  
 Například zadána třída `MyClass` s metodou instance `MyMethod`:  
  
```csharp  
// code under test  
public class MyClass {  
    public int MyMethod() {  
        ...  
    }  
}  
```  
  
 Dva typy shim MyMethod jsme můžete nastavit tak, aby první z nich vždy vrátí hodnotu 5 a druhý vždy vrátí 10:  
  
```csharp  
// unit test code  
var myClass1 = new ShimMyClass()  
{  
    MyMethod = () => 5  
};  
var myClass2 = new ShimMyClass { MyMethod = () => 10 };  
```  
  
 Vygenerovaný typ strukturu ShimMyClass vypadá následující kód:  
  
```csharp  
// Fakes generated code  
public class ShimMyClass : ShimBase<MyClass> {  
    public Func<int> MyMethod {  
        set {  
            ...  
        }  
    }  
    public MyClass Instance {  
        get {  
            ...  
        }  
    }  
}  
```  
  
 Vlastnost Instance se dá dostat instance shimmed skutečný typ:  
  
```csharp  
// unit test code  
var shim = new ShimMyClass();  
var instance = shim.Instance;  
```  
  
 Typ shim také obsahuje implicitní převod na typ shimmed, takže můžete obvykle stačí použít typ shim, jako je:  
  
```csharp  
// unit test code  
var shim = new ShimMyClass();  
MyClass instance = shim; // implicit cast retrieves the runtime  
                         // instance  
```  
  
###  <a name="BKMK_Constructors"></a>Konstruktory  
 Konstruktory můžete také shimmed Chcete-li přiřadit shim typy budoucí objekty. Každý konstruktor je k dispozici jako statickou metodu konstruktor typu shim. Například zadána třída `MyClass` s konstruktor trvá celé číslo:  
  
```csharp  
// code under test  
public class MyClass {  
    public MyClass(int value) {  
        this.Value = value;  
    }  
    ...  
}  
```  
  
 Nastaví typ shim konstruktoru tak, že všechny budoucí instance vrátí -5, když je vyvolán získá hodnotu, bez ohledu na hodnotu v konstruktoru:  
  
```csharp  
// unit test code  
ShimMyClass.ConstructorInt32 = (@this, value) => {  
    var shim = new ShimMyClass(@this) {  
        ValueGet = () => -5  
    };  
};  
```  
  
 Všimněte si, že každý typ shim zpřístupní dva konstruktory. Výchozí konstruktor musí být použit, je potřeba novou instanci, při konstruktor trvá shimmed instance jako argument by měly být použity pouze konstruktor překrytí:  
  
```csharp  
// unit test code  
public ShimMyClass() { }  
public ShimMyClass(MyClass instance) : base(instance) { }  
```  
  
 Vygenerovaný typ strukturu ShimMyClass se podobá followoing kód:  
  
```csharp  
// Fakes generated code  
public class ShimMyClass : ShimBase<MyClass>  
{  
    public static Action<MyClass, int> ConstructorInt32 {  
        set {  
            ...  
        }  
    }  
  
    public ShimMyClass() { }  
    public ShimMyClass(MyClass instance) : base(instance) { }  
    ...  
}  
```  
  
###  <a name="BKMK_Base_members"></a>Základní členy  
 Vlastnosti shim základní členů přístupná pomocí vytváření shim pro základní typ a předáním instance podřízené jako parametr konstruktoru shim základní třídy.  
  
 Například zadána třída `MyBase` s metodou instance `MyMethod` a podtypem `MyChild`:  
  
```csharp  
public abstract class MyBase {  
    public int MyMethod() {  
        ...  
    }  
}  
  
public class MyChild : MyBase {  
}  
  
```  
  
 Nemůžeme nastavit shim z `MyBase` tak, že vytvoříte novou `ShimMyBase` shim:  
  
```csharp  
// unit test code  
var child = new ShimMyChild();  
new ShimMyBase(child) { MyMethod = () => 5 };  
```  
  
 Všimněte si, že je podřízený typ shim implicitně převést na podřízené instance, kdy jako parametr předaný konstruktoru základní shim.  
  
 Vygenerovaný typ strukturu ShimMyChild a ShimMyBase se podobá následující kód:  
  
```csharp  
// Fakes generated code  
public class ShimMyChild : ShimBase<MyChild> {  
    public ShimMyChild() { }  
    public ShimMyChild(Child child)  
        : base(child) { }  
}  
public class ShimMyBase : ShimBase<MyBase> {  
    public ShimMyBase(Base target) { }  
    public Func<int> MyMethod  
    { set { ... } }  
}  
```  
  
###  <a name="BKMK_Static_constructors"></a>Statické konstruktory  
 Typy Shim vystavit statickou metodu `StaticConstructor` na kód shim statického konstruktoru typu. Vzhledem k tomu, že statické konstruktory provedení po pouze, musíte zajistit, aby je shimu dřív, než kteréhokoli člena typu přistupuje.  
  
###  <a name="BKMK_Finalizers"></a>Finalizační metody  
 Finalizační metody nejsou podporovány v napodobeniny.  
  
###  <a name="BKMK_Private_methods"></a>Privátní metody  
 Generátor kódu Fakes vytvoří shim vlastnosti pro privátní metody, které mají v podpisu, tj. parametry a návratový typ viditelné pouze viditelné typy.  
  
###  <a name="BKMK_Binding_interfaces"></a>Rozhraní vazby  
 Když shimmed typ implementuje rozhraní, generátor kódu vysílá metodu, která umožňuje vytvořit vazbu všechny členy z tohoto rozhraní najednou.  
  
 Například zadána třída `MyClass` , která implementuje `IEnumerable<int>`:  
  
```csharp  
public class MyClass : IEnumerable<int> {  
    public IEnumerator<int> GetEnumerator() {  
        ...  
    }  
    ...  
}  
  
```  
  
 Jsme můžete kód shim implementace `IEnumerable<int>` v MyClass voláním metody Bind:  
  
```csharp  
// unit test code  
var shimMyClass = new ShimMyClass();  
shimMyClass.Bind(new List<int> { 1, 2, 3 });  
  
```  
  
 Vygenerovaný typ strukturu ShimMyClass se podobá následující kód:  
  
```csharp  
// Fakes generated code  
public class ShimMyClass : ShimBase<MyClass> {  
    public ShimMyClass Bind(IEnumerable<int> target) {  
        ...  
    }  
}  
  
```  
  
##  <a name="BKMK_Changing_the_default_behavior"></a>Změna výchozího chování  
 Každý typ generovaného shim obsahuje instanci `IShimBehavior` rozhraní, prostřednictvím `ShimBase<T>.InstanceBehavior` vlastnost. Chování je použít vždy, když klient volá instanci členu, který nebyl shimmed explicitně.  
  
 Pokud chování nebyla explicitně nastavena, bude používat instanci vrácený statických `ShimsBehaviors.Current` vlastnost. Ve výchozím nastavení, tato vlastnost vrací chování, které vyvolá `NotImplementedException` výjimka.  
  
 Toto chování lze změnit kdykoli nastavením `InstanceBehavior` vlastnost na jakoukoli instanci shim. Například následující fragment kódu změny shimu chování, neprovede se žádná nebo výchozí hodnotu návratový typ vrátí – to znamená, default(T):  
  
```csharp  
// unit test code  
var shim = new ShimMyClass();  
//return default(T) or do nothing  
shim.InstanceBehavior = ShimsBehaviors.DefaultValue;  
  
```  
  
 Chování lze také změnit globálně pro všechny instance shimmed pro kterou `InstanceBehavior` vlastnost nebyla nastavena explicitně nastavením statických `ShimsBehaviors.Current` vlastnost:  
  
```csharp  
// unit test code  
// change default shim for all shim instances  
// where the behavior has not been set  
ShimsBehaviors.Current =   
    ShimsBehaviors.DefaultValue;  
  
```  
  
##  <a name="BKMK_Detecting_environment_accesses"></a>Přistupuje k zjišťuje prostředí  
 Je možné připojit chování pro všechny členy, včetně statické metody třídy konkrétní typ přiřazením `ShimsBehaviors.NotImplemented` chování statickou vlastnost `Behavior` příslušného typu shim:  
  
```csharp  
// unit test code  
// assigning the not implemented behavior  
ShimMyClass.Behavior = ShimsBehaviors.NotImplemented;  
// shorthand  
ShimMyClass.BehaveAsNotImplemented();  
  
```  
  
##  <a name="BKMK_Concurrency"></a>Souběžnosti  
 Typy Shim platí pro všechna vlákna do domény aplikace a nemají spřažení vláken. Toto je důležité fakt, pokud budete chtít použít test runner, které podporují souběžnosti: testy zahrnující typy shim nelze spustit souběžně. Tato vlastnost není enfored modulem Fakes runtime.  
  
##  <a name="BKMK_Calling_the_original_method_from_the_shim_method"></a>Volání metody původní z metody shim  
 Představte si, že jsme chtěli po ověření názvu souboru předaný metodě ve skutečnosti zápis textu do systému souborů. V takovém případě by chceme volat metodu původní uprostřed metodu shim.  
  
 Prvním přístupem k vyřešení tohoto problému je zabalit volání původní metody delegáta pomocí a `ShimsContext.ExecuteWithoutShims()` jako v následujícím kódu:  
  
```csharp  
// unit test code  
ShimFile.WriteAllTextStringString = (fileName, content) => {  
  ShimsContext.ExecuteWithoutShims(() => {  
  
      Console.WriteLine("enter");  
      File.WriteAllText(fileName, content);  
      Console.WriteLine("leave");  
  });  
};  
  
```  
  
 Další možností je nastavit shim hodnotu null, zavolejte metodu původní a obnovení shimu.  
  
```csharp  
// unit test code  
ShimsDelegates.Action<string, string> shim = null;  
shim = (fileName, content) => {  
  try {  
    Console.WriteLine("enter");  
    // remove shim in order to call original method  
    ShimFile.WriteAllTextStringString = null;  
    File.WriteAllText(fileName, content);  
  }  
  finally  
  {  
    // restore shim  
    ShimFile.WriteAllTextStringString = shim;  
    Console.WriteLine("leave");  
  }  
};  
// initialize the shim  
ShimFile.WriteAllTextStringString = shim;  
  
```  
  
##  <a name="BKMK_Limitations"></a>Omezení  
 Překrytí nelze použít na všechny typy v knihovně .NET základní třída **mscorlib** a **systému**.  
  
## <a name="external-resources"></a>Externí zdroje  
  
### <a name="guidance"></a>Doprovodné materiály  
 [Testování pro nastavené průběžné doručování s Visual Studio 2012 – kapitoly 2: testování částí: testování uvnitř](http://go.microsoft.com/fwlink/?LinkID=255188)  
  
## <a name="see-also"></a>Viz také  
 [Izolace testovaného kódu pomocí zástupného rozhraní Microsoft](../test/isolating-code-under-test-with-microsoft-fakes.md)   
 [Blog Petr Provost: Visual Studio 2012 překrytí](http://www.peterprovost.org/blog/2012/04/25/visual-studio-11-fakes-part-2)   
 [Video (1 hod 16): testování zrušení možností intenzivního testování kódu pomocí zástupného rozhraní v sadě Visual Studio 2012](http://go.microsoft.com/fwlink/?LinkId=261837)
