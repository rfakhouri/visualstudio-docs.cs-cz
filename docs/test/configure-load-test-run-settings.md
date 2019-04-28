---
title: Konfigurace parametrů běhu zátěžových testů
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, configuring run settings
ms.assetid: 0c86918b-cd63-4468-8f49-6d547a1276dc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 751dda344f65160fc76a528380d1f61e2cae5bec
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62784129"
---
# <a name="configure-load-test-run-settings"></a>Konfigurace parametrů spuštění zátěžového testu

*Nastavení spuštění* představují sadu vlastností ovlivňujících způsob běhu zátěžového testu. Parametry spuštění jsou uspořádány podle kategorií v **vlastnosti** okna.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

V rámci zátěžového testu, ale pouze jeden z parametrů běhu může být aktivní za běhu může mít více než jeden parametr spuštění. Další parametry spuštění poskytují rychlý způsob výběru alternativního nastavení pro následné běhy testu.

Počáteční parametr spuštění se vytvoří při vytvoření zátěžového testu pomocí **nového Průvodce zátěžovým testem**.

![Parametry spuštění zátěžového testu](../test/media/loadtestrunsettings.png)

## <a name="tasks"></a>Úlohy

|Úlohy|Související témata|
|-|-|
|**Přidáte více parametrů spuštění do zátěžového testu:** Kromě nastavení spuštění, který je vytvořen při spuštění **nového Průvodce zátěžovým testem**, přidáním dalších parametrů spuštění do zátěžového testu tak, že spustíte test za jiných podmínek.|-   [Jak: Přidání dalších parametrů běhu k zátěžovému testu](../test/how-to-add-additional-run-settings-to-a-load-test.md)|
|**Určení aktivního parametru spuštění pro zátěžový test:** Můžete vybrat nastavení spuštění, který chcete používat se zátěžovým testem pomocí editoru zátěžového testu. Aktivní parametr spuštění lze rozpoznat pomocí přípony „[Active]“.|-   [Jak: Vyberte aktivní parametry běhu zátěžového testu](../test/how-to-select-the-active-run-setting-for-a-load-test.md)|
|**Úprava vlastností parametrů spuštění:** Spuštění můžete upravit nastavení vlastností pro takové věci jako možnosti protokolování (Další informace naleznete níže), určení délky testu, dobu zahřívání, maximální počet chyb podrobnosti o ohlášených, vzorkovací frekvenci, model připojení (jenom testy webového výkonu), výsledky Typ úložiště, úroveň validace a SQL trasování. Parametry spuštění by měly odrážet cíle zátěžového testu.|-   [Vlastnosti nastavení běhu zátěžového testu](../test/load-test-run-settings-properties.md)<br />-   [Změna vlastností nastavení spuštění](../test/load-test-run-settings-properties.md#change-run-setting-properties)|
|**Určení počtu iterací testu v spuštění zátěžového testu:** Můžete určit počet, kolikrát chcete spustit všechny webového výkonu a testy jednotek ve všech scénářích zátěžových testů pomocí konfigurace **testovacích iterací** vlastnost.|-   [Jak: Určení počtu testovacích iterací v nastavení spuštění](../test/how-to-specify-the-number-of-test-iterations-in-a-load-test.md)|
|**Určení vzorkovací frekvence pro spuštění zátěžového testu:** Můžete určit, jak často chcete, aby zátěžový test shromažďoval data čítačů výkonu tím, že nakonfigurujete **vzorkovací frekvence** vlastnost.|-   [Jak: Určení vzorkovací frekvence](../test/how-to-specify-the-sample-rate-for-a-load-test.md)|
|**Zadejte možnosti úložiště podrobností časování:** Můžete určit, jak chcete podrobnosti zátěžového testu uložen tím, že nakonfigurujete **úložiště podrobností časování** vlastnost.|-   [Jak: Určení vlastnosti úložiště podrobností časování](../test/how-to-specify-the-timing-details-storage-property-for-a-load-test.md)|
|**Zadejte dobu uchování zdrojů testu:** Urychlit test > Opravit > otestujeme cyklu zachováním testovací prostředky během zadaného období nastavením **doba uchování prostředků** vlastnost.|-   [Uchovávat prostředky pro urychlení zátěžové testování](/azure/devops/test/load-test/getting-started-with-performance-testing?view=vsts)|
|**Použití kontextových parametrů:** Použití kontextových parametrů pro parametrizaci řetězce. Například pokud zátěžový test obsahuje test výkonnosti webu, který používá parametrizované webový server, můžete přidat kontextový parametr parametrů spuštění, které se mapují na jiný server.|-   [Jak: Přidání kontextových parametrů k parametrům spuštění](../test/how-to-add-context-parameters-to-a-load-test-run-setting.md)|
|**Konfigurace vlastností protokolování testu:** Můžete nakonfigurovat, jak často se data zapisují do protokolu, který je spojen s parametry spuštění zátěžového testu. To může být důležité při spouštění rozsáhlých nebo složitých zátěžových testů, protože protokol by mohl mít velikost několik gigabajtů.<br /><br /> Lze také nakonfigurovat, aby se soubor protokolu automaticky uložil při selhání zátěžového testu, což pomůže při ladění a analýze aplikace.|-   [Úprava nastavení protokolování zátěžového testu](../test/modify-load-test-logging-settings.md)|