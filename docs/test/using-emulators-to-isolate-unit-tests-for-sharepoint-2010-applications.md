---
title: Izolace testů jednotek aplikací pro SharePoint 2010 s použitím emulátorů
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 6a4a9b99da94ef754906b095f99fa812c7474103
ms.sourcegitcommit: d9e4ea95d0ea70827de281754067309a517205a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/29/2018
ms.locfileid: "37117664"
---
# <a name="using-emulators-to-isolate-unit-tests-for-sharepoint-2010-applications"></a>Izolace testů jednotek aplikací pro SharePoint 2010 s použitím emulátorů

Balíček Microsoft.SharePoint.Emulators poskytuje sadu knihoven, které vám pomohou vytvořit testy izolované jednotek aplikací pro Microsoft SharePoint 2010. Použít emulátorů [překrytí](../test/using-shims-to-isolate-your-application-from-other-assemblies-for-unit-testing.md) z [Microsoft Fakes](../test/isolating-code-under-test-with-microsoft-fakes.md) izolace rámec vytvořit jednoduché objekty v paměti, které napodobují nejběžnější objekty a metody rozhraní API služby SharePoint. Pokud není emulovaných metoda služby SharePoint, nebo pokud chcete změnit výchozí chování emulátoru, můžete vytvořit překrytí Fakes výsledky, které chcete poskytnout.

Třídy a metody stávající testovací lze snadno převést na spouštění v kontextu emulátor. Tato funkce umožňuje vytvářet testy duální použití. Duální použití testu může přepínat mezi testy integrace skutečné rozhraní API služby SharePoint a testy izolované jednotek, které používají emulátorů.

##  <a name="BKMK_Requirements"></a> Požadavky

-   Microsoft SharePoint 2010 (SharePoint 2010 Server nebo SharePoint 2010 Foundation)

-   Microsoft Visual Studio Enterprise

-   Balíček NuGet emulátorů Microsoft SharePoint

Měli byste také se seznámit s [základní informace o testování v sadě Visual Studio částí](../test/unit-test-basics.md) a některé znalosti o [Microsoft Fakes](../test/isolating-code-under-test-with-microsoft-fakes.md).

##  <a name="BKMK_The_AppointmentsWebPart_example"></a> Příklad AppointmentsWebPart

AppointmentsWebPart umožňuje zobrazit a spravovat seznam serveru SharePoint událostí.

![Webová část událostí](../test/media/ut_emulators_appointmentswebpart.png)

Otestujeme dvě metody webové části v tomto příkladu:

-   `ScheduleAppointment` Metoda ověří předaný metodě hodnoty položek seznamu a vytvoří novou položku v seznamu na zadané webové služby SharePoint.

-   `GetAppointmentsForToday` Metoda vrátí podrobnosti o události je aktuální.

##  <a name="BKMK_Converting_an_existing_test"></a> Převod existujícího testu

V typické testu metody v součásti služby SharePoint metodu testovací vytvoří dočasný lokality ve službě SharePoint Foundation a přidá součásti služby SharePoint k lokalitě, která vyžaduje testovaného kódu. Metoda testovací potom vytvoří a využije instanci součásti. Na konci testu webu odpojí.

`ScheduleAppointment` Metoda naše testovaného kódu je pravděpodobně jednu z metod první napsané pro komponentu:

```csharp
// method under test
public bool ScheduleAppointment(SPWeb web, string listName, string name,
    string phone, string email, string age, DateTime date, out string errorMsg)
{
    errorMsg = string.Empty;
    var badFormat = this.checkInput(name, phone, email, age);
    if (badFormat)
    {
        errorMsg = "Bad Format";
        return false;
    }
    var exists = this.CheckDuplicate(listName, web, name, phone, email, age, date);
    if (exists)
    {
        errorMsg = "Item already exists";
        return false;
    }
    SPListItemCollection items = web.Lists[listName].Items;
    // create item and populate fields
    SPListItem item = items.Add();
    item["Name"] = name;
    item["Phone"] = phone;
    item["Email"] = email;
    item["Age"] = age;
    item["Date"] = date.ToString("D");
    item.Update();
    return true;
}
```

Prvního testu funkce v `ScheduleAppointment` metoda může vypadat například takto:

```csharp
[TestMethod]
public void ScheduleAppointmentReturnsTrueWhenNewAppointmentIsCreated()
{
    using( var site = new SPSite("http://localhost"))
    using (var webPart = new BookAnAppointmentWebPart())
    {
        // Arrange
        string errorMsg = string.Empty;
        DateTime date = DateTime.Now;
        SPList list = AddListToSiteHelper(site);

        // Act
        bool success = webPart.ScheduleAppointment(site.RootWeb, list.Title,
            "Raisa Pokrovskaya", "425-555-0163", "raisa@outlook.com", "55", date,
            out errorMsg);
        list.Delete();

        // Assert
        Assert.IsTrue(success);
    }
}
```

I když tato metoda ověřte, zda `ScheduleAppointment` metoda správně přidá novou položku do seznamu, je více integrace test webové části než testu konkrétní chování vašeho kódu. Vnější závislosti na SharePoint a rozhraní API služby SharePoint může způsobit, že test selhání důvodů než uživatelského kódu v `ScheduleAppointment` metoda. Režijní náklady v vytváření a zničení web služby SharePoint můžete také provést test příliš pomalé spustit jako s řádnou součástí procesu kódování. Provádění instalační program a odstraňování lokality pro každou metodu testovací pouze sloučeniny problém testů jednotek efektivní developer.

Microsoft SharePoint emulátorů získáte sadu objektů a metoda "zdvojnásobí", které napodobují chování nejběžnější rozhraní API služby SharePoint. Emulované metody jsou lightweight implementace rozhraní API služby SharePoint, které nevyžadují SharePoint ke spuštění. Pomocí Microsoft Fakes k volání rozhraní API služby SharePoint na hodnoty Double metoda služby SharePoint emulátorů obcházejí izolace testů a ujistěte se, že testujete kód, který chcete. Při volání metody služby SharePoint, které nejsou emulovaných, můžete přímo k vytvoření požadované chování Fakes.

###  <a name="BKMK_Adding_the_Emulators_package_to_a_test_project"></a> Probíhá přidávání balíčku emulátorů na zkušební projekt

Přidání emulátorů služby SharePoint do testovacího projektu:

1.  Vyberte k testovacímu projektu v Průzkumníku řešení.

2.  Zvolte **spravovat balíčky NuGet** v místní nabídce.

3.  Hledání **Online** kategorii pro `Microsoft.SharePoint.Emulators`a potom zvolte **nainstalovat**.

![Balíček NuGet emulátorů služby SharePoint](../test/media/ut_emulators_nuget.png)

###  <a name="BKMK__Running_a_test_method_in_the_emulation_context"></a> Spuštění testu metody s emulace

Instalace balíčku přidá odkazy na požadované knihovny do vašich projektů. Chcete-li snadno použitelný emulátorů v existující třídy test, přidat obory názvů `Microsoft.SharePoint.Emulators` a `Microsoft.QualityTools.Testing.Emulators`.

Povolit emulace v zkušební metody, zabalení metoda textu v `using` příkaz, který vytvoří `SharePointEmulationScope` objektu. Příklad:

```csharp
[TestMethod]
public void ScheduleAppointmentReturnsTrueWhenNewAppointmentIsCreated()
{
    // create the emulation scope with a using statement
    using (new SharePointEmulationScope())
    using( var site = new SPSite("http://localhost"))
    using (var webPart = new BookAnAppointmentWebPart())
    {
        // Arrange
        string errorMsg = string.Empty;
        DateTime date = DateTime.Now;
        SPList list = AddListToSiteHelper(site);

        // Act
        bool success = webPart.ScheduleAppointment(site.RootWeb, list.Title,
            "Raisa Pokrovskaya", "425-555-0163", "raisa@outlook.com", "55", date,
            out errorMsg);
        list.Delete();

        // Assert
        Assert.IsTrue(success);
    }
}
```

Po provedení testů metoda volá runtime emulátoru Microsoft Fakes dynamicky vložení kódu do služby SharePoint metod k volání na tyto metody na delegáty, které jsou deklarované v Microsoft.SharePoint.Fakes.dll přesměrovat. Microsoft.SharePoint.Emulators.dll implementuje delegáty pro emulované metody úzce mimicking skutečné chování služby SharePoint. Když součást testovaného nebo testovací metoda volá metodu služby SharePoint, chování, která způsobí, že je u emulaci.

![Emulátor provádění toku](../test/media/ut_emulators_flowchart.png)

##  <a name="BKMK_Creating_dual_use_classes_and_methods"></a> Vytváření duální použití třídy a metody

K vytvoření metody, které lze použít pro obě integrace testy skutečné rozhraní API služby SharePoint a testy izolované jednotek, které používají emulátorů, použijte přetížené konstruktor `SharePointEmulationScope(EmulationMode)` zabalit testovacího kódu metoda. Dvě hodnoty `EmulationMode` výčtu zadejte, zda rozsah používá emulátorů (`EmulationMode.Enabled`) nebo zda oboru používá rozhraní API služby SharePoint (`EmulationMode.Passthrough`).

Můžete zde je ukázka, jak je možné upravit předchozím testu být duální použití:

```csharp
// class level field specifies emulation mode
private const EmulationMode emulatorMode = EmulationMode.Enabled;

[TestMethod]
public void ScheduleAppointmentReturnsTrueWhenNewAppointmentIsCreated()
{
    // emulation scope determined by emulatorMode
    using( SharePointEmulationScope(emulatorMode))
    using( var site = new SPSite("http://localhost"))
    using (var webPart = new BookAnAppointmentWebPart())
    {
        // Arrange
        string errorMsg = string.Empty;
        DateTime date = DateTime.Now;
        SPList list = AddListToSiteHelper(site);

        // Act
        bool success = webPart.ScheduleAppointment(site.RootWeb, list.Title,
            "Raisa Pokrovskaya", "425-555-0163", "raisa@outlook.com", "55", date,
            out errorMsg);
        list.Delete();

        // Assert
        Assert.IsTrue(success);
    }
}
```

## <a name="using-testinitialize-and-testcleanup-attributes-to-create-a-dual-use-test-class"></a>Pomocí TestInitialize a TestCleanup atributy pro vytvoření dual použití testovací – třída

Pokud spustíte všechny nebo většinu testů v třídy pomocí `SharePointEmulationScope`, můžete využít techniky úrovni třídy nastavení emulace režimu.

-   Test metody třídy, které opatřená <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestInitializeAttribute> a <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCleanupAttribute> můžete vytvořit a zrušení oboru.

-   Nastavení `EmulationMode` třída úrovni můžete umožňují automatizovat Změna režimu mezi `EmulationMode.Enabled` a `EmulationMode.Passthrough`.

Metoda třídy s atributem `[TestInitialize]` běží na začátku každého testu metody a metodu, která je opatřená `[TestCleanup]` běží na konci každé metody testu. Je možné deklarovat soukromé pole pro `SharePointEmulationScope` objektu na úrovni třídy, inicializujte ho v `TestInitialize` s atributy metoda a pak uvolnění objektu v `TestCleanup` s atributy metoda.

Můžete použít libovolnou metodu, který zvolíte, k automatizaci výběr `EmulationMode`. Jedním ze způsobů je zkontrolovat existenci symbol pomocí preprocesor – direktivy. Například pokud chcete spustit testovací metody ve třídě s použitím emulátorů, můžete definovat symbol, jako `USE_EMULATION` v souboru projektu testovací nebo na příkazovém řádku sestavení. Pokud je definována symbol, úrovni třídy `EmulationMode` konstanta je deklarovaná a nastavený na `Enabled`. Jinak hodnota je nastaven na konstantu na `Passthrough`.

Tady je příklad testovací třídu, která demonstruje použití direktivy preprocesoru a `TestInitialize` a `TestCleanup` s atributy metody nastavení emulace režimu.

```csharp
//namespace declarations
...

namspace MySPAppTests
{
    [TestClass]
    public class BookAnAppointmentWebPartTests
    {

        // emulationScope is a class level field
        private SharePointEmulationScope emulationScope;

        // preprocessor directives determine the value of emulatorMode
        #if USE_EMULATIONprivate const EmulationMode emulatorMode = EmulationMode.Enabled;#elseprivate const EmulationMode emulatorMode = EmulationMode.Passthrough;#endif

        // InitializeTest sets the emulation scope at the beginning of each test method
        [TestInitialize]public void InitializeTest(){this.emulationScope = new SharePointEmulationScope(emulatorMode);}

        // CleanupTest disposes the emulation scope at the end of each test method
        [TestCleanup]public void CleanupTest(){this.emulationScope.Dispose();}

        [TestMethod]
        public void ScheduleAppointmentReturnsTrueWhenNewAppointmentIsCreated()
        {
            // remove the SharePointEmulationScope using statement from the method
            using( var site = new SPSite("http://localhost"))
            using (var webPart = new BookAnAppointmentWebPart())
            {
                // Arrange
                string errorMsg = string.Empty;
                DateTime date = DateTime.Now;
                SPList list = AddListToSiteHelper(site);

                // Act
                bool success = webPart.ScheduleAppointment(site.RootWeb, list.Title,
                    "Raisa Pokrovskaya", "425-555-0163", "raisa@outlook.com", "55", date,
                    out errorMsg);
                list.Delete()

                // Assert
                Assert.IsTrue(success);
            }
        }

        ...// More tests

    }
}
```

##  <a name="BKMK_Handling_non_emulated_SharePoint_methods"></a> Zpracování – emulace metod služby SharePoint

Ne všechny typy SharePoint emulovaných a ne všechny metody v některé typy emulované emulovaných. Pokud testovaného kódu volá metodu služby SharePoint, která není emulovaných, vyvolá metoda `NotSupportedException` výjimka. Když dojde k výjimce, přidáte shim Fakes pro metodu služby SharePoint.

**Nastavení Fakes služby Sharepoint**

Explicitní volání překrytí Microsoft Fakes:

1.  Pokud chcete na kód shim SharePoint třídu, která není emulovaných, upravte soubor Microsoft.SharePoint.fakes a přidejte třídu do seznamu shimmed třídy. Najdete v článku [konfigurace kódu generování zástupných procedur a překrytí](http://msdn.microsoft.com/library/hh708916.aspx#bkmk_configuring_code_generation_of_stubs) části [vytváření, kompilace a konvence pojmenování ve Microsoft Fakes kódu](../test/code-generation-compilation-and-naming-conventions-in-microsoft-fakes.md).

     ![Fakes složky v Průzkumníku řešení](../test/media/ut_emulators_fakesfilefolder.png)

2.  Projekt znovu sestavte testovací alespoň jednou po instalaci balíčku emulátorů Microsoft SharePoint, a pokud jste upravili Microsoft.SharePoint.Fakes souboru. Sestavení projektu vytvoří a naplní **FakesAssembly** složky v kořenové složce projektu na disku.

     ![FakesAssembly složky](../test/media/ut_emulators_fakesassemblyfolder.png)

3.  Přidat odkaz na **Microsoft.SharePoint.14.0.0.0.Fakes.dll** sestavení, které se nachází v **FakesAssembly** složky.

4.  (Volitelné) Přidat direktivu obor názvů pro třídu testu pro `Microsoft.QualityTools.Testing.Fakes`, `Microsoft.SharePoint.Fakes` a všechny vnořené obor názvů `Microsoft.SharePoint.Fakes`, kterou chcete použít.

**Implementace shim delegáta pro metodu služby SharePoint**

V našem příkladu projektu `GetAppointmentsForToday` volání metod [SPList.GetItems(SPQuery)](http://msdn.microsoft.com/library/ms457534.aspx) metoda API služby SharePoint.

```csharp
// method under test
public string GetAppointmentsForToday(string listName, SPWeb web)
{
    SPList list = web.Lists[listName];
    DateTime today = DateTime.Now;
    var listQuery = new SPQuery{Query = String.Format("<Where><Eq><FieldRef Name='Date'/>" +"<Value Type='Text'>{0}</Value>" +"</Eq></Where>", today.ToString("D"))};
    var result = new System.Text.StringBuilder();
    foreach (SPListItem item in list.GetItems(listQuery))
    {
        result.AppendFormat("Name: {0}, Phone: {1}, Email: {2}, Age: {3}, Date: {4}\n",
            item["Name"], item["Phone"], item["Email"], item["Age"], item["Date"]);
    }
    return result.ToString();
}
```

`SPList.GetItems(SPQuery)` Verzi přetížené `GetItems` není emulovaných metoda. Proto právě zabalení existujícího testu pro `GetAppointmentsForToday` v `SharePoint.Emulation.Scope` skončí s chybou. K vytvoření testu práci, budete muset zapsat implementace delegáta Fakes `ShimSPList.GetItemsSPQuery` , vrátí výsledky, které chcete testovat proti.

Tady je změna metody stávající testovací `GetAppointmentsForTodayReturnsOnlyTodaysAppointments`, která implementuje delegáta Fakes. Požadované změny jsou vyznačeny v komentářích:

> [!IMPORTANT]
> Test metody, které explicitně vytvořit Fakes throw překrytí `ShimNotSupported` výjimka při spuštění testu `EmulationMode.Passthrough` kontextu. K tomuto problému vyhnout, použijte proměnnou nastavit `EmulationMode` hodnotu a zabalení spuštěním kódu Fakes `if` příkaz, který testuje hodnota.

```csharp
// class level field to set emulation mode
private const EmulationMode emulatorMode = EmulationMode.Enabled

[TestMethod]
public void GetAppointmentsForTodayReturnsOnlyTodaysAppointments()
{

    // create the emulation scope with a using statement
    using (var emulationScope = new SharePointEmulationScope(emulatorMode))
    using( var site = new SPSite("http://localhost"))
    using (var webPart = new BookAnAppointmentWebPart())
    {
        // Arrange
        DateTime date = DateTime.Now;
        SPList list = AddListToSiteHelper(site);
        // insert 2 items into list
        AddItemsToListHelper(list, new string[] {"Raisa Pokrovskaya", "425-555-0163",
            "raisa@outlook.com", "55", date.ToString("D") });
        AddItemsToListHelper(list, new string[] {"Francis Totten", "313-555-0100",
            "francis@contoso.com", "42", date.AddDays(1).ToString("D") });

        // use Fakes shims only if emulation is enabled
        if (emulatorMode == EmulationMode.Enabled){var sList = new ShimSPList(list);sList.GetItemsSPQuery = (query) =>{var shim = new ShimSPListItemCollection();shim.Bind(new[] { list.Items[0] });return shim.Instance;}}

        // Act
        string result = webPart.GetAppointmentsForToday(list.Title, site.RootWeb);
        list.Delete();

        // Assert
        Assert.IsTrue(result.Contains(String.Format(
            "Name: Raisa Pokrovskaya, Phone: 425-555-0163, Email: raisa@outlook.com," +
            "Age: 55, Date: {0}", date.ToString("D"))));
        Assert.IsFalse(result.Contains("Name: Francis Totten"));
    }
}
```

Tato metoda nejprve otestovat povolení emulace. Pokud je, nemůžeme vytvořit objekt Fakes shim pro naše `SPList` seznamu a pak vytvořte a přiřaďte metodu pro jeho `GetItemsSPQuery` delegovat. Delegát používá Fakes `Bind` metody přidat položku seznamu správný a `ShimSPListItemCollection` , je vrácen volajícímu.

##  <a name="BKMK_Writing_emulation_tests_from_scratch__and_a_summary"></a> Zápis emulace testy od začátku a souhrn

Přestože techniky k vytvoření emulace a duální použití testy, které jsou popsané v předchozích částech předpokládá, že převádíte existující testy, můžete také použít technik zápis testy od začátku. Následující seznam shrnuje těchto postupů:

-   V projektu testovací použít emulátorů, přidejte do projektu balíček Microsoft.SharePoint.Emulators NuGet.

-   V testu metodu použít emulátorů, vytvoření `SharePointEmulationScope` objektu na začátku metodu. Všechny podporované rozhraní API služby SharePoint bude emulovat, dokud jeho uvolnění.

-   Zápis testovacího kódu, jako když jste zapisovali skutečné rozhraní API služby SharePoint. Kontext emulace automaticky obchází volání metod služby SharePoint k jejich emulátorů.

-   Ne všechny objekty SharePoint emulovaných a emulovaných ne všechny metody některých emulované objektů. A `NotSupportedException` při použití – emulace objekt nebo metoda je vyvolána výjimka. V takovém případě explicitně vytvořte Fakes shim delegáta pro metodu vrátit požadované chování.

-   K vytvoření duální použití testů, použijte `SharePointEmulationScope(EmulationMode)` konstruktor k vytvoření objektu oboru emulace. `EmulationMode` Hodnota určuje, zda jsou volání SharePoint emulovaných nebo spustit pro skutečné web služby SharePoint.

-   Pokud všechny nebo většinu vaše testovací metody ve třídě testovací spuštěn v kontextu emulace, můžete použít úrovni třídy `TestInitialize` s atributy metodu pro vytvoření `SharePointEmulationScope` objekt a pole úrovni třídy, které chcete nastavit režim emulace. To vám pomůže automatizovat Změna režimu emulace. Potom pomocí `TestCleanup` s atributy metoda k uvolnění objektu oboru.

##  <a name="BKMK_Example"></a> Příklad

Tady je příklad konečné, která zahrnuje techniky emulátor služby SharePoint, které jsou popsané výše:

```csharp
using System;
//other namespace declarations
...
// code under test
using MySPApps;
using Microsoft.SharePoint;
// unit testing and emulators
using Microsoft.VisualStudio.TestTools.UnitTesting;
using Microsoft.QualityTools.Testing.Emulators;
using Microsoft.SharePoint.Emulators;
// explicit Fakes shims
using Microsoft.QualityTools.Testing.Fakes;
using Microsoft.SharePoint.Fakes

namspace MySPAppTests
{
    [TestClass]
    public class BookAnAppointmentWebPartTests
    {

        // emulationScope is a class level field
        private SharePointEmulationScope emulationScope;

        // preprocessor directives determine the value of emulatorMode
        #if USE_EMULATION
            private const EmulationMode emulatorMode = EmulationMode.Enabled;
        #else
            private const EmulationMode emulatorMode = EmulationMode.Passthrough;
        #endif

        // InitializeTest sets the emulation scope at the beginning of each test method
        [TestInitialize]
        public void InitializeTest()
        {
            this.emulationScope = new SharePointEmulationScope(emulatorMode);
        }

        // CleanupTest disposes the emulation scope at the end of each test method
        [TestCleanup]
        public void Cleanup()
        {
            this.emulationScope.Dispose();
        }

        [TestMethod]
        public void ScheduleAppointmentReturnsTrueWhenNewAppointmentIsCreated()
        {
            // remove the SharePointEmulationScope using statement from the method
            using( var site = new SPSite("http://localhost"))
            using (var webPart = new BookAnAppointmentWebPart())
            {
                // Arrange
                string errorMsg = string.Empty;
                DateTime date = DateTime.Now;
                SPList list = AddListToSiteHelper(site);

                // Act
                bool success = webPart.ScheduleAppointment(site.RootWeb, list.Title,
                    "Raisa Pokrovskaya", "425-555-0163", "raisa@outlook.com", "55", date,
                    out errorMsg);
                list.Delete()

                // Assert
                Assert.IsTrue(success);
            }
        }

        [TestMethod]
        public void GetAppointmentsForTodayReturnsOnlyTodaysAppointments()
        {

            // remove the SharePointEmulationScope using statement from the method
            using( var site = new SPSite("http://localhost"))
            using (var webPart = new BookAnAppointmentWebPart())
            {
                // Arrange
                DateTime date = DateTime.Now;
                SPList list = AddListToSiteHelper(site);
                // insert 2 items into list
                AddItemsToListHelper(list, new string[] {"Raisa Pokrovskaya", "425-555-0163",
                    "raisa@outlook.com", "55", date.ToString("D") });
                AddItemsToListHelper(list, new string[] {"Francis Totten", "313-555-0100",
                    "francis@contoso.com", "42", date.AddDays(1).ToString("D") });

                // use Fakes shims only if emulation is enabled
                if (emulatorMode == EmulationMode.Enabled)
                {
                    var sList = new ShimSPList(list);

                    sList.GetItemsSPQuery = (query) =>
                    {
                        var shim = new ShimSPListItemCollection();
                        shim.Bind(new[] { list.Items[0] });
                        return shim.Instance;
                    }
                }

                // Act
                string result = webPart.GetAppointmentsForToday(list.Title, site.RootWeb);
                list.Delete();

                // Assert
                Assert.IsTrue(result.Contains(String.Format(
                    "Name: Raisa Pokrovskaya, Phone: 425-555-0163, Email: raisa@outlook.com," +
                    "Age: 55, Date: {0}", date.ToString("D"))));
                Assert.IsFalse(result.Contains("Name: Francis Totten"));
            }
        }

        ...// More tests

    }
}
```

##  <a name="BKMK_Emulated_SharePoint_types"></a> Emulované typy služby SharePoint

[Microsoft.SharePoint.SPField](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPField)

 [Microsoft.SharePoint.SPFieldIndex](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPFieldIndex)

 [Microsoft.SharePoint.SPFieldIndexCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPFieldIndexCollection)

 [Microsoft.SharePoint.SPFieldLink](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPFieldLink)

 [Microsoft.SharePoint.SPFieldLinkCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPFieldLinkCollection)

 [Microsoft.SharePoint.SPFieldUrlValue](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPFieldUrlValue)

 [Microsoft.SharePoint.SPFile](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPFile)

 [Microsoft.SharePoint.SPFileCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPFileCollection)

 [Microsoft.SharePoint.SPFolder](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPFolder)

 [Microsoft.SharePoint.SPFolderCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPFolderCollection)

 [Microsoft.SharePoint.SPItem](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPItem)

 [Microsoft.SharePoint.SPItemEventDataCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPItemEventDataCollection)

 [Microsoft.SharePoint.SPItemEventProperties](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPItemEventProperties)

 [Microsoft.SharePoint.SPList](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPList)

 [Microsoft.SharePoint.SPListCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPListCollection)

 [Microsoft.SharePoint.SPListEventProperties](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPListEventProperties)

 [Microsoft.SharePoint.SPListItem](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPListItem)

 [Microsoft.SharePoint.SPListItemCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPListItemCollection)

 [Microsoft.SharePoint.SPQuery](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPQuery)

 [Microsoft.SharePoint.SPRoleAssignment](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPRoleAssignment)

 [Microsoft.SharePoint.SPRoleAssignmentCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPRoleAssignmentCollection)

 [Microsoft.SharePoint.SPSecurableObject](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPSecurableObject)

 [Microsoft.SharePoint.SPSecurity](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPSecurity)

 [Microsoft.SharePoint.SPSite](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPSite)

 [Microsoft.SharePoint.SPUser](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPUser)

 [Microsoft.SharePoint.SPUserCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPUserCollection)

 [Microsoft.SharePoint.SPView](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPView)

 [Microsoft.SharePoint.SPViewCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPViewCollection)

 [Microsoft.SharePoint.SPViewContext](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPViewContext)

 [Microsoft.SharePoint.SPWeb](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPWeb)

 [Microsoft.SharePoint.SPWebCollection](http://msdn.microsoft.com/library/Microsoft.SharePoint.SPWebCollection)

## <a name="see-also"></a>Viz také:

- [Testování částí kódu](../test/unit-test-your-code.md)
- [Testování aplikací pro SharePoint 2010 pomocí programových testů uživatelského rozhraní](../test/testing-sharepoint-2010-applications-with-coded-ui-tests.md)
- [Vývoj řešení služby SharePoint](../sharepoint/developing-sharepoint-solutions.md)
