---
title: "Vytvoření testu jednotky zástupných procedur metoda v sadě Visual Studio | Microsoft Docs"
ms.date: 05/02/2017
ms.technology: vs-ide-test
ms.topic: article
helpviewer_keywords:
- unit testing, create unit tests
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 1620612bc27c41fcebfcc28b2844b3022fa482fa
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="create-unit-test-method-stubs-with-the-create-unit-tests-command"></a>Vytvořte jednotky zástupných procedur metoda test pomocí příkazu Vytvořit testování částí

Visual Studio **vytvořit testování částí** příkaz nabízí možnost vytvářet jednotky zástupných procedur metoda test. Tato funkce umožňuje snadno konfiguraci projekt testu, test třídu a stub metoda testu v něm.

## <a name="availability-and-extensions"></a>Dostupnost a rozšíření

**Vytvořit testování částí** příkazu v nabídce:

* Je k dispozici v Community, Professional a Enterprise edice nástroje Visual Studio 2015 a novější.

* Podporuje pouze C# kód, který cílí rozhraní .NET Framework.

* Rozšiřitelný a podporuje generování testů v Mstestu, Mstestu V2, NUnit, xUnit formátu.

## <a name="get-started"></a>Začínáme

Abyste mohli začít, vyberte v editoru kódu v projektu, které chcete testovat, otevřete místní nabídku a vyberte metodu, typ nebo obor názvů **vytvořit testování částí**. Tím se otevře **vytvořit testování částí** dialogové okno, kde lze vybrat možnosti vytvoření nové testování částí.

![Pomocí příkazu Vytvořit testy jednotek](media/createunittestcommand.png)

## <a name="setting-unit-test-traits"></a>Nastavení vlastnosti testů jednotek

Pokud plánujete spouštět tyto testy je součást automatizace procesu test, můžete zvážit s testovací vytvořené v jiné testovacího projektu (druhá možnost v dialogovém okně výše) a nastavení jednotkové testování vlastnosti pro testování částí. To vám umožní snadno zahrnout nebo vyloučit tyto konkrétní testy v rámci průběžnou integraci nebo průběžné nasazování kanálu. Jsou vlastnosti se nastavují přidáním metadata do testu jednotek přímo, jak je uvedeno níže.

![Nastavení vlastnosti testů jednotek](media/createunittest.png)

## <a name="using-third-party-unit-test-frameworks"></a>Použití systémů testů jednotek třetích stran

Pomocí sady Visual Studio můžete snadno mít testování částí vytvořená pomocí libovolnou architekturu testu. K instalaci jiných systémů testů:

1. Zvolte **nástroje** > **rozšíření a aktualizace**.
2. Rozbalte položku **Online** > **Visual Studio Marketplace** > **nástroje**a potom zvolte **testování**.

![Pomocí rozhraní test třetích stran](media/createunittestfx.png)

Test framework – rozšíření jsou k dispozici ve Visual Studio Marketplace:

* [Rozšíření NUnit pro Test generátory](https://marketplace.visualstudio.com/items?itemName=NUnitDevelopers.TestGeneratorNUnitextension)
* [Rozšíření xUnit.net pro Test generátory](https://marketplace.visualstudio.com/items?itemName=BradWilson.xUnitnetTestExtensions)

## <a name="when-should-i-use-this-feature"></a>Kdy použít tuto funkci?

Tuto funkci použít vždy, když je potřeba vytvářet testy částí, ale konkrétně při testování existující kód s velmi málo nebo žádné pokrytí test a žádná dokumentace. Jinými slovy kde je kód omezenou nebo žádnou specifikaci. Efektivně implementuje podobná přístup [inteligentní testování částí](http://blogs.msdn.com/b/visualstudioalm/archive/2014/11/19/introducing-smart-unit-tests.aspx) který charakterizovat zjištěnou chování kód.

Tato funkce je však rovněž na situaci, kdy vývojář spustí napsáním nějakého kódu a použije ho k bootstrap testování disciplíně částí. V rámci toku kódování vývojář chtít rychle vytvořit jednotku testovací metoda zástupnou proceduru (s třídu vhodné testovací a vhodný testovacího projektu) pro konkrétní kód.

## <a name="see-also"></a>Viz také

- [Vytváření testů jednotek zástupných procedur metoda s testování částí"vytvoření"](https://blogs.msdn.microsoft.com/visualstudioalm/2015/03/06/creating-unit-test-method-stubs-with-create-unit-tests/)
- [Příspěvky blogu testování částí](https://blogs.msdn.microsoft.com/devops/?s=unit+testing)
