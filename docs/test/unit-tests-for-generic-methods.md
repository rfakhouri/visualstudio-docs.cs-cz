---
title: Testování částí pro obecné metody v sadě Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- generics, and unit tests
- unit tests, and generics
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: c4d752b66c65f10d46d57b69acc532d07ea8e2da
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31977280"
---
# <a name="unit-tests-for-generic-methods"></a>Testy jednotek pro obecné metody

Testování částí pro obecné metody můžete vygenerovat přesně tak jako u jiných metod. Následující části obsahují informace a příklady vytváření testy částí pro obecné metody.

## <a name="type-arguments-and-type-constraints"></a>Argumenty typu a omezení typu

Visual Studio vygeneruje-li testování částí pro obecné třídy, jako například `MyList<T>`, vygeneruje dvě metody: Obecné pomocné rutiny a metodu test. Pokud `MyList<T>` má minimálně jeden typ omezení, argument typu musí splňovat všechny typ omezení. Abyste měli jistotu, že obecná kódu v rámci testu funguje podle očekávání pro všechny povolenou vstupy, volá metodu testovací obecné pomocnou metodu s všechna omezení, které chcete testovat.

## <a name="examples"></a>Příklady
 Následující příklady ilustrují testy částí pro obecné typy:

-   [Úpravy generovaného kódu testovací](#EditingGeneratedTestCode). V tomto příkladu má dvě části, vygeneruje testovací kód a upravit testovacího kódu. Ukazuje, jak upravit nezpracovaná testovací kód, který se generují z obecná metoda do metody užitečné testu.

-   [Použití omezení typu](#TypeConstraintNotSatisfied). Tento příklad ukazuje testů jednotek pro obecné metody, která používá typ omezení. V tomto příkladu není splněná omezení typu.

###  <a name="EditingGeneratedTestCode"></a> Příklad 1: Úpravy kódu generovaného testu
 Testovací kód v této části testy kódu v rámci testu metodu s názvem `SizeOfLinkedList()`. Tato metoda vrátí celé číslo, které určuje počet uzlů v odkazovaného seznamu.

 První ukázce kódu, v části generované testovací kód, zobrazuje neupravenou testovací kód, protože byl vygenerován nástrojem Visual Studio Enterprise. Druhý příklad, v části upravovaný testovací kód, ukazuje, jak může způsobit, že testovací fungování metodu SizeOfLinkedList pro dva různé typy dat, `int` a `char`.

 Tento kód ukazuje dva způsoby:

-   Pomocná metoda test, `SizeOfLinkedListTestHelper<T>()`. Ve výchozím nastavení má Pomocná metoda test "TestHelper" v názvu.

-   test metody `SizeOfLinkedListTest()`. Každý test metoda je označena atributem TestMethod.

#### <a name="generated-test-code"></a>Vygenerovaný testovacího kódu
 Následující testovací kód se vygeneroval ze `SizeOfLinkedList()` metoda. Protože je to neupravenou generovaného test, se musí upravit, aby správně test SizeOfLinkedList metody.

```csharp
public void SizeOfLinkedListTestHelper<T>()
{
    T val = default(T); // TODO: Initialize to an appropriate value
    MyLinkedList<T> target = new MyLinkedList<T>(val); // TODO: Initialize to an appropriate value
    int expected = 0; // TODO: Initialize to an appropriate value
    int actual;
    actual = target.SizeOfLinkedList();
    Assert.AreEqual(expected, actual);
    Assert.Inconclusive("Verify the correctness of this test method.");
}

[TestMethod()]
public void SizeOfLinkedListTest()
{
   SizeOfLinkedListTestHelper<GenericParameterHelper>();
}
```

 Předchozí kód je parametr obecného typu `GenericParameterHelper`. Zatímco ho zadat konkrétní datové typy, můžete upravit, jak je znázorněno v následujícím příkladu, můžete spustit test bez úprav tohoto prohlášení.

#### <a name="edited-test-code"></a>Upravit testovacího kódu
 V následujícím kódu, bylo upraveno metoda testů a testovací pomocnou metodu tak, aby byly úspěšně testovacího kódu v rámci testu metoda `SizeOfLinkedList()`.

##### <a name="test-helper-method"></a>Test Pomocná metoda
 Pomocná metoda testovací provede následující kroky, které odpovídají řádky v kódu s názvem bez přípony kroky 1 až 5.

1.  Vytvořte obecný odkazovaného seznamu.

2.  Čtyři uzly připojí k odkazovaného seznamu. Datový typ obsahu tyto uzly neznámý.

3.  Proměnné přiřadit očekávané velikosti odkazovaného seznamu `expected`.

4.  Výpočetní skutečná velikost odkazovaného seznamu a přiřaďte ho k proměnné `actual`.

5.  Porovnání `actual` s `expected` v příkazu Assert. Pokud skutečnou není rovno očekávané, test se nezdaří.

##### <a name="test-method"></a>Test – metoda
 Metoda testovací zkompilován kód, který je volána, když spustíte test s názvem SizeOfLinkedListTest. Provede následující kroky, které odpovídají řádky v kódu s názvem bez přípony kroky 6 a 7.

1.  Zadejte `<int>` při volání testu pomocnou metodu, chcete-li ověřit, že test funguje u `integer` proměnné.

2.  Zadejte `<char>` při volání testu pomocnou metodu, chcete-li ověřit, že test funguje u `char` proměnné.

```csharp
public void SizeOfLinkedListTestHelper<T>()
{
    T val = default(T);
    MyLinkedList<T> target = new MyLinkedList<T>(val); // step 1
    for (int i = 0; i < 4; i++) // step 2
    {
        MyLinkedList<T> newNode = new MyLinkedList<T>(val);
        target.Append(newNode);
    }
    int expected = 5; // step 3
    int actual;
    actual = target.SizeOfLinkedList(); // step 4
    Assert.AreEqual(expected, actual); // step 5
}

[TestMethod()]
public void SizeOfLinkedListTest()
{
    SizeOfLinkedListTestHelper<int>();  // step 6
    SizeOfLinkedListTestHelper<char>(); // step 7
}
```

> [!NOTE]
> Pokaždé, když SizeOfLinkedListTest testovací běhy, jeho TestHelper metoda je volána dvakrát. Příkaz assert musí vyhodnotit na hodnotu true, pokaždé, když pro test předat. Pokud se test nezdaří, nemusí být zrušte zda volání, který uveden `<int>` nebo volání, které zadané `<char>` způsobuje její neočekávané selhání. Pokud chcete najít odpověď, může zkontrolujte zásobníku volání, nebo můžete nastavit zarážky ve své metodě testu a pak ladění při spouštění testu. Další informace najdete v tématu [postupy: ladění během zpracování testu v řešení technologie ASP.NET](http://msdn.microsoft.com/Library/de4d7aa1-4a1e-467e-a19b-4a85ec245b8b).


###  <a name="TypeConstraintNotSatisfied"></a> Příklad 2: Použití omezení typu.
 Tento příklad ukazuje testů jednotek pro obecné metody, která používá typ omezení, která není splněna. První část ukazuje kód z projektu kódu v rámci testu. Omezení typu zvýrazní.

 Druhá část ukazuje kód z testovacího projektu.

#### <a name="code-under-test-project"></a>Kód v části testovacího projektu

```csharp
using System;
using System.Linq;
using System.Collections.Generic;
using System.Text;

namespace ClassLibrary2
{
    public class Employee
    {
        public Employee(string s, int i)
        {
        }
    }

    public class GenericList<T> where T : Employee
    {
        private class Node
        {
            private T data;
            public T Data
            {
                get { return data; }
                set { data = value; }
            }
        }
    }
}
```

#### <a name="test-project"></a>Testovacího projektu

Stejně jako u všechny testy nově vygenerovaný jednotky, je nutné přidat-neprůkazné Assert – příkazy pro tento test jednotky vrátíte užitečných výsledků. Nepřidáte je metoda s atributem TestMethod, ale metodu "TestHelper", který pro tento test se nazývá `DataTestHelper<T>()`.

 V tomto příkladu obecný parametr typu `T` má omezení `where T : Employee`. Toto omezení není splněná v metodě testu. Proto `DataTest()` metoda obsahuje příkazu Assert, která vás upozorní, požadavek na zadat omezení typu, který se nachází na `T`. Zpráva Tento příkaz Assert měl vypadat následovně: `("No appropriate type parameter is found to satisfies the type constraint(s) of T. " + "Please call DataTestHelper<T>() with appropriate type parameters.");`

 Jinými slovy, při volání `DataTestHelper<T>()` metoda z metody test `DataTest()`, je nutné předat parametr typu `Employee` nebo třídy odvozené od `Employee`.

 `using ClassLibrary2;`

 `using Microsoft.VisualStudio.TestTools.UnitTesting;`

 `namespace TestProject1`

```csharp
{
    [TestClass()]
    public class GenericList_NodeTest
    {

        public void DataTestHelper<T>()
            where T : Employee
        {
            GenericList_Shadow<T>.Node target = new GenericList_Shadow<T>.Node(); // TODO: Initialize to an appropriate value
            T expected = default(T); // TODO: Initialize to an appropriate value
            T actual;
            target.Data = expected;
            actual = target.Data;
            Assert.AreEqual(expected, actual);
            Assert.Inconclusive("Verify the correctness of this test method.");
        }

        [TestMethod()]
        public void DataTest()
        {
            Assert.Inconclusive("No appropriate type parameter is found to satisfies the type constraint(s) of T. " +
            "Please call DataTestHelper<T>() with appropriate type parameters.");
        }
    }
}
```

## <a name="see-also"></a>Viz také

- [Testování částí kódu](../test/unit-test-your-code.md)
