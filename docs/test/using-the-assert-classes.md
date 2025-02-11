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
ms.openlocfilehash: d145734dc89faafcedbca6730f0a90da174376c4
ms.sourcegitcommit: 51dad3e11d7580567673e0d426ab3b0a17584319
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/10/2019
ms.locfileid: "66820321"
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

Chcete-li ověřit, že je vyvolána výjimka očekáváte, která je vyvolána metoda v kódu aplikace, použijte <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.ThrowsException%2A?displayProperty=nameWithType> metody.

## <a name="see-also"></a>Viz také:

- [Testování částí kódu](../test/unit-test-your-code.md)