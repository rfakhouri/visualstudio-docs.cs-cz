---
title: MSTest assert třídy a metody
ms.date: 06/07/2018
ms.topic: reference
helpviewer_keywords:
- Assert classes
- Assert methods
- unit tests, Assert classes
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: d9d02ee375a5b9e6069a94cd7b534b871792088a
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62962005"
---
# <a name="use-assert-classes-for-unit-testing"></a>Používání tříd Assert pro testování částí

Používání tříd Assert z <xref:Microsoft.VisualStudio.TestTools.UnitTesting> obor názvů pro ověření konkrétní funkce. Metodu testovací jednotky uplatňuje kód metody v kódu vaší aplikace, ale pouze v případě, že zahrnete příkazů Assert oznámí správnosti kódu chování.

## <a name="kinds-of-asserts"></a>Typy z nepodmíněné výrazy

<xref:Microsoft.VisualStudio.TestTools.UnitTesting> Obor názvů obsahuje několik typů tříd Assert.

V testovací metodě, můžete volat všechny metody <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert?displayProperty=fullName> třídy, jako například <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A?displayProperty=nameWithType>. <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> Třída má vybírat z mnoha způsobů a řada z metod má několik přetížení.

### <a name="compare-strings-and-collections"></a>Porovnání řetězců a kolekce

Použití <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CollectionAssert> třídy porovnávání kolekcí objektů nebo ověřit stav kolekce.

Použití <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert> třídy můžete porovnat a prozkoumejte řetězce. Tato třída obsahuje celou řadu užitečných metod, jako například <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert.Contains%2A?displayProperty=nameWithType>, <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert.Matches%2A?displayProperty=nameWithType>, a <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert.StartsWith%2A?displayProperty=nameWithType>.

### <a name="exceptions"></a>Výjimky

<xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertFailedException> Pokaždé, když se test nezdaří, je vyvolána výjimka. Test se nezdaří, pokud vyprší časový limit, dojde k neočekávané výjimce nebo obsahuje kontrolní příkaz, který vytváří **neúspěšné** výsledek.

<xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertInconclusiveException> Je vyvolána pokaždé, když se test vytvoří výsledek **neprůkazné**. Obvykle přidáte <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.Inconclusive%2A?displayProperty=nameWithType> test, který se stále pracujete, k označení ještě není připraven ke spuštění příkazu.

> [!NOTE]
> Alternativní strategií je označit test, který není připraven ke spuštění s <xref:Microsoft.VisualStudio.TestTools.UnitTesting.IgnoreAttribute> atribut. Má to ale nevýhodou, že nelze snadno vygenerujete sestavu pro počet testů, které nejsou implementovány.

Pokud píšete nový, Assert – třída výjimky dědit ze základní třídy <xref:Microsoft.VisualStudio.TestTools.UnitTesting.UnitTestAssertException> pro snazší identifikaci výjimku jako selhání kontrolního výrazu místo Neočekávaná výjimka vyvolána v testovacím nebo produkčním kódu.

Uspořádání testovací metodu s <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute> atribut, pokud chcete testovací metodu za účelem ověření, že je vyvolána výjimka očekáváte, která je vyvolána metoda v kódu aplikace.

## <a name="see-also"></a>Viz také:

- [Testování částí kódu](../test/unit-test-your-code.md)