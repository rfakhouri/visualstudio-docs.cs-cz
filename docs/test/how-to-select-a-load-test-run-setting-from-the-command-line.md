---
title: Nastavení spuštění zátěžového testu z příkazového řádku
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, command line
- load tests, run settings, selecting
ms.assetid: 175d1d58-f09a-4449-b132-a29a394a7c8e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e022eec099682581f244ad426500a512c63035d4
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55936158"
---
# <a name="how-to-select-a-load-test-run-setting-to-use-from-the-command-line"></a>Postupy: Vyberte nastavení, můžete používat z příkazového řádku pro spuštění zátěžového testu

Zátěžový test může obsahovat *parametry běhu*, které jsou vlastnosti, které ovlivňují způsob běhu zátěžového testu. Parametry spuštění jsou uspořádány podle kategorií v **vlastnosti** okna. Zátěžový test při svém spuštění používá parametry spuštění, které jsou aktuálně nastaveny jako aktivní.

Pokud zátěžový test obsahuje pouze jeden parametr spuštění, jedná se vždy o aktivní uzel. Pokud zátěžový test obsahuje více uzlů parametrů spuštění, můžete vybrat ten, který má použít při spuštění zátěžového testu z příkazového řádku. Zobrazit [jak: Přidání dalších parametrů běhu k zátěžovému testu](../test/how-to-add-additional-run-settings-to-a-load-test.md).

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="to-change-the-run-setting-from-the-command-line"></a>Chcete-li změnit nastavení spuštění z příkazového řádku

1.  Pokud chcete použít různé parametry spuštění z příkazového řádku využít tak strategii kontextových parametrů, použijte následující příkaz:

    `Set Test.UseRunSetting= CorporateStagingWebServer`

2.  Spusťte zátěžový test pomocí nástroje mstest:

    `mstest /testcontainer:loadtest1.loadtest`

## <a name="see-also"></a>Viz také:

- [Konfigurace parametrů spuštění zátěžového testu](../test/configure-load-test-run-settings.md)
- [Určení sad čítačů a mezních pravidel pro počítače v rámci zátěžového testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Postupy: Přidání dalších parametrů běhu k zátěžovému testu](../test/how-to-add-additional-run-settings-to-a-load-test.md)
- [Postupy: Vyberte aktivní parametry běhu zátěžového testu](../test/how-to-select-the-active-run-setting-for-a-load-test.md)
