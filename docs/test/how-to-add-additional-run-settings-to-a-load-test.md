---
title: Přidání parametrů běhu k Zátěžovému testu v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, run settings, adding
- load tests, run settings
ms.assetid: 257d2a24-d582-4cfe-8b2b-51f51ba9cc84
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 88c1170f2740423ba59f43a16ea6990f279c1203
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/20/2018
ms.locfileid: "39176772"
---
# <a name="how-to-add-additional-run-settings-to-a-load-test"></a>Postupy: přidání dalších parametrů běhu k zátěžovému testu

Parametry spuštění zátěžového testu určují celou řadu dalších nastavení. Patří mezi ně doba trvání testu, úroveň podrobností shromažďování výsledků a sady čítačů, které se shromažďují za běhu testu. Pro každý zátěžový test lze vytvořit a uložit několik parametrů spuštění a následně při spouštění testu zvolit jedno konkrétní nastavení. Počáteční parametr spuštění se přidá k zátěžovému testu při vytvoření zátěžového testu s použitím **nového Průvodce zátěžovým testem**.

 K zátěžovému testu lze přidat více parametrů spuštění s různými nastaveními vlastností a spouštět tak zátěžový test za jiných podmínek. Lze například přidat nové nastavení testu a použít jinou vzorkovací frekvenci či zadat delší dobu běhu. V jednu chvíli lze používat pouze jeden parametr spuštění; parametr, který se má spustit, určíte tak, že jej nastavíte jako aktivní.

## <a name="to-add-another-run-setting"></a>Přidání dalšího parametru spuštění

1.  Otevřete zátěžový test.

2.  (Volitelné) Rozbalte **parametrů běhu** složky.

3.  Klikněte pravým tlačítkem myši **parametrů běhu** a pak zvolte položku **přidat parametry spuštění**.

     Nový parametr spuštění se přidá do **parametrů běhu** složky.

4.  Na **zobrazení** nabídce zvolte **okno vlastností**.

     **Vlastnosti** se zobrazí okno s vlastnostmi pro vybraný parametr spuštění.

5.  V **vlastnosti** okno, použijte textové pole pro **název** vlastnost poskytnout nového parametru spuštění. název, který by měl popisovat záměr parametru spuštění (například **spuštění: pětiminutový běh** ).

6.  Použití **vlastnosti** oknu změnit parametry spuštění. Například změnit dobu spuštění **00:05:00** na test běžel pět minut.

    > [!NOTE]
    > Úplný seznam vlastností parametrů spuštění a jejich popis najdete v tématu [zátěžového testu spusťte nastavení](../test/load-test-run-settings-properties.md).

     Aby byl přidaný parametr spuštění použit, nastavte jej jako aktivní. Další informace najdete v tématu [postupy: výběr aktivního parametru spuštění pro zátěžový test](../test/how-to-select-the-active-run-setting-for-a-load-test.md).

## <a name="see-also"></a>Viz také:

- [Konfigurace parametrů spuštění zátěžového testu](../test/configure-load-test-run-settings.md)
- [Určení sad čítačů a mezních pravidel pro počítače v rámci zátěžového testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)