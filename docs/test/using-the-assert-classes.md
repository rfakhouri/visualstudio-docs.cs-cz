---
title: "Používání tříd Assert pro testování v sadě Visual Studio částí | Microsoft Docs"
ms.date: 11/04/2016
ms.technology: vs-ide-test
ms.topic: article
helpviewer_keywords:
- Assert classes
- Assert statements
- unit tests, Assert statements
- unit tests, Assert classes
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: d9c6e2b62a32771b02c3244984eb8a59e2513635
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="use-the-assert-classes"></a>Používání tříd Assert

Pomocí tříd Assert oboru názvů UnitTestingFramework ověřte specifické funkce. Metoda testování částí uplatňuje kód metody ve vašem kódu vývoj, ale sestavy správnost kódu na chování, pouze pokud zahrnete Assert – příkazy.

## <a name="kinds-of-asserts"></a>Typy z vyhodnotí
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting> Obor názvů obsahuje několik druhů tříd Assert:

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>

 V testu metodu můžete volat libovolný počet metody Assert třídy, jako je například Assert.AreEqual(). Assert – třída má mnoho způsobů vybírat a mnoho z těchto metod má několik přetížení.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CollectionAssert>

 Použití třídy CollectionAssert porovnávání kolekcí objektů a můžete ověřit stav jednoho nebo více kolekcí.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert>

 Třída StringAssert slouží k porovnání řetězců. Tato třída obsahuje celou řadu užitečných metod například StringAssert.Contains, StringAssert.Matches a StringAssert.StartsWith.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertFailedException>

 Vždy, když test se nezdaří, je vyvolána výjimka AssertFailedException. Test nezdaří, pokud vyprší časový limit, neočekávanou výjimku nebo obsahuje příkazu Assert, který vytvoří výsledek se nezdařilo.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertInconclusiveException>

 AssertInconclusiveException je vyvolána při každém testu vytvoří výsledek Inconclusive. Obvykle přidejte příkaz Assert.Inconclusive do testu, stále můžete pracujete se indikovat, že ještě není připraven ke spuštění.

> [!NOTE]
>  Alternativní strategie by k označení test, který není připraven ke spuštění s atributem ignorovat. To má však nevýhodou, že nelze snadno vygenerovat sestavu na počet testů, že jste opustili k implementaci.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.UnitTestAssertException>

 Pokud napíšete novou třídu výjimka Assert, s třídy dědí ze základní třídy UnitTestAssertException je snazší identifikaci výjimky jako chybu assertion místo k neočekávané výjimce v testovacím nebo produkční kódu.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute>

 Test metody s atributem ExpectedExceptionAttribute uspořádání, pokud chcete testovací metodu za účelem ověření, že výjimku, které chcete-li být vyvolána metoda ve vašem kódu vývoj je skutečně hlášeny v dané metody.

## <a name="see-also"></a>Viz také

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting>
- [Testování částí kódu](../test/unit-test-your-code.md)
