---
title: Přidání parametrů běhu k Zátěžovému testu
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, run settings, adding
- load tests, run settings
ms.assetid: 257d2a24-d582-4cfe-8b2b-51f51ba9cc84
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: c1d7f9d0c9ad07223d0b59d7aeca585b53432280
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63002241"
---
# <a name="how-to-add-additional-run-settings-to-a-load-test"></a>Postupy: Přidání dalších parametrů běhu k zátěžovému testu

Parametry spuštění zátěžového testu určují celou řadu dalších nastavení. Patří mezi ně doba trvání testu, úroveň podrobností shromažďování výsledků a sady čítačů, které se shromažďují za běhu testu. Pro každý zátěžový test lze vytvořit a uložit několik parametrů spuštění a následně při spouštění testu zvolit jedno konkrétní nastavení. Počáteční parametr spuštění se přidá k zátěžovému testu při vytvoření zátěžového testu s použitím **nového Průvodce zátěžovým testem**.

K zátěžovému testu lze přidat více parametrů spuštění s různými nastaveními vlastností a spouštět tak zátěžový test za jiných podmínek. Lze například přidat nové nastavení testu a použít jinou vzorkovací frekvenci či zadat delší dobu běhu. V jednu chvíli lze používat pouze jeden parametr spuštění; parametr, který se má spustit, určíte tak, že jej nastavíte jako aktivní.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="to-add-another-run-setting"></a>Přidání dalšího parametru spuštění

1. Otevřete zátěžový test.

2. (Volitelné) Rozbalte **parametrů běhu** složky.

3. Klikněte pravým tlačítkem myši **parametrů běhu** a pak zvolte položku **přidat parametry spuštění**.

     Nový parametr spuštění se přidá do **parametrů běhu** složky.

4. Na **zobrazení** nabídce zvolte **okno vlastností**.

     **Vlastnosti** se zobrazí okno s vlastnostmi pro vybraný parametr spuštění.

5. V **vlastnosti** okno, použijte textové pole pro **název** vlastnost poskytnout nového parametru spuštění. název, který by měl popisovat záměr parametru spuštění (například **spuštění: Pětiminutový běh**).

6. Použití **vlastnosti** oknu změnit parametry spuštění. Například změnit dobu spuštění **00:05:00** na test běžel pět minut.

    > [!NOTE]
    > Úplný seznam vlastností parametrů spuštění a jejich popis najdete v tématu [zátěžového testu spusťte nastavení](../test/load-test-run-settings-properties.md).

     Aby byl přidaný parametr spuštění použit, nastavte jej jako aktivní. Další informace najdete v tématu [jak: Vyberte aktivního parametru spuštění pro zátěžový test](../test/how-to-select-the-active-run-setting-for-a-load-test.md).

## <a name="see-also"></a>Viz také:

- [Konfigurace parametrů spuštění zátěžového testu](../test/configure-load-test-run-settings.md)
- [Určení sad čítačů a mezních pravidel pro počítače v rámci zátěžového testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)