---
title: Vlastnosti úložiště podrobností časování pro spuštění zátěžového testu
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, properties
- load tests, run settings
ms.assetid: 867a9c21-0909-4963-bc02-d41e9393008c
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: ec6ca0e39a7816d99377bc13e1274cbc96a663ea
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62970633"
---
# <a name="how-to-specify-the-timing-details-storage-property-for-a-load-test-run-setting"></a>Postupy: Určení vlastnosti úložiště podrobností časování pro spuštění zátěžového testu

Po vytvoření zátěžového testu pomocí **nového Průvodce zátěžovým testem**, můžete použít **editoru zátěžového testu** Chcete-li změnit nastavení, aby splňovalo potřebám a cílům testování.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

Můžete upravit nastavení spuštění **úložiště podrobností časování** hodnotu vlastnosti v **vlastnosti** okna. **Úložiště podrobností časování** vlastnost lze nastavit na kteroukoli z následujících možností:

- **Detaily o všech jednotlivých položkách:** Shromažďuje a ukládá data jednotlivých časování pro každý test, transakci a stránku zmíněnou v průběhu testu.

  > [!NOTE]
  > **Detaily o všech jednotlivých položkách** musí být vybrána možnost povolit informace o datech virtuálních uživatelů ve vašich výsledcích zátěžového testu. Další informace najdete v tématu [analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md).

- **Žádné:** Neshromažďuje žádné podrobnosti jednotlivých časování. Průměrné hodnoty jsou však stále k dispozici.

- **Pouze statistiky:** Ukládá data jednotlivých časování, ale pouze jako percentil. Tím ušetříte prostředky prostoru.

  **Důležité informace týkající se vlastnosti úložiště podrobností časování**

  Pokud **úložiště podrobností časování** vlastnost je povolená, pak čas ke spuštění každé jednotlivé testy, transakce a stránky během zátěžového testu uložen v úložišti výsledků zátěžového testu. To umožňuje 90. percentil. a 95. percentil dat zobrazený v **Analyzéru zátěžového testu** v **testy**, **transakce**, a **stránky** tabulky.

  Pokud **úložiště podrobností časování** je povolena vlastnost nastavením její hodnoty na buď **StatisticsOnly** nebo **AllIndividualDetails**, všechny individuální testy, stránky, a transakce jsou časovány a data percentilu se vypočtou z jednotlivých dat časování. Rozdíl je, že u **StatisticsOnly** poté, co byla vypočtena data pro percentil, možnost jednotlivá časová data odstraněna z úložiště. To snižuje množství místa, které je nutné v úložišti, pokud jsou použity podrobnosti časování. Můžete však chtít zpracovat podrobná data časování jiným způsobem pomocí nástrojů SQL, v takovém případě **AllIndividualDetails** by měl být použit, tak, aby podrobná data časování byla k dispozici pro zpracování. Navíc pokud nastavíte vlastnost na **AllIndividualDetails**, pak lze analyzovat aktivity virtuálního uživatele pomocí **graf aktivity virtuálního uživatele** v **Analyzéru zátěžového testu** po dokončení zátěžového testu. Další informace najdete v tématu [analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md).

  Množství místa potřebné v úložišti výsledků zátěžového testu k ukládání dat s podrobnosti časování může být značné, zejména pro delší zkoušky zatížení. Také čas pro ukládání těchto dat v zátěžovém testu, které úložiště výsledků na konci zátěžového testu je delší, protože tato data jsou uložena v agentech zátěžového testu, dokud zátěžový test neskončí, po kterém jsou data uložena do úložiště. **Úložiště podrobností časování** ve výchozím nastavení je povolena vlastnost. Pokud je to problém pro testovací prostředí, možná budete chtít nastavit **úložiště podrobností časování** k **žádný**.

  Podrobnosti časování, data se ukládají do *LoadTestItemResults.dat* ukládáte za běhu a jsou odeslány zpět do řadiče po dokončení zátěžového testu. U zátěžového test spuštěného na dlouhou dobu velikost souboru je velká. Pokud na počítači agenta není dostatek místa na disku, bude problém.

  Pokud provádíte upgrade projektu z předchozí verze zátěžového testu sady Visual Studio, pomocí následující postupu povolíte zcela podrobnou kolekci.

## <a name="to-configure-the-timing-details-storage-property-in-a-load-test"></a>Konfigurace vlastnosti úložiště podrobností načasování v zátěžovém testu

1. V editoru zátěžového testu otevřete zátěžový test.

2. Rozbalte **parametrů běhu** uzlu v zátěžovém testu.

3. Zvolte v běhu, které chcete konfigurovat, například **běhu1 [aktivní]**.

4. Otevřít **vlastnosti** okna. Na **zobrazení** nabídce vyberte možnost **okno vlastností**.

5. V části **výsledky** kategorie, zvolte **úložiště podrobností časování** vlastnosti a vyberte **detaily o všech jednotlivých položkách**.

     Po nakonfigurování **detaily o všech jednotlivých položkách** nastavení **úložiště podrobností časování** vlastností, můžete spustit zatížení testování a zobrazení **graf aktivity virtuálního uživatele**. Další informace najdete v tématu [jak: Co dělají virtuálních uživatelů během zátěžového testu analyzovat](../test/how-to-analyze-virtual-user-activity-during-a-load-test.md).

## <a name="see-also"></a>Viz také:

- [Analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)
- [Návod: Izolace problémů pomocí graf aktivity virtuálního uživatele](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)