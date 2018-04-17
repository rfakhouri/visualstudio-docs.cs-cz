---
title: Přehled | Nástroj pro testování Microsoft IntelliTest Developer | Microsoft Docs
ms.date: 05/02/2017
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- IntelliTest, Visual Studio IntelliTest developer testing tool
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: c5e95091b9305e6802976d19570783459cc47179
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="overview-of-microsoft-intellitest"></a>Přehled Microsoft IntelliTest

IntelliTest umožňuje najít chyby časná a snižuje náklady na údržbu test. Automatizovaná a transparentní testování přístup IntelliTest můžete vygenerovat candidate sada testů kódu .NET. Testovací sady generování můžete provést další podle *správnost vlastnosti* zadáte. IntelliTest bude i momentální testovací sady automaticky jako zpracovaní testovaného kódu.

**Testy charakteristiku** IntelliTest umožňuje určit chování kód z hlediska sada testů tradiční jednotek.
Testovací sady můžete použít jako sada regrese, které tvoří základ k boji složitost spojené s refaktoring starší verze nebo neznámého kódu.

**S průvodcem testovací vstupní generování** IntelliTest používá analýza otevřete kódu a omezení řešení přístupu k automatickému generování přesné testování vstupní hodnoty; obvykle bez nutnosti zásahu uživatele. Pro komplexní typy objektů automaticky vygeneruje objekty pro vytváření. Vstupní generování testů můžete Průvodce rozšířením a konfiguraci objektů Factory podle svých potřeb. Vlastnosti správnost zadané jako kontrolní výrazy ve kódu se taky použije automaticky k další průvodci testovací vstupní generace.

**Integrace IDE** IntelliTest plně integrován do prostředí Visual Studio IDE. Všechny informace shromážděné během generování testovací sada (například automaticky generované vstup výstupu z vašeho kódu, vygenerovaný testovací případy a jejich průchodu nebo neúspěch stav) se zobrazí v prostředí Visual Studio IDE. Můžete snadno iterovat mezi opravě kódu a znovu spustit IntelliTest, aniž byste museli opustit Visual Studio IDE.
Testy můžete uložit do řešení jako projektu testování částí a bude automaticky zjištěn později pomocí Průzkumníka testů Visual Studio.

**Doplnit existující testování postupů** IntelliTest použití, aby doplňovala existující testování postupů, možná již podle.

Pokud chcete testovat:

* Algoritmy přes primitivní datové nebo pole jednoduchých dat:
  * zápis [parametrizovaných testů jednotek](test-generation.md#parameterized-unit-testing)
* Algoritmy přes komplexní data, jako třeba kompilátoru:
  * umožní IntelliTest nejprve vygenerovat reprezentaci abstraktní dat a informační kanál algoritmus
  * umožní IntelliTest sestavení instancí pomocí [vytvoření vlastního objektu](input-generation.md#objects) a výstupních dat podmínek a pak vyvolejte algoritmus
* Kontejnery dat:
  * zápis [parametrizovaných testů jednotek](test-generation.md#parameterized-unit-testing)
  * umožní IntelliTest sestavení instancí pomocí [vytvoření vlastního objektu](input-generation.md#objects) a výstupních dat podmínek a pak vyvolat metodu kontejneru a pak znovu zkontrolovat výstupních podmínek
  * zápis [parametrizovaných testů částí](test-generation.md#parameterized-unit-testing) volání různé metody provedení, v závislosti na hodnoty parametru
* Existujícího základu kódu:
  * pomocí sady Visual Studio IntelliTest Průvodce Začínáme vygenerováním sadu [parametrizovaných testů částí (PUT)](test-generation.md#parameterized-unit-testing)

## <a name="the-hello-world-of-intellitest"></a>Hello World z IntelliTest

IntelliTest vyhledá vstupy relevantní pro otestované programu, což znamená, můžete ho použít ke generování famous **Hello, World!** Řetězec. Předpokladem je, že jste vytvořili na základě jazyka C# Mstestu testovacího projektu a přidat odkaz na **Microsoft.Pex.Framework**. Pokud používáte jiný testovací framework, vytvoření knihovny tříd jazyka C# a test framework dokumentaci o tom, jak nastavit projekt.

Následující příklad vytvoří dvě omezení na parametr s názvem **hodnota** tak, aby IntelliTest vygeneruje požadovaný řetězec:

```csharp
using System;
using Microsoft.Pex.Framework;
using Microsoft.VisualStudio.TestTools.UnitTesting;

[TestClass]
public partial class HelloWorldTest {
    [PexMethod]
    public void HelloWorld([PexAssumeNotNull]string value) {
        if (value.StartsWith("Hello")
            && value.EndsWith("World!")
            && value.Contains(" "))
            throw new Exception("found it!");
    }
}
```

Jakmile zkompilovat a provést, generuje IntelliTest sadu testů jako třeba následující:

1. ""
2. "\0\0\0\0\0"
3. Text "hello"
4. "\0\0\0\0\0\0"
5. "Hello\0"
6. "Hello\0\0"
7. "Hello\0World!"
8. "Hello, World!"

Čtení [generování testů částí s Intellitest](../../test/generate-unit-tests-for-your-code-with-intellitest.md) pochopit uložení generovaného testy. Vygenerovaný testovacího kódu by měla obsahovat testu například následující kód:

```csharp
[TestMethod]
[PexGeneratedBy(typeof(global::HelloWorldTest))]
[PexRaisedException(typeof(Exception))]
public void HelloWorldThrowsException167()
{
    this.HelloWorld("Hello World!");
}
```

Je to snadné!

## <a name="limitations"></a>Omezení

Tato část popisuje omezení IntelliTest:

* [Nondeterminism](#nondeterminism)
* [Souběžnost](#concurrency)
* [Nativní kód .NET](#native-code)
* [Platforma](#platform)
* [Jazyk](#language)
* [Symbolický reasoning](#symbolic-reasoning)
* [Trasování zásobníku](#incorrect-stack)

### <a name="nondeterminism"></a>Nondeterminism

IntelliTest předpokládá, že se analyzovaných program deterministický. Pokud není, bude IntelliTest cyklus, dokud nebude dosaženo zkoumání vázána.

IntelliTest zvažuje programu, který má být bez determistic, pokud je závislé na vstupních hodnot, které IntelliTest nemůže řídit.

IntelliTest ovládací prvky vstupy poskytované [parametrizovaných testů částí](test-generation.md#parameterized-unit-testing) a získaných z [PexChoose](static-helper-classes.md#pexchoose).
V této smysl výsledky volání nespravovaného nebo uninstrumented kódu za "vstupy" instrumentovaného programu, ale IntelliTest jejich řízení. Pokud řízení toku programu závisí na konkrétní hodnoty pocházející z těchto externích zdrojů, IntelliTest nelze "řídit" program směrem dříve neodkrytých oblasti.

Kromě toho program považován za jiný determistic hodnoty z externích zdrojů změně při znovu spustit program. V takových případech IntelliTest ztratí kontrolu nad spuštění programu a jeho vyhledávání stane neefektivní.

Není někdy zřejmé v takovém případě.
Vezměte v úvahu následující příklady:

* Výsledkem **GetHashCode()** metoda zajišťuje nespravovaného kódu a není předvídatelný.
* **System.Random** třída používá aktuální systémový čas k poskytování skutečně náhodných hodnot.
* **System.DateTime** třída poskytuje aktuální čas, který není pod kontrolou IntelliTest.

### <a name="concurrency"></a>Souběžnost

IntelliTest nezpracovává programy s více vlákny.

### <a name="native-code"></a>Nativní kód

IntelliTest nerozumí nativního kódu, například x86 pokyny zavolaném prostřednictvím **P/Invoke**. Nemůže určit, jak převede těchto volání do omezení, která se dá předat do [Řešitel omezení](input-generation.md#constraint-solver).
I pro kód .NET ho můžete analyzovat pouze kód, který ho instruments. IntelliTest nelze instrumentace na určité části **mscorlib**, včetně knihovně reflexe. **DynamicMethod** nelze instrumentovány.

Navrhovaná alternativní řešení je do mají testovací režim, kde tyto metody jsou umístěny v typy v dynamickém sestavení. Ale i když některé metody jsou uninstrumented, IntelliTest pokusí tak, aby pokrývalo co nejvíc kód instrumentovaného nejblíže.

### <a name="platform"></a>Platforma

IntelliTest je podporována pouze na X86, 32bitová verze. NETframework.

### <a name="language"></a>Jazyk

V zásadě můžete analyzovat IntelliTest libovolný programy .NET, vytvořené v kterémkoli jazyce platformy .NET. V sadě Visual Studio podporuje však pouze C#.

### <a name="symbolic-reasoning"></a>Symbolický reasoning

IntelliTest používá automatické [Řešitel omezení](input-generation.md#constraint-solver) k určení hodnoty, které jsou relevantní pro testovací a program v rámci testu. Dalo solver omezení jsou však a vždy bude, omezené.

### <a name="incorrect-stack-traces"></a>Trasování zásobníku nesprávný

Protože IntelliTest zachytí a "znovu vyvolá" výjimky v každou instrumentovaného metodu, nebudou čísla řádků v trasování zásobníku správné. Jedná se o omezení záměrně pokynu "opětovné".

## <a name="further-reading"></a>Další čtení

* [Úvodní příspěvku na blogu](https://blogs.msdn.microsoft.com/visualstudioalm/2014/11/19/introducing-smart-unit-tests/) na webu MSDN.
* [Generování testů částí pro kód pomocí funkce IntelliTest](../../test/generate-unit-tests-for-your-code-with-intellitest.md)
