---
title: "Glosář pro atribut | Nástroj pro testování Microsoft IntelliTest Developer | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: IntelliTest, Attribute glossary
ms.assetid: 557C7869-48BE-4B82-9563-1FF356ABACDB
caps.latest.revision: "56"
ms.author: douge
manager: douge
ms.openlocfilehash: 71f8adb78c594b6558d570bf79b7535a7517ddbe
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="attribute-glossary"></a>Atribut Glosář

## <a name="attributes-by-namespace"></a>Atributy podle oboru názvů

* **Microsoft.Pex.Framework**
  * [PexAssumeNotNull](#pexassumenotnull)
  * [PexClass](#pexclass)
  * [PexGenericArguments](#pexgenericarguments)
  * [PexMethod](#pexmethod)
     - [PexExplorationAttributeBase](#pexexplorationattributebase)<p />

* **Microsoft.Pex.Framework.Settings**
  * [PexAssemblySettings](#pexassemblysettings)<p />

* **Microsoft.Pex.Framework.Instrumentation**
  * [PexAssemblyUnderTest](#pexassemblyundertest)
  * [PexInstrumentAssembly](#pexinstrumentassemblyattribute)<p />

* **Microsoft.Pex.Framework.Using**
  * [PexUseType](#pexusetype)<p />

* **Microsoft.Pex.Framework.Validation**
  * [PexAllowedException](#pexallowedexception)
  * [PexAllowedExceptionFromAssembly](#pexallowedexceptionfromassembly)
  * [PexAllowedExceptionFromType](#pexallowedexceptionfromtype)
  * [PexAllowedExceptionFromTypeUnderTest](#pexallowedexceptionfromtypeundertest)

<a name="pexassumenotnull"></a>
## <a name="pexassumenotnull"></a>PexAssumeNotNull

Tento atribut vyhodnotí, že upraveny hodnota nemůže být **null**. Je možné připojit k:

* **parametr** metody parametrizované testu

  ```
  // assume foo is not null
  [PexMethod]
  public void SomeTest([PexAssumeNotNull]IFoo foo, ...) {}
  ```

* **pole**

  ```
  public class Foo {
     // this field should not be null
     [PexAssumeNotNull]
     public object Bar;
  }
  ```

* **typu**

  ```
  // never consider null for Foo types
  [PexAssumeNotNull]
  public class Foo {}
  ```

Také se lze připojit k sestavení test, zkušebního přípravku nebo testovací metoda; v takovém případě musí označovat první argumenty, které pole nebo typ předpokladů použít. Atribut se vztahuje na typ, platí pro všechna pole s tímto typem formální.

<a name="pexclass"></a>
## <a name="pexclass"></a>PexClass

Tento atribut označuje třídu, která obsahuje *explorations*. Jedná se o ekvivalent Mstestu **TestClassAttribute** (nebo NUnit **TestFixtureAttribute**). Tento atribut je volitelné.

Třídy označené jako [PexClass](#pexclass) musí být *výchozí zkonstruovatelný*:

* veřejně exportovaný typu
* výchozí konstruktor
* není abstraktní.

Pokud třída těchto požadavků nesplňuje, zobrazí se chybová zpráva a průzkum nezdaří.

Chcete-li tyto třídy také důrazně doporučujeme **částečné** tak, aby IntelliTest může generovat nové testy, které jsou součástí třídy, ale v samostatném souboru. Tento přístup řeší mnohé problémy, kvůli [viditelnost](input-generation.md#visibility) a je typické technika v jazyce C#.

**Další sada a kategorie**:

```
[TestClass] // MSTest test fixture attribute
[PexClass(Suite = "checkin")] // fixture attribute
public partial class MyTests { ... }
```

**Určení typu testovaného**:

```
[PexClass(typeof(Foo))] // this is a test for Foo
public partial class FooTest { ... }
```

Třída může obsahovat metody opatřen poznámkou [PexMethod](#pexmethod). Také rozumí IntelliTest [nastavit a přerušit metody](test-generation.md#setup-teardown).

<a name="pexgenericarguments"></a>
## <a name="pexgenericarguments"></a>PexGenericArguments

Tento atribut obsahuje typ řazené kolekce členů pro vytváření instancí [testování částí obecný parametrizované](test-generation.md#generic-parameterized).

<a name="pexmethod"></a>
## <a name="pexmethod"></a>PexMethod

Tento atribut určí metodu jako [testování částí parametrizované](test-generation.md#parameterized-unit-testing).
Metoda se musí nacházet v rámci třídy označené jako [PexClass](#pexclass) atribut.

IntelliTest vygeneruje testy tradiční, bez parametrů, které volání [testování částí parametrizované](test-generation.md#parameterized-unit-testing) s odlišnými parametry.

Testování parametrizované částí:

* musí být metoda instance
* musí být [viditelné](input-generation.md#visibility) testovací třídy, do kterého se umístí generovaného testy podle [vodopádu nastavení](settings-waterfall.md)
* může trvat libovolný počet parametrů
* může být obecný

**Příklad**

```
[PexClass]
public partial class MyTests {
     [PexMethod]
     public void MyTest(int i)
     { ... }
}
```

<a name="pexexplorationattributebase"></a>
## <a name="pexexplorationattributebase"></a>PexExplorationAttributeBase

[Další informace](https://msdn.microsoft.com/library/microsoft.pex.framework.pexexplorationattributebase.aspx)

<a name="pexassemblysettings"></a>
## <a name="pexassemblysettings"></a>PexAssemblySettings

Tento atribut lze nastavit na úrovni sestavení přepsat výchozí hodnoty nastavení pro všechny explorations.

```
using Microsoft.Pex.Framework;
// overriding the test framework selection
[assembly: PexAssemblySettings(TestFramework = "Naked")]
```

<a name="pexassemblyundertest"></a>
## <a name="pexassemblyundertest"></a>PexAssemblyUnderTest

Tento atribut určuje sestavení, která se testuje v aktuálním projektu testu. 

```
[assembly: PexAssemblyUnderTest("MyAssembly")]
```

<a name="pexinstrumentassemblyattribute"></a>
## <a name="pexinstrumentassemblyattribute"></a>PexInstrumentAssemblyAttribute

Tento atribut slouží k zadání sestavení, které chcete instrumentovány.

**Příklad**

```
using Microsoft.Pex.Framework;

// the assembly containing ATypeFromTheAssemblyToInstrument should be instrumented
[assembly: PexInstrumentAssembly(typeof(ATypeFromTheAssemblyToInstrument))]

// the assembly name can be used as well
[assembly: PexInstrumentAssembly("MyAssemblyName")]
```

<a name="pexusetype"></a>
## <a name="pexusetype"></a>PexUseType

Tento atribut informuje IntelliTest, že konkrétní typ může použít k vytváření instancí rozhraní nebo základní typy (abstract).

**Příklad**

```
[PexMethod]
[PexUseType(typeof(A))]
[PexUseType(typeof(B))]
public void MyTest(object testParameter)
{
     ... // IntelliTest will consider types A and B to instantiate 'testParameter'
}
```

<a name="pexallowedexception"></a>
## <a name="pexallowedexception"></a>PexAllowedException

Pokud tento atribut je připojena k [PexMethod](#pexmethod) (nebo [PexClass](#pexclass), změní výchozí IntelliTest logiku, která určuje, kdy testů selže. Test se nepovažuje jako neúspěšný i v případě, že nastane zadanou výjimkou.

**Příklad**

Následující test Určuje, že konstruktoru **zásobníku** může vyvolat **výjimka ArgumentOutOfRangeException**:

```
class Stack {
  int[] _elements;
  int _count;
  public Stack(int capacity) {
    if (capacity<0) throw new ArgumentOutOfRangeException();
    _elements = new int[capacity];
    _count = 0;
  }
  ...
}
```

Filtr je připojen k z přípravku následujícím způsobem (ho lze také definovat na úrovni sestavení nebo testovací):

```
[PexMethod]
[PexAllowedException(typeof(ArgumentOutOfRangeException))]
class CtorTest(int capacity) {
  Stack s = new Stack(capacity); // may throw ArgumentOutOfRangeException
}
```

<a name="pexallowedexceptionfromassembly"></a>
## <a name="pexallowedexceptionfromassembly"></a>PexAllowedExceptionFromAssembly

[Další informace](https://msdn.microsoft.com/library/microsoft.pex.framework.validation.pexallowedexceptionfromassemblyattribute.aspx)

<a name="pexallowedexceptionfromtype"></a>
## <a name="pexallowedexceptionfromtype"></a>PexAllowedExceptionFromType

[Další informace](https://msdn.microsoft.com/library/microsoft.pex.framework.validation.pexallowedexceptionfromtypeattribute.aspx)

<a name="pexallowedexceptionfromtypeundertest"></a>
## <a name="pexallowedexceptionfromtypeundertest"></a>PexAllowedExceptionFromTypeUnderTest

[Další informace](https://msdn.microsoft.com/library/microsoft.pex.framework.validation.pexallowedexceptionfromtypeundertestattribute.aspx)

## <a name="got-feedback"></a>Zpětné vazby máte?

Vystavení vašich nápadů a funkce požadavky na  **[UserVoice](https://visualstudio.uservoice.com/forums/121579-visual-studio-2015/category/157869-test-tools?query=IntelliTest)**.
