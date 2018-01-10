---
title: "Používání tříd Assert | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Assert classes
- Assert statements
- unit tests, Assert statements
- unit tests, Assert classes
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: f2d0e0020ae26a3a2331643f74f436441612b9fc
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="using-the-assert-classes"></a>Používání tříd Assert
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
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting>   
 [Vytváření a spouštění testování částí pro existujícího kódu](http://msdn.microsoft.com/en-us/e8370b93-085b-41c9-8dec-655bd886f173)
