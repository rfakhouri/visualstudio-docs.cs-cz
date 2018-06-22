---
title: Konfigurace běhu zátěžových testů v sadě Visual Studio
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, configuring run settings
ms.assetid: 0c86918b-cd63-4468-8f49-6d547a1276dc
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 7aa35b072429caffc8f499f4f1bd570dcd32265b
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36282870"
---
# <a name="configure-load-test-run-settings"></a>Konfigurace nastavení testu zatížení

*Parametry spuštění* jsou sadu vlastností, které ovlivňují způsob spuštění zátěžového testu. Spuštění nastavení jsou uspořádány do kategorií v **vlastnosti** okno.

Můžete mít více než jedno spuštění nastavení v zátěžovém testu, ale pouze jeden z parametrů běhu může být aktivní jedno spuštění. Další parametry spuštění poskytují rychlý způsob výběru alternativního nastavení pro následné běhy testu.

Počáteční spustit nastavení se vytvoří, když vytvoříte zátěžový test pomocí **načíst testování Průvodce novým**.

![Parametry spuštění zátěžového testu](../test/media/loadtestrunsettings.png)

## <a name="tasks"></a>Úlohy

|Úlohy|Související témata|
|-----------|-----------------------|
|**Přidat další parametry spuštění zátěžového testu:** kromě spuštění nastavení, která se vytvoří při spuštění **načíst testování Průvodce novým**, můžete přidat více spustit nastavení pro zátěžový test, aby můžete spustit test v rámci různých podmínky:|-   [Postupy: přidání dalších parametrů běhu k zátěžovému testu](../test/how-to-add-additional-run-settings-to-a-load-test.md)|
|**Zadejte aktivní spustit nastavení pro použití s zátěžového testu:** můžete vybrat, kterou chcete používat s vaší zátěžového testu pomocí editoru načíst testovací nastavení spuštění. Aktivní parametr spuštění lze rozpoznat pomocí přípony „[Active]“.|-   [Postupy: Vyberte aktivní spustit nastavení pro zátěžový test](../test/how-to-select-the-active-run-setting-for-a-load-test.md)|
|**Upravit spustit vlastnosti nastavení:** vaše práce můžete upravit vlastnosti nastavení pro e možnosti protokolování (Další informace níže), stanovení délky test, doba trvání warm-up, maximální počet chyb podrobnosti o ohlášených, vzorkovací frekvenci připojení Model (pouze testy výkonnosti webu), typ úložiště výsledků, úroveň ověření a trasování SQL. Parametry spuštění by měly odrážet cíle zátěžového testu.|-   [Vlastnosti nastavení spuštění zátěžového testu](../test/load-test-run-settings-properties.md)<br />-   [Změna vlastnosti spuštění nastavení](../test/load-test-run-settings-properties.md#LoadTestRunSettingsHowToChange)|
|**Zadejte počet iterací testů v nastavení testu zatížení:** můžete zadat počet spustit všechny testy výkonu a jednotka webu ve všech scénářích zátěžových testů nakonfigurováním **testování iterací** Vlastnost.|-   [Postupy: určení počtu testovacích iterací v parametrech běhu](../test/how-to-specify-the-number-of-test-iterations-in-a-load-test.md)|
|**Zadejte vzorkovací frekvenci pro zátěžový test spusťte nastavení:** můžete určit, jak často budou do mají zatížení testovací data čítače výkonu pro shromažďování konfigurací **vzorkovací frekvence** vlastnost.|-   [Postupy: určení vzorkovací frekvence](../test/how-to-specify-the-sample-rate-for-a-load-test.md)|
|**Zadejte možnost úložiště podrobností časování:** můžete určit, jak se mají podrobnosti zátěžový test, uložit tak, že nakonfigurujete **úložiště podrobností časování** vlastnost.|-   [Postupy: určení vlastnosti úložiště podrobností časování](../test/how-to-specify-the-timing-details-storage-property-for-a-load-test.md)|
|**Zadejte dobu uchování prostředků testu:** urychlení test > Opravit > testování cyklus zachováním testovací prostředky v zadaném období nastavením **dobu uchování prostředky** vlastnost.|-   [Zachovat prostředky pro urychlení zátěžové testování](/vsts/test/load-test/getting-started-with-performance-testing?view=vsts)|
|**Použití kontextových parametrů:** kontextových parametrů můžete Parametrizace řetězec. Například pokud zátěžového testu obsahuje testu výkonnosti webu, který používá parametrizované webový server, můžete přidat parametr kontextu spuštění nastavení, která se mapuje na jiný server.|-   [Postupy: Přidání kontextových parametrů k parametrům spuštění](../test/how-to-add-context-parameters-to-a-load-test-run-setting.md)|
|**Konfigurace vlastností protokolování testu:** můžete nakonfigurovat, jak často se data se zapisují do protokolu, která souvisí s testováním zatížení spusťte nastavení. To může být důležité při spouštění rozsáhlých nebo složitých zátěžových testů, protože protokol by mohl mít velikost několik gigabajtů.<br /><br /> Lze také nakonfigurovat, aby se soubor protokolu automaticky uložil při selhání zátěžového testu, což pomůže při ladění a analýze aplikace.|-   [Úprava nastavení protokolování testu zatížení](../test/modify-load-test-logging-settings.md)|