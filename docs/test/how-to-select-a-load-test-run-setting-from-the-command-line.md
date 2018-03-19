---
title: "Nastavení sady Visual Studio zatížení testu z příkazového řádku | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, command line
- load tests, run settings, selecting
ms.assetid: 175d1d58-f09a-4449-b132-a29a394a7c8e
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: e7a9a7dec6fffdb51cf71ff5a45a2841c616f8c0
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="how-to-select-a-load-test-run-setting-to-use-from-the-command-line"></a>Postupy: Výběr použitých parametrů běhu zátěžového testu z příkazového řádku

Zátěžový test může obsahovat jednu nebo více *spustit nastavení*, což je sada vlastností, které ovlivňují způsob spuštění zátěžového testu. Spuštění nastavení jsou uspořádány do kategorií v okně Vlastnosti. Zátěžový test při svém spuštění používá parametry spuštění, které jsou aktuálně nastaveny jako aktivní.

 Pokud zátěžový test obsahuje pouze jeden parametr spuštění, jedná se vždy o aktivní uzel. Pokud zátěžový test obsahuje více uzlů parametrů spuštění, lze zvolit ten, který má být použit při spuštění zátěžového testu z příkazového řádku. V tématu [postupy: přidání dalších parametrů běhu k Zátěžovému testu](../test/how-to-add-additional-run-settings-to-a-load-test.md).

## <a name="to-change-the-run-setting-from-the-command-line"></a>Změna parametrů spuštění z příkazového řádku

1.  Pokud chcete využít výhod strategie parametr kontextu pomocí různých nastavení spuštění z příkazového řádku, použijte následující příkaz:

    `Set Test.UseRunSetting= CorporateStagingWebServer`

2.  Spusťte zátěžový test pomocí nástroje mstest:

    `mstest /testcontainer:loadtest1.loadtest`

## <a name="see-also"></a>Viz také

- [Konfigurace běhu zátěžových testů](../test/configure-load-test-run-settings.md)
- [Určení sad čítačů a mezních pravidel pro počítače v zátěžovém testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Postupy: přidání dalších parametrů běhu k Zátěžovému testu](../test/how-to-add-additional-run-settings-to-a-load-test.md)
- [Postupy: Vyberte nastavení Active spouštění pro zátěžový Test](../test/how-to-select-the-active-run-setting-for-a-load-test.md)