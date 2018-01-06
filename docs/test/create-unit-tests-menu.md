---
title: "Vytváření testů jednotek zástupných procedur metoda pomocí příkazu Vytvořit testování částí | Microsoft Docs"
ms.custom: 
ms.date: 05/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: unit testing, create unit tests
ms.assetid: 5D625021-BA96-48A5-9453-3EF6F0943466
caps.latest.revision: "56"
ms.author: douge
manager: douge
ms.workload: multiple
ms.openlocfilehash: c1bd2d883a86a74ee79ced5bf857e3c81c019c5c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="create-unit-test-method-stubs-with-the-create-unit-tests-command"></a>Vytvořte jednotky zástupných procedur metoda test pomocí příkazu Vytvořit testování částí

Visual Studio **vytvořit testování částí** příkaz nabízí možnost vytvářet jednotky zástupných procedur metoda test. Tato funkce umožňuje snadno konfiguraci projekt testu, test třídu a stub metoda testu v něm. 

## <a name="availability-and-extensions"></a>Dostupnost a rozšíření

**Vytvořit testování částí** příkazu v nabídce:

* Je k dispozici v Community, Professional a Enterprise edice nástroje Visual Studio 2015 a novější.

* Podporuje pouze C# kód, který cílí rozhraní .NET Framework.

* Je [extensible](#extend-framework)a podporuje generování testů v Mstestu, Mstestu V2, NUnit, xUnit formátu.

## <a name="get-started"></a>Začínáme

Abyste mohli začít, vyberte v editoru kódu v projektu, které chcete testovat, otevřete místní nabídku a vyberte metodu, typ nebo obor názvů **vytvořit testování částí**. Tím se otevře **vytvořit testování částí** dialogové okno, kde lze vybrat možnosti vytvoření nové testování částí.

![Pomocí příkazu Vytvořit testy jednotek](media/createunittestcommand.png)

## <a name="setting-unit-test-traits"></a>Nastavení vlastnosti testů jednotek

Pokud plánujete spouštět tyto testy je součást automatizace procesu test, můžete zvážit s testovací vytvořené v jiné testovacího projektu (druhá možnost v dialogovém okně výše) a nastavení jednotkové testování vlastnosti pro testování částí. To vám umožní snadno zahrnout nebo vyloučit tyto konkrétní testy v rámci průběžnou integraci nebo průběžné nasazování kanálu. Jsou vlastnosti se nastavují přidáním metadata do testu jednotek přímo, jak je uvedeno níže. 

![Nastavení vlastnosti testů jednotek](media/createunittest.png)

<a name="extend-framework"></a>
## <a name="using-third-party-unit-test-frameworks"></a>Použití systémů testů jednotek třetích stran

Pomocí sady Visual Studio můžete snadno mít testování částí vytvořená pomocí libovolnou architekturu testu. Chcete-li nainstalovat přidat jiných systémů testů, zvolte **nástroje | Rozšíření a aktualizace**.
Rozbalte položku **Online**, **Galerie sady Visual Studio**, **nástroje**a zvolte **testování**. 

![Pomocí rozhraní test třetích stran](media/createunittestfx.png)

Test framework – rozšíření jsou k dispozici ve Visual Studio Marketplace:

* [Rozšíření NUnit pro Test generátory](https://marketplace.visualstudio.com/items?itemName=NUnitDevelopers.TestGeneratorNUnitextension)
* [Rozšíření xUnit.net pro Test generátory](https://marketplace.visualstudio.com/items?itemName=BradWilson.xUnitnetTestExtensions)

## <a name="when-should-i-use-this-feature"></a>Kdy použít tuto funkci?

Tuto funkci použít vždy, když je potřeba vytvářet testy částí, ale konkrétně při testování existující kód s velmi málo nebo žádné pokrytí test a žádná dokumentace. Jinými slovy kde je kód omezenou nebo žádnou specifikaci. Efektivně implementuje podobná přístup [inteligentní testování částí](http://blogs.msdn.com/b/visualstudioalm/archive/2014/11/19/introducing-smart-unit-tests.aspx) který charakterizovat zjištěnou chování kód.

Tato funkce je však rovněž na situaci, kdy vývojář spustí napsáním nějakého kódu a použije ho k bootstrap testování disciplíně částí. V rámci toku kódování vývojář chtít rychle vytvořit jednotku testovací metoda zástupnou proceduru (s třídu vhodné testovací a vhodný testovacího projektu) pro konkrétní kód. 

## <a name="more-information"></a>Další informace

Naleznete v příspěvku blogu [vytváření zástupných procedur metoda testování částí s testování částí"vytvoření"](https://blogs.msdn.microsoft.com/visualstudioalm/2015/03/06/creating-unit-test-method-stubs-with-create-unit-tests/).

Naleznete další jednotky testování příspěvcích na blogu [zde](https://blogs.msdn.microsoft.com/visualstudioalm/tag/unit-testing/).
