---
title: Vyberte nastavení spouštění pro zátěžový Test v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, run settings, active
ms.assetid: ed6ff546-acfa-4dd8-b3a2-6e7455930ca4
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 8566964ab8dd3fbfa1fca15ce8362218c99c27e6
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31967606"
---
# <a name="how-to-select-the-active-run-setting-for-a-load-test"></a>Postupy: Výběr aktivních parametrů spouštění pro zátěžový test

Po vytvoření vaší zátěžový test pomocí **načíst testování Průvodce novým**, můžete použít **načíst Editor testů** ke změně vlastností scénáře pro splnění vašich potřeb testování a cíle.

Zátěžový test může obsahovat jednu nebo více *spustit nastavení* který jsou sadu vlastností, které ovlivňují způsob spuštění zátěžového testu. Spuštění nastavení jsou uspořádány do kategorií v okně Vlastnosti. Zátěžový test při svém spuštění používá parametry spuštění, které jsou aktuálně nastaveny jako aktivní.

> [!NOTE]
> Úplný seznam vlastností parametrů běhu a jejich popisy najdete v tématu [vlastnosti nastavení spustit Test zatížení](../test/load-test-run-settings-properties.md).

Pokud obsahuje jenom jeden uzel spouštění v rámci zátěžového testu **spustit nastavení** složky, tento uzel je vždy aktivní uzel. Pokud zátěžového testu obsahuje několik parametrů běhu uzly, můžete vybrat má použít při spuštění zátěžového testu. V tématu [postupy: přidání dalších parametrů běhu k Zátěžovému testu](../test/how-to-add-additional-run-settings-to-a-load-test.md).

V editoru zátěžových testů aktivní spustit nastavení je identifikován příponou "[Active]".

## <a name="selecting-the-active-run-setting"></a>Výběr nastavení Active spuštění

### <a name="to-select-the-active-run-setting-in-a-load-test"></a>Chcete-li vybrat aktivní běhu v zátěžovém testu

1.  Otevřete zátěžový test.

2.  Rozbalte **spustit nastavení** složky.

3.  Klikněte pravým tlačítkem na spuštění nastavení uzlu, který chcete být aktivní uzel a potom vyberte **nastavená jako aktivní**.

     V **Edito testu zatížení**r, ovlivněných nastavení spuštění uzlu se aktualizuje s příponou "[Active]".

     Spuštění vybraným nastavením stane aktivní a zůstane aktivní, dokud nevyberete jinou spusťte nastavení jako aktivní.

> [!NOTE]
> Můžete přepsat active spustit nastavení podle nastavení proměnné prostředí s názvem `Test.UseRunSetting=<run setting name>`. To je užitečné v případě spuštění zátěžového testu z příkazového řádku nebo z dávkového souboru. Tímto způsobem můžete vybrat jiné nastavení spuštění bez otevření zátěžový test.


## <a name="specifying-the-run-setting-to-use-from-the-command-line"></a>Určení nastavení spuštění z příkazového řádku pro použití
 Můžete přepsat výchozí spusťte nastavení v zátěžovém testu nastavením proměnné prostředí z příkazového řádku:

 **Nastavit Test.UseRunSetting=PreProdEnvironment**

 A spusťte test:

 **/testcontainer:loadtest1.loadtest mstestu**

## <a name="see-also"></a>Viz také

- [Konfigurace běhu zátěžových testů](../test/configure-load-test-run-settings.md)
- [Určení sad čítačů a mezních pravidel pro počítače v zátěžovém testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Postupy: přidání dalších parametrů běhu k Zátěžovému testu](../test/how-to-add-additional-run-settings-to-a-load-test.md)