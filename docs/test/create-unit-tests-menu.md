---
title: Vytvoření zástupné procedury metodu testu jednotek
ms.date: 04/01/2019
ms.topic: conceptual
helpviewer_keywords:
- unit testing, create unit tests
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e7eb72f104560991f1bb191e62641041879df071
ms.sourcegitcommit: 509fc3a324b7748f96a072d0023572f8a645bffc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/02/2019
ms.locfileid: "58857720"
---
# <a name="create-unit-test-method-stubs-with-the-create-unit-tests-command"></a>Metoda zástupné procedury s příkaz Vytvořit testy jednotek pro testování částí Create

**Vytvořit testy jednotek** příkaz vytvoří jednotku zástupné procedury testovací metody. Tato funkce umožňuje snadno konfigurace testovacího projektu, testovací třídy a pahýl metody testu v rámci něj.

> [!NOTE]
> **Vytvořit testy jednotek** příkazu nabídky je dostupná pouze pro spravovaný kód, který cílí na rozhraní .NET Framework (ale ne .NET Core).

**Vytvořit testy jednotek** příkazu nabídky je možné rozšířit a může sloužit ke generování testů pro MSTest, nástroji MSTest V2, xUnit a NUnit.

## <a name="get-started"></a>Začínáme

Chcete-li začít, vyberte metodu, typ nebo obor názvů v editoru kódu v projektu, které chcete testovat, klikněte pravým tlačítkem a pak zvolte **vytvořit testy jednotek**. **Vytvořit testy jednotek** otevře dialogové okno, kde můžete nakonfigurovat způsob, jak mají být testy mají být vytvořeny.

![Pomocí příkazu Vytvořit testy jednotek](media/createunittestcommand.png)

## <a name="set-unit-test-traits"></a>Nastavení vlastností testu jednotek

Pokud budete chtít spustit tyto testy jako součást procesu automatizace testů, můžete zvážit s testů vytvořené v jiném projektu testu (druhá možnost v dialogovém okně výše) a vlastnosti pro test jednotek pro testování částí nastavení. To umožňuje snadněji zahrňte nebo vylučte tyto specifické testy jako součást průběžné integrace nebo průběžného nasazování kanálu. Rysy jsou nastavené tak, že přidáte metadat pro testování částí přímo, jak je znázorněno níže.

![Nastavení vlastností testu jednotek](media/createunittest.png)

## <a name="use-third-party-unit-test-frameworks"></a>Použití rozhraní pro testování jednotky třetí strany

Automatické generování testů jednotek pro NUnit a xUnit, nainstalujte některou z následujících přípon framework testu z webu Visual Studio Marketplace:

* [NUnit rozšíření pro test generátory](https://marketplace.visualstudio.com/items?itemName=NUnitDevelopers.TestGeneratorNUnitextension)
* [xUnit.net rozšíření pro test generátory](https://marketplace.visualstudio.com/items?itemName=BradWilson.xUnitnetTestExtensions)

## <a name="when-should-i-use-this-feature"></a>Kdy použít tuto funkci?

Tuto funkci použít vždy, když je potřeba vytvořit testy jednotek, ale specificky při testování existující kód, který má žádné nebo téměř žádné pokrytí testu a žádná dokumentace. Jinými slovy ve kterých je specifikace omezené nebo neexistující kódu. Efektivně implementuje podobný přístup [inteligentní testování částí](https://devblogs.microsoft.com/devops/introducing-smart-unit-tests/) , který charakterizuje zjištěnou chování kódu.

Tato funkce je však vztahuje rovněž, když vývojář začíná napsáním nějakého kódu a pak, který používá ke spuštění testů jednotek. Ve službě flow kódování může být vhodné vývojáře k rychlému vytvoření jednotky testovací metoda zástupnou proceduru (s vhodné testovací třídy a vhodný testovacího projektu) pro konkrétní část kódu.

## <a name="see-also"></a>Viz také:

- [Vytvoření testu jednotek metoda zástupné procedury s "Vytvoření Unit Tests"](https://devblogs.microsoft.com/devops/creating-unit-test-method-stubs-with-create-unit-tests/)
- [Testování blogové příspěvky](https://devblogs.microsoft.com/devops/?s=unit+testing)
