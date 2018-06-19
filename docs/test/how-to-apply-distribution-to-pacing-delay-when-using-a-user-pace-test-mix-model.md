---
title: Použití rozdělení pro zpoždění interval pro zátěžové testování
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, test mix model
ms.assetid: ae8b35f9-d465-4d72-8d7d-7b56ae6ffd22
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 268578638524ab4f5e5db605c3d394d28414547a
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/22/2018
ms.locfileid: "34448516"
---
# <a name="how-to-apply-distribution-to-pacing-delay-for-a-user-pace-test-mix-model"></a>Postupy: použití rozdělení pro interval zpoždění pro model kombinace testů se stimulací podle uživatele

Jakmile vytvoříte zátěžový test pomocí **načíst testování Průvodce novým**, editoru načíst testování můžete změnit vlastnosti tento scénář pro splnění vašich potřeb testování a cíle.

**Použít distribuční interval zpoždění** je nastavena pomocí **vlastnosti** okno. Vlastnosti scénáře zátěžového testu jsou upravit pomocí editoru zátěžových testů.

> [!NOTE]
> **Použít distribuční interval zpoždění** vlastnost platí jenom v případě *načíst poměru testů* je nakonfigurován na základě stimulací podle uživatele. Další informace najdete v tématu [úpravy modelů kombinací určení pravděpodobnosti virtuální uživatele spuštění testu](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).

Hodnota **použít distribuční interval zpoždění** lze nastavit na true nebo false:

- **Hodnota TRUE,**: Tento scénář platí normálního rozdělení. statistické zpoždění, které jsou určené hodnotě v **testy na uživatele za hodinu** sloupec v dialogovém okně Upravit poměru testů. Další informace najdete v tématu [úpravy modelů kombinací určení pravděpodobnosti virtuální uživatele spuštění testu](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).

     Předpokládejme například, že máte **testy na uživatele za hodinu** hodnotu v dialogovém okně Upravit kombinace testů pro test nastavit dva uživatelům za hodinu. Pokud **použít distribuční interval zpoždění** je nastavena na **True**, normální statistické distribuční se použije na dobu čekání mezi testy. Testy budou přesto spuštěny dva testy za hodinu, ale nemusí být nutně 30 minut zpoždění mezi nimi. První test by mohl spustit až čtyři minut a druhý test po 45 minut.

- **False**: testu tempem, který jste zadali pro hodnotu v **testy na uživatele za hodinu** sloupec v **úpravy poměru testů** dialogové okno. Další informace najdete v tématu [úpravy modelů kombinací určení pravděpodobnosti virtuální uživatele spuštění testu](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md).

     Předpokládejme například, že máte **testy na uživatele za hodinu** hodnotu **úpravy kombinace testů** nastavte dialogové okno pro test na dva uživatele za hodinu. Pokud **použít distribuční interval zpoždění** je nastavena na **False**, udělujete žádné volně mohou při spuštění testů. Test se spouští každých 30 minut. Tím je zajištěno, že můžete spustit dva testy za hodinu.

## <a name="to-specify-the-apply-distribution-to-pacing-delay-property-setting-for-a-scenario"></a>Určení distribučních použít k nastavení vlastnosti interval zpoždění pro scénáře

1. Otevřete zátěžový test.

   **Editoru zátěžových testů** se zobrazí. Zobrazí se strom zátěžového testu.

2. V **scénáře** složky stromu testu zatížení vyberte scénář uzlu, kterou chcete použít intervalu distribuce do.

3. Na **zobrazení** nabídce vyberte možnost **vlastnosti – okno**.

   Kategorií a vlastností tohoto scénáře se zobrazují v **vlastnosti** okno.

4. V hodnotě vlastnosti pro **použít distribuční interval zpoždění**, vyberte buď **True** nebo **False**.

5. Vyberte **soubor** > **Uložit**. Teď můžete spustit zátěžový test pomocí nového **použít distribuční interval zpoždění** hodnotu.

## <a name="see-also"></a>Viz také

- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)
- [Návod: Vytvoření a spuštění zátěžového testu](../test/walkthrough-create-and-run-a-load-test.md)
- [Kontrolery testů a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md)
- [Vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md)