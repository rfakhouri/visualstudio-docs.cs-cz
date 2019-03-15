---
title: Vytvoření zástupné procedury metodu testu jednotek
ms.date: 05/02/2017
ms.topic: conceptual
helpviewer_keywords:
- unit testing, create unit tests
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e8ddc4e7a44aa0d5d42a64556092874413e3a3b2
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2019
ms.locfileid: "57982763"
---
# <a name="create-unit-test-method-stubs-with-the-create-unit-tests-command"></a>Metoda zástupné procedury s příkaz Vytvořit testy jednotek pro testování částí Create

Visual Studio **vytvořit testy jednotek** příkaz poskytuje možnost vytvořit jednotku zástupné procedury testovací metody. Tato funkce umožňuje snadno konfigurace testovacího projektu, testovací třídy a pahýl metody testu v rámci něj.

## <a name="availability-and-extensions"></a>Dostupnost a rozšíření

**Vytvořit testy jednotek** příkazu nabídky:

* Je k dispozici v Community, Professional a Enterprise edice sady Visual Studio 2015 a novější.

* Podporuje pouze kód jazyka C#, který cílí na .NET Framework.

* Je možné rozšířit a podporuje generování testů MSTest, nástroji MSTest V2, NUnit, xUnit formátu.

* Ještě není k dispozici v projektech .NET Core.

## <a name="get-started"></a>Začínáme

Abyste mohli začít, vyberte metodu, typ nebo obor názvů v editoru kódu v projektu, kterou chcete testovat, otevřete místní nabídku a zvolte **vytvořit testy jednotek**. **Vytvořit testy jednotek** otevře se dialogové okno, které je možné vybrat možnosti vytvoření nové jednotkové testy.

![Pomocí příkazu Vytvořit testy jednotek](media/createunittestcommand.png)

## <a name="set-unit-test-traits"></a>Nastavení vlastností testu jednotek

Pokud budete chtít spustit tyto testy jako součást procesu automatizace testů, můžete zvážit s testů vytvořené v jiném projektu testu (druhá možnost v dialogovém okně výše) a vlastnosti pro test jednotek pro testování částí nastavení. To umožňuje snadněji zahrňte nebo vylučte tyto specifické testy jako součást průběžné integrace nebo průběžného nasazování kanálu. Rysy jsou nastavené tak, že přidáte metadat pro testování částí přímo, jak je znázorněno níže.

![Nastavení vlastností testu jednotek](media/createunittest.png)

## <a name="use-third-party-unit-test-frameworks"></a>Použití rozhraní pro testování jednotky třetí strany

Pomocí sady Visual Studio můžete snadno mít vytvořené pomocí libovolné rozhraní testování částí. Chcete-li nainstalovat další rozhraní pro testování:

::: moniker range="vs-2017"

1. Zvolte **nástroje** > **rozšíření a aktualizace**.

::: moniker-end

::: moniker range=">=vs-2019"

1. Zvolte **rozšíření** > **spravovat rozšíření**.

::: moniker-end

2. Rozbalte **Online** > **Visual Studio Marketplace** > **nástroje**a klikněte na tlačítko **testování**.

![Pomocí rozhraní pro testování třetích stran](media/createunittestfx.png)

Testovací rozhraní framework rozšíření jsou k dispozici v aplikaci Visual Studio Marketplace:

* [NUnit rozšíření pro generátory testu](https://marketplace.visualstudio.com/items?itemName=NUnitDevelopers.TestGeneratorNUnitextension)
* [rozšíření xUnit.net pro generátory testu](https://marketplace.visualstudio.com/items?itemName=BradWilson.xUnitnetTestExtensions)

## <a name="when-should-i-use-this-feature"></a>Kdy použít tuto funkci?

Tuto funkci použít vždy, když je potřeba vytvořit testy jednotek, ale specificky při testování existující kód, který má žádné nebo téměř žádné pokrytí testu a žádná dokumentace. Jinými slovy ve kterých je specifikace omezené nebo neexistující kódu. Efektivně implementuje podobný přístup [inteligentní testování částí](https://devblogs.microsoft.com/devops/introducing-smart-unit-tests/) , které charakterizují zjištěnou chování kódu.

Tato funkce je však vztahuje rovněž na situaci, kdy vývojář spustí napsáním nějakého kódu a, který používá ke spuštění testování disciplíny. Ve službě flow kódování může být vhodné Vývojář můžete rychle vytvořit jednotku testovací metoda zástupnou proceduru (s vhodné testovací třídy a vhodný testovacího projektu) pro konkrétní část kódu.

## <a name="see-also"></a>Viz také:

- [Vytvoření testu jednotek metoda zástupné procedury s "Vytvoření Unit Tests"](https://devblogs.microsoft.com/devops/creating-unit-test-method-stubs-with-create-unit-tests/)
- [Testování blogové příspěvky](https://devblogs.microsoft.com/devops/?s=unit+testing)
