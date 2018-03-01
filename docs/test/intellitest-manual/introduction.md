---
title: "Přehled | Nástroj pro testování Microsoft IntelliTest Developer | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IntelliTest, Visual Studio IntelliTest developer testing tool
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 65f14d96bd495a1b3f8ca138176fbf805fdfeb67
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="overview-of-microsoft-intellitest"></a>Přehled Microsoft IntelliTest

IntelliTest umožňuje najít chyby časná a snižuje náklady na údržbu test. Automatizovaná a transparentní testování přístup IntelliTest můžete vygenerovat candidate sada testů kódu .NET. Testovací sady generování můžete provést další podle *správnost vlastnosti* zadáte. IntelliTest bude i momentální testovací sady automaticky jako zpracovaní testovaného kódu.

**Charakteristiku testů**  
IntelliTest umožňuje určit chování kódu z hlediska sada testů tradiční jednotek. Testovací sady můžete použít jako sada regrese, které tvoří základ k boji složitost spojené s refaktoring starší verze nebo neznámého kódu.

**Vstupní generování s průvodcem testu**  
IntelliTest používá otevřete kód analýzu a testování omezení řešení přístupu k automatickému generování přesné vstupní hodnoty; obvykle bez nutnosti zásahu uživatele. Pro komplexní typy objektů automaticky vygeneruje objekty pro vytváření. Vstupní generování testů můžete Průvodce rozšířením a konfiguraci objektů Factory podle svých potřeb. Vlastnosti správnost zadané jako kontrolní výrazy ve kódu se taky použije automaticky k další průvodci testovací vstupní generace.

**Integrace rozhraní IDE**  
IntelliTest plně integrován do prostředí Visual Studio IDE. Všechny informace shromážděné během generování testovací sada (například automaticky generované vstup výstupu z vašeho kódu, vygenerovaný testovací případy a jejich průchodu nebo neúspěch stav) se zobrazí v prostředí Visual Studio IDE. Můžete snadno iterovat mezi oprava kódu a opětovné spuštění IntelliTest, aniž byste museli opustit Visual Studio IDE. Testy můžete uložit do řešení jako projektu testování částí a bude automaticky zjištěn později pomocí Průzkumníka testů Visual Studio.

**Doplnit existující testování postupy**  
Pomocí IntelliTest doplňují všechny existující testování postupy, které je může provést.

Pokud chcete testovat:

* Algoritmy přes primitivní datové nebo pole jednoduchých dat:
  * zápis [parametrizovaných testů jednotek](test-generation.md#parameterized-unit-testing)
* Algoritmy přes komplexní data, jako třeba kompilátoru:
  * umožní IntelliTest nejprve vygenerovat reprezentaci abstraktní dat a informační kanál algoritmus
  * umožní IntelliTest sestavení instancí pomocí [vytvoření vlastního objektu](input-generation.md#objects) a výstupních dat podmínek a pak vyvolejte algoritmus
* Kontejnery dat:
  * zápis [parametrizovaných testů jednotek](test-generation.md#parameterized-unit-testing)
  * umožní IntelliTest sestavení instancí pomocí [vytvoření vlastního objektu](input-generation.md#objects) a výstupních dat podmínek a poté vyvolá metoda výstupních podmínek kontejneru a znovu zkontrolujte později
  * zápis [parametrizovaných testů částí](test-generation.md#parameterized-unit-testing) volání různé metody provedení, v závislosti na hodnoty parametru
* Existujícího základu kódu:
  * pomocí sady Visual Studio IntelliTest Průvodce Začínáme vygenerováním sadu [parametrizovaných testů částí (PUT)](test-generation.md#parameterized-unit-testing)

<a name="hello-world"></a>
## <a name="the-hello-world-of-intellitest"></a>Hello World z IntelliTest

IntelliTest vyhledá vstupy relevantní pro otestované programu, což znamená, můžete ho použít ke generování famous **Hello, World!** Řetězec. Předpokladem je, že jste vytvořili na základě jazyka C# Mstestu testovacího projektu a přidat odkaz na **Microsoft.Pex.Framework**. Pokud používáte jiný testovací framework, vytvoření knihovny tříd jazyka C# a test framework dokumentaci o tom, jak nastavit projekt.

Následující příklad vytvoří dvě omezení na parametr s názvem **hodnota** tak, aby IntelliTest vygeneruje požadovaný řetězec.

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

Jakmile zkompilovat a provést, generuje IntelliTest sadu testů například následující:

1. ""
2. "\0\0\0\0\0"
3. Text "hello"
4. "\0\0\0\0\0\0"
5. "Hello\0"
6. "Hello\0\0"
7. "Hello\0World!"
8. "Hello, World!"

Čtení [generování testů částí s Intellitest](../../test/generate-unit-tests-for-your-code-with-intellitest.md) pochopit uložení generovaného testy. Vygenerovaný testovacího kódu by měla obsahovat testu například následující:

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

<a name="nondeterminism"></a>
### <a name="nondeterminism"></a>Nondeterminism

IntelliTest předpokládá, že se analyzovaných program deterministický. Pokud není, bude IntelliTest cyklus, dokud nebude dosaženo zkoumání vázána.

IntelliTest zvažuje programu, který má být bez determistic, pokud je závislé na vstupních hodnot, které IntelliTest nemůže řídit.

IntelliTest ovládací prvky vstupy poskytované [parametrizovaných testů částí](test-generation.md#parameterized-unit-testing) a získaných z [PexChoose](static-helper-classes.md#pexchoose). V této smysl výsledky volání nespravovaného nebo uninstrumented kódu za "vstupy" instrumentovaného programu, ale IntelliTest jejich řízení. Pokud řízení toku programu závisí na konkrétní hodnoty pocházející z těchto externích zdrojů, IntelliTest nelze "řídit" program směrem dříve neodkrytých oblasti. 

Kromě toho program považován za jiný determistic hodnoty z externích zdrojů změně při opětovné spuštění programu. V takových případech IntelliTest ztratí kontrolu nad spuštění programu a jeho vyhledávání se bude velmi neefektivní.

Není někdy zřejmé v takovém případě. Vezměte v úvahu následující příklady:

* Výsledkem **GetHashCode()** metoda zajišťuje nespravovaného kódu a není předvídatelný.
* **System.Random** třída používá aktuální systémový čas k poskytování skutečně náhodných hodnot.
* **System.DateTime** třída poskytuje aktuální čas, který není samozřejmě pod kontrolou IntelliTest.

<a name="concurrency"></a>
### <a name="concurrency"></a>Souběžnost

IntelliTest nezpracovává programy s více vlákny.

<a name="native-code"></a>
### <a name="native-code-net-code-that-is-not-instrumented"></a>Nativní kód, .NET kód, který není instrumentována

IntelliTest nerozumí nativního kódu, například x86 pokyny zavolaném prostřednictvím **P/Invoke**. Nemůže určit, jak převede těchto volání do omezení, která se dá předat do [Řešitel omezení](input-generation.md#constraint-solver). I pro kód .NET se analyzují pouze kód, který ho instruments. IntelliTest nelze instrumentace na určité části **mscorlib**, včetně knihovně reflexe. **DynamicMethod** nelze instrumentovány. 

Navrhovaná alternativní řešení je do mají testovací režim, kde tyto metody jsou umístěny v typy v dynamickém sestavení. Ale i když některé metody jsou uninstrumented, IntelliTest pokusí tak, aby pokrývalo co nejvíc kód instrumentovaného nejblíže.

<a name="platform"></a>
### <a name="platform"></a>Platforma

IntelliTest je podporována pouze na X86, 32bitová verze. NETframework.

<a name="language"></a>
### <a name="language"></a>Jazyk

V zásadě můžete analyzovat IntelliTest libovolný programy .NET, vytvořené v kterémkoli jazyce platformy .NET. V sadě Visual Studio podporuje však pouze C#.

<a name="symbolic-reasoning"></a>
### <a name="symbolic-reasoning"></a>Symbolický reasoning

IntelliTest používá automatické [Řešitel omezení](input-generation.md#constraint-solver) k určení hodnoty, které jsou relevantní pro testovací a program v rámci testu. Dalo solver omezení jsou však a vždy bude, omezené.

<a name="incorrect-stack"></a>
### <a name="slightly-incorrect-stack-traces"></a>Trasování zásobníku (mírně) nesprávný

Protože IntelliTest zachytí a "znovu vyvolá" výjimky v každou instrumentovaného metodu, nebudou čísla řádků v trasování zásobníku správné. Jedná se o omezení záměrně pokynu "opětovné".

<a name="further-reading"></a>
## <a name="further-reading"></a>Další čtení

* [Úvodní příspěvku na blogu](https://blogs.msdn.microsoft.com/visualstudioalm/2014/11/19/introducing-smart-unit-tests/) na webu MSDN.
* [Generování testů částí pro kód pomocí funkce IntelliTest](../../test/generate-unit-tests-for-your-code-with-intellitest.md)

## <a name="got-feedback"></a>Zpětné vazby máte?

Vystavení vašich nápadů a funkce požadavky na  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
