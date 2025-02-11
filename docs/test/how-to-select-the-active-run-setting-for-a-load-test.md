---
title: Výběr parametru spuštění pro zátěžový Test
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, run settings, active
ms.assetid: ed6ff546-acfa-4dd8-b3a2-6e7455930ca4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 12582aa4c1aa41aa0a38f652cf4841ba1f9953e1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62949939"
---
# <a name="how-to-select-the-active-run-setting-for-a-load-test"></a>Postupy: Vyberte aktivní parametry běhu zátěžového testu

Po vytvoření zátěžového testu pomocí **nového Průvodce zátěžovým testem**, můžete použít **editoru zátěžového testu** Chcete-li změnit vlastnosti scénářů pro splnění potřebám a cílům testování.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

Zátěžový test může obsahovat jeden nebo více *parametry běhu* které představují sadu vlastností ovlivňujících způsob běhu zátěžového testu. Parametry spuštění jsou uspořádány podle kategorií v **vlastnosti** okna. Zátěžový test při svém spuštění používá parametry spuštění, které jsou aktuálně nastaveny jako aktivní.

> [!NOTE]
> Úplný seznam vlastností parametrů spuštění a jejich popis najdete v části [zátěžového testu spusťte nastavení](../test/load-test-run-settings-properties.md).

Pokud zátěžový test obsahuje pouze jeden parametr spuštění uzel v rámci **parametrů běhu** složka, tento uzel je vždy aktivní uzel. Pokud zátěžový test obsahuje více uzlů parametrů spuštění, můžete vybrat ten, který má použít při spuštění zátěžového testu. Zobrazit [jak: Přidání dalších parametrů běhu k Zátěžovému testu](../test/how-to-add-additional-run-settings-to-a-load-test.md).

V **editoru zátěžových testů**, aktivní parametry běhu je identifikován podle přípony "[Active]".

## <a name="select-the-active-run-setting"></a>Vyberte aktivního parametru spuštění

1. Otevřete zátěžový test.

2. Rozbalte **parametrů běhu** složky.

3. Klikněte pravým tlačítkem na uzel parametrů spuštění, který chcete být aktivní uzel a klikněte na tlačítko **nastavit jako aktivní**.

     V **zátěžového testu Edito**r, ovlivněných nastavení spuštění uzlu se aktualizuje s příponou "[Active]".

     Nastavení spuštění vybrané stane aktivní a zůstane aktivní, dokud nevyberete jinou parametry běhu jako aktivní.

> [!NOTE]
> Můžete přepsat aktivní spuštění nastavte proměnnou prostředí s názvem `Test.UseRunSetting=<run setting name>`. To je užitečné při spuštění zátěžového testu z příkazového řádku nebo z dávkového souboru. Tímto způsobem můžete vybrat různé parametry spuštění bez nutnosti otevřít zátěžového testu.

## <a name="specify-the-run-setting-to-use-from-the-command-line"></a>Zadejte nastavení spuštění z příkazového řádku

Můžete přepsat výchozích parametrů běhu v zátěžovém testu a nastavením proměnné prostředí z příkazového řádku:

**Nastavte Test.UseRunSetting=PreProdEnvironment**

A spusťte test:

**mstest /testcontainer:loadtest1.loadtest**

## <a name="see-also"></a>Viz také:

- [Konfigurace parametrů spuštění zátěžového testu](../test/configure-load-test-run-settings.md)
- [Určení sad čítačů a mezních pravidel pro počítače v rámci zátěžového testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Postupy: Přidání dalších parametrů běhu k zátěžovému testu](../test/how-to-add-additional-run-settings-to-a-load-test.md)