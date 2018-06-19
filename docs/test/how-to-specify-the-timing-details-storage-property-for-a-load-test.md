---
title: Vlastnosti úložiště podrobností časování pro spuštění zátěžového testu v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, properties
- load tests, run settings
ms.assetid: 867a9c21-0909-4963-bc02-d41e9393008c
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: a41b9e7470fb9741a47f355e533c0451fe67fc3a
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31974054"
---
# <a name="how-to-specify-the-timing-details-storage-property-for-a-load-test-run-setting"></a>Postupy: Určení vlastnosti úložiště podrobností časování pro parametry běhu zátěžového testu

Po vytvoření vaší zátěžový test pomocí **načíst testování Průvodce novým**, můžete použít **načíst Editor testů** Chcete-li změnit nastavení, aby splňovalo potřeby testování a cíle.

Můžete upravit nastavení spuštění **úložiště podrobností časování** hodnotu vlastnosti v **vlastnosti** okno. **Úložiště podrobností časování** může být nastavena na žádnou z následujících možností:

-   **Všechny podrobnosti o jednotlivých:** shromažďuje a ukládá data jednotlivých časování pro každý test, transakce a stránka vydané během testu.

    > [!NOTE]
    > **Všech podrobností o jednotlivých** je třeba vybrat možnost povolení informace data virtuálních uživatelů v si výsledky testu zatížení. Další informace najdete v tématu [analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md).

-   **Žádné:** neshromažďuje žádné informace o jednotlivých časování. Průměrné hodnoty jsou však stále k dispozici.

-   **Pouze statistiku:** ukládá data jednotlivých časování, ale pouze jako percentilu data. To umožňuje ušetřit místo na prostředky.

 **Důležité informace týkající se vlastnosti úložiště podrobností časování**

 Pokud **úložiště podrobností časování** je povolena vlastnost a potom čas spuštění každé jednotlivé testy, transakce a stránku během zátěžového testu se budou ukládat do úložiště výsledků zátěžového testu. To umožňuje data 90 a 95. percentil zobrazený v Analyzéru zátěžového testu v tabulkách testy, transakce a stránky.

 Pokud **úložiště podrobností časování** vlastnost povolena, podle nastavení její hodnoty na buď **StatisticsOnly** nebo **AllIndividualDetails**, všechny jednotlivé testy, stránky a transakce jsou vypršel časový limit a percentilu dat se počítá z dat jednotlivých časování. Rozdíl je, že se **StatisticsOnly** po vypočítáváno data percentilu možnost jednotlivých načasování data se odstraní z úložiště. Tím se snižuje množství místa, které je vyžadováno úložiště podrobností časování se používají. Můžete ale chtít zpracovat podrobných dat časování v jiné způsoby pomocí nástroje SQL, v takovém případě **AllIndividualDetails** by měl být použit, aby byla dostupná pro toto zpracování podrobných dat časování. Kromě toho pokud nastavíte vlastnost na **AllIndividualDetails**, pak můžete analyzovat aktivity virtuálních uživatelů po dokončení spuštění zátěžového testu pomocí grafu aktivity virtuálních uživatelů v analyzátoru načíst otestovat. Další informace najdete v tématu [analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md).

 Množství místa v úložiště výsledků zátěžového testu pro ukládání dat časování podrobnosti může být velký, zejména pro již spouštění zátěžových testů. Navíc čas k uložení dat této v zátěžový test, který úložiště výsledků zátěžového testu na konci je delší, protože tato data jsou ukládána v testovacích agentů zatížení, dokud zátěžový test byl dokončen, po kterých jsou data uložena do úložiště. **Úložiště podrobností časování** vlastnost je ve výchozím nastavení povolené. Jedná se o problém pro testovací prostředí, můžete nastavit **úložiště podrobností časování** k **žádné**.

 Podrobnosti dat časování je uložený v souboru LoadTestItemResults.dat během spuštění a je odeslána zpět do kontroleru, po dokončení zátěžový test. Velikost souboru je pro zátěžový test systémem po dlouhou dobu, velké. Pokud v počítači agenta není dostatek místa na disku, bude problém.

 Pokud projekt provádíte upgrade z předchozí verze sady Visual Studio zátěžový test, použijte následující postup povolení kolekce úplné podrobnosti.

## <a name="to-configure-the-timing-details-storage-property-in-a-load-test"></a>Konfigurovat vlastnosti úložiště podrobností časování v zátěžovém testu

1.  Otevřete v editoru zátěžových testů zátěžový test.

2.  Rozbalte **spustit nastavení** uzlu v zátěžovém testu.

3.  Zvolit na spuštění nastavení, které chcete konfigurovat, například **spustit Settings1 [Active]**.

4.  Otevřete okno Vlastnosti. Na **zobrazení** nabídce vyberte možnost **vlastnosti – okno**.

5.  V části **výsledky** kategorie, vyberte **úložiště podrobností časování** vlastnost a vyberte **všech podrobností o jednotlivých**.

     Po dokončení konfigurace **všech podrobností o jednotlivých** nastavení **úložiště podrobností časování** vlastnost, můžete spustit zátěžový test a zobrazení grafu aktivity virtuálního uživatele. Další informace najdete v tématu [postupy: Analýza co virtuální uživatelé jsou to během zátěžový Test](../test/how-to-analyze-virtual-user-activity-during-a-load-test.md).

## <a name="see-also"></a>Viz také

- [Analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)
- [Návod: Izolace problémů pomocí graf aktivity virtuálního uživatele](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)