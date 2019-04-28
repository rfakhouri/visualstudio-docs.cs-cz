---
title: Instalace systémů testování částí od třetích stran
ms.date: 04/01/2019
ms.topic: conceptual
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 9f61b52f72474a8ecd8fac4c30265dcd7cf36a5e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62978651"
---
# <a name="install-unit-test-frameworks"></a>Nainstalujte rozhraní pro testování částí

Visual Studio Test Explorer můžete spouštět testy z libovolné jednotky rozhraní testování, který byl vyvinut adaptéru rozhraní pro něj. Instalace rozhraní framework kopíruje binární soubory a přidá šablony projektů Visual Studio pro jazyky, které podporuje. Při vytváření projektu se šablonou rozhraní zaregistrován pomocí Průzkumníka testů.

Řešení sady Visual Studio může obsahovat projektů testů jednotek, které používají různá rozhraní a, který cílí na různé jazyky.

[MSTest](getting-started-with-unit-testing.md) je rozhraní pro testování poskytovaný sadou Visual Studio a je ve výchozím nastavení nainstalovaná.

## <a name="acquire-frameworks"></a>Získání rozhraní

Nainstalujte rozhraní pro testování jednotky třetí strany s použitím **Správce balíčků NuGet**.

1. Klikněte pravým tlačítkem na projekt, který bude obsahovat váš testovací kód a vybrat **spravovat balíčky NuGet**.

2. V **Správce balíčků NuGet**, vyhledejte testovací rozhraní, kterou chcete nainstalovat a potom klikněte na **nainstalovat**.

   ![Správce balíčků NuGet v sadě Visual Studio](media/vs-2019/nuget-package-manager.png)

## <a name="update-to-the-latest-test-adapters"></a>Aktualizovat na nejnovější adaptéry testu

Aktualizace na nejnovější stabilní testovací adaptér, který má lepší prostředí testování a spuštění zjišťování. Další informace o aktualizacích adaptéry testů xUnit, MSTest a NUnit, najdete v článku [blogu sady Visual Studio](https://devblogs.microsoft.com/visualstudio/test-experience-improvements/).

### <a name="to-update-to-the-latest-stable-test-adapter-version"></a>Aktualizovat na nejnovější stabilní test adapter verze

1. Otevřete Správce balíčků Nuget pro řešení tak, že přejdete do **nástroje** > **Správce balíčků NuGet** > **spravovat balíčky NuGet pro řešení**.

2. Klikněte na **aktualizace** kartu a vyhledejte xUnit, MSTest nebo NUnit testování adaptéry, které jsou nainstalovány.

3. Vyberte jednotlivé adaptéry testu a pak v rozevírací nabídce vyberte nejnovější stabilní verzi.

4. Zvolte **nainstalovat** tlačítko.

   ![Upgrade adaptéru testu](media/install-adapter-upgrade.png)

## <a name="see-also"></a>Viz také:

- [Testování částí kódu](../test/unit-test-your-code.md)
