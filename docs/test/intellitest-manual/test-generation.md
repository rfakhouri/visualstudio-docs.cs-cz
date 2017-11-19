---
title: "Testování generování | Nástroj pro testování Microsoft IntelliTest Developer | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IntelliTest, Test generation
ms.assetid: B6CADFD1-42C7-4FC0-B41F-0E9F8291A702
caps.latest.revision: "56"
ms.author: douge
manager: douge
ms.openlocfilehash: 5bc8b15d2bd8de53cabc11986e9e848aea973c39
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="test-generation"></a>Generování testů

V tradiční testování částí vyžaduje několik přísady dávat dohromady testu:

```
[Test]
void MyTest() {
    // data
    ArrayList a = new ArrayList();

    // method sequence
    a.Add(5);

    // assertions
    Assert.IsTrue(a.Count==1);
    Assert.AreEqual(a[0], 5);
}
```

Test se skládá z různých aspektech:

* Ho opravy [pořadí volání metod](test-generation.md#test-generators)
* Opravuje argumenty, se kterými se nazývají metody; argumenty, které jsou [testování vstupy](input-generation.md)
* Ověřuje zamýšlené chování otestované aplikace uvádí sadu [kontrolní výrazy](#assumptions-and-assertions)

IntelliTest můžete často automaticky určit relevantní argument hodnoty pro další Obecné [parametrizovaných testů částí](#parameterized-unit-testing), které poskytují pořadí volání metod a kontrolní výrazy.

<a name="test-generators"></a>
## <a name="test-generators"></a>Test generátory

IntelliTest vygeneruje testovacích případů vyberete sekvenci metod implementace testovaného provést a pak generování vstupy pro metody při kontrole kontrolní výrazy přes odvozené data.

A [testování částí parametrizované](#parameterized-unit-testing) přímo stavy posloupnost metoda volá v jeho obsahu.

Když IntelliTest potřebuje vytvořit objekty, budou volání konstruktorů a metod vytváření automaticky přidat do pořadí podle potřeby.

<a name="parameterized-unit-testing"></a>
## <a name="parameterized-unit-testing"></a>Parametrizované testování částí

*Parametrizovaných testů částí* (PUT) jsou testy, které trvat parametry. Na rozdíl od tradiční jednotky testy, které jsou obvykle uzavřeny metody, PUT trvat libovolnou sadu parametrů. Je to jednoduché? Ano – odtud IntelliTest se pokusí [generovat (minimální) sadu vstupy](input-generation.md) , [plně zahrnují](input-generation.md#dynamic-code-coverage) kód dosažitelný z testu.

PUT jsou definovány pomocí [PexMethod](attribute-glossary.md#pexmethod) vlastní atribut podobným způsobem Mstestu (nebo NUnit, xUnit). PUT jsou logicky seskupeny do třídy, které jsou označené metody instance [PexClass](attribute-glossary.md#pexclass). Následující příklad ukazuje jednoduchý PUT uložené v **MyPexTest** třídy:

```
[PexMethod]
void ReplaceFirstChar(string target, char c) {

    string result = StringHelper.ReplaceFirstChar(target, c);

    Assert.AreEqual(result[0], c);
}
```

kde **ReplaceFirstChar** je metoda, která nahrazuje první znak řetězce:

```
class StringHelper {
    static string ReplaceFirstChar(string target, char c) {
        if (target == null) throw new ArgumentNullException();
        if (target.Length == 0) throw new ArgumentOutOfRangeException();
        return c + target.Substring(1);
    }
}
```

Z tento test můžete automaticky IntelliTest [generovat vstupy](input-generation.md) pro PUT, který popisuje mnoho cesty provádění otestované kódu. Každé zadané, která se vztahuje provádění různých cesta získá "serializovány" jako testování částí:

```
[TestMethod, ExpectedException(typeof(ArgumentNullException))]
void ReplaceFirstChar0() {
    this.ReplaceFirstChar(null, 0);
}
...
[TestMethod]
void ReplaceFirstChar10() {
    this.ReplaceFirstChar("a", 'c');
}
```

<a name="generic-parameterized"></a>
## <a name="generic-parameterized-unit-testing"></a>Obecné parametrizované testování částí

Testování částí parametrizované může být obecné metody. V takovém případě musí uživatel zadat typy používaný k vytváření instancí metodu pomocí [PexGenericArguments](attribute-glossary.md#pexgenericarguments).

```
[PexClass]
public partial class ListTest {
    [PexMethod]
    [PexGenericArguments(typeof(int))]
    [PexGenericArguments(typeof(object))]
    public void AddItem<T>(List<T> list, T value)
    { ... }
}
```

<a name="allowing-exceptions"></a>
## <a name="allowing-exceptions"></a>Povolení výjimek

IntelliTest poskytuje mnoho atributů ověření ke třídění výjimky do očekávané výjimky a neočekávané výjimky.

Očekávané výjimky generovat záporné testovacích případů s příslušnou poznámkou jako  **ExpectedException (typeof (*xxx*)) **, zatímco neočekávané výjimky generovat selhání testovací případy.

```
[PexMethod, PexAllowedException(typeof(ArgumentNullException))]
void SomeTest() {...}
```

Validátory jsou:

* [PexAllowedException](attribute-glossary.md#pexallowedexception): umožňuje typ konkrétní výjimky z libovolného místa
* [PexAllowedExceptionFromAssembly](attribute-glossary.md#pexallowedexceptionfromassembly): umožňuje typ konkrétní výjimky ze zadaného sestavení
* [PexAllowedExceptionFromType](attribute-glossary.md#pexallowedexceptionfromtype): umožňuje typ konkrétní výjimky ze zadaného typu
* [PexAllowedExceptionFromTypeUnderTest](attribute-glossary.md#pexallowedexceptionfromtypeundertest): umožňuje typ konkrétní výjimky z typu v rámci testu

<a name="internal-types"></a>
## <a name="testing-internal-types"></a>Testování interní typy

IntelliTest můžete "test" interní typy tak dlouho, dokud je uvidí. Pro IntelliTest a zjistit typy následující atribut přidána do produktu nebo testování projektu Visual Studio IntelliTest průvodci:

```
[assembly: InternalsVisibleTo("Microsoft.Pex, PublicKey=002400000480000094000000060200000024000052534131000400000100010007d1fa57c4aed9f0a32e84aa0faefd0de9e8fd6aec8f87fb03766c834c99921eb23be79ad9d5dcc1dd9ad236132102900b723cf980957fc4e177108fc607774f29e8320e92ea05ece4e821c0a5efe8f1645c4c0c93c1ab99285d622caa652c1dfad63d745d6f2de5f17e5eaf0fc4963d261c8a12436518206dc093344d5ad293
```

<a name="assumptions-and-assertions"></a>
## <a name="assumptions-and-assertions"></a>Předpoklady a kontrolní výrazy

Uživatelé mohou používat předpoklady a kontrolní výrazy pro express [předběžné podmínky](#precondition) (předpoklady) a [vstupních](#postcondition) (kontrolní výrazy) o jejich testy. Když IntelliTest generuje sadu hodnot parametrů a "jsou zde popsány" kód, může porušení předpokládá testu. Pokud k tomu dojde, nebude vygenerování testu pro tuto cestu, ale bude bez upozornění ignorovat.

Kontrolní výrazy jsou dobře známé koncept v systémů testů jednotek regulární, takže IntelliTest již "rozumí" integrované **Assert** třídy poskytované každé podporované test framework. Ale většina architektury neposkytují **Assume** třídy. V takovém případě IntelliTest poskytuje [PexAssume](static-helper-classes.md#pexassume) třídy. Pokud nechcete použít existující architekturu test, IntelliTest má také [PexAssert](static-helper-classes.md#pexassert) třídy.

```
[PexMethod]
public void Test1(object o) {
    // precondition: o should not be null
    PexAssume.IsNotNull(o);

    ...
}
```

Konkrétně bez nullness předpokládá můžete být zakódován jako vlastní atribut:

```
[PexMethod]
public void Test2([PexAssumeNotNull] object o)
// precondition: o should not be null
{
   ...
}
```

<a name="precondition"></a>
## <a name="precondition"></a>Předběžnou podmínku.

Předběžné podmínky metody vyjadřoval podmínky, za kterých bude úspěšné metodu.

Obvykle je předpoklad vynucené kontroly parametry a stav objektu a vyvolávání **ArgumentException –** nebo **InvalidOperationException** Pokud je porušeno.

V IntelliTest předpokladem [testování částí parametrizované](#parameterized-unit-testing) vyjádřený [PexAssume](static-helper-classes.md#pexassume).

<a name="postcondition"></a>
## <a name="postcondition"></a>Koncová podmínka

Koncová podmínka metody vyjadřoval podmínky, které by měl obsahovat během a po spuštění metody, za předpokladu, že jeho předpoklady byly původně platný.

Obvykle je koncová podmínka vynucené volání **Assert** metody.

S IntelliTest, koncová podmínka z [testování částí parametrizované](#parameterized-unit-testing) vyjádřený [PexAssert](static-helper-classes.md#pexassert).

<a name="test-failures"></a>
## <a name="test-failures"></a>Selhání při testu
Když generovaného testovacího případu nepovede?

1. Jestliže neskončí v rámci [nakonfigurovat cestu hranice](exploration-bounds.md), je považován za neúspěšný, pokud [TestExcludePathBoundsExceeded](exploration-bounds.md#testexcludepathboundsexceeded) je možnost nastavena

1. V případě, test nastane **PexAssumeFailedException**, neproběhne úspěšně. Ale ho je obvykle odfiltrovat Pokud [TestEmissionFilter](exploration-bounds.md#testemissionfilter) je nastaven na **všechny**

1. Pokud je v rozporu test [assertion](#assumptions-and-assertions), například podle došlo k výjimce porušení assertion jednotky testování framework, se nezdaří

Pokud žádná z výše uvedeného produkují rozhodnutí, testovací úspěšné pouze v případě nevyvolá výjimku. Kontrolní výraz porušení jsou zpracovány stejným způsobem jako výjimky.

<a name="setup-teardown"></a>
## <a name="setup-and-tear-down"></a>Instalační program a přerušit

V rámci integrace s systémů testování IntelliTest podporuje zjišťování a spuštění instalace a přerušit metody.

**Příklad**

```
using Microsoft.Pex.Framework;
using NUnit.Framework;

namespace MyTests
{
    [PexClass]
    [TestFixture]
    public partial class MyTestClass
    {
        [SetUp]
        public void Init()
        {
            // monitored
        }

        [PexMethod]
        public void MyTest(int i)
        {
        }

        [TearDown]
        public void Dispose()
        {
            // monitored
        }
    }
}

```

<a name="further-reading"></a>
## <a name="further-reading"></a>Další čtení

* [Testování, aby vazba kódu](https://blogs.msdn.microsoft.com/visualstudioalm/2015/04/18/smart-unit-tests-test-to-code-binding-test-case-management/)
* [Jeden test pro všechna pravidla](https://blogs.msdn.microsoft.com/visualstudioalm/2015/07/05/intellitest-one-test-to-rule-them-all/)

## <a name="got-feedback"></a>Zpětné vazby máte?

Vystavení vašich nápadů a funkce požadavky na  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
