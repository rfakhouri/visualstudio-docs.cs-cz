---
title: Přidání parametrů běhu k Zátěžovému testu v sadě Visual Studio | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, run settings, adding
- load tests, run settings
ms.assetid: 257d2a24-d582-4cfe-8b2b-51f51ba9cc84
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: ff4a023f7bed6e182c6807b68a1ed918aee034df
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-additional-run-settings-to-a-load-test"></a>Postupy: Přidání dalších parametrů běhu k zátěžovému testu

Parametry spuštění zátěžového testu určují celou řadu dalších nastavení. Patří mezi ně doba trvání testu, úroveň podrobností shromažďování výsledků a sady čítačů, které se shromažďují za běhu testu. Pro každý zátěžový test lze vytvořit a uložit několik parametrů spuštění a následně při spouštění testu zvolit jedno konkrétní nastavení. Po vytvoření zátěžového testu pomocí nového Průvodce zátěžovým testem jsou k zátěžovému testu přidány počáteční parametry spuštění.

 K zátěžovému testu lze přidat více parametrů spuštění s různými nastaveními vlastností a spouštět tak zátěžový test za jiných podmínek. Lze například přidat nové nastavení testu a použít jinou vzorkovací frekvenci či zadat delší dobu běhu. V jednu chvíli lze používat pouze jeden parametr spuštění; parametr, který se má spustit, určíte tak, že jej nastavíte jako aktivní.

## <a name="to-add-another-run-setting"></a>Přidání dalšího parametru spuštění

1.  Otevřete zátěžový test.

2.  (Volitelné) Rozbalte **spustit nastavení** složky.

3.  Klikněte pravým tlačítkem myši **spustit nastavení** složky a vyberte **přidávat spusťte nastavení**.

     Nové nastavení spuštění se přidá do **spustit nastavení** složky.

4.  Na **zobrazení** nabídce zvolte **vlastnosti – okno**.

     Zobrazí se okno Vlastnosti s vlastnostmi pro vybraný parametr spuštění.

5.  V okně vlastností použijte textové pole pro **název** vlastnost umožnit nové spustit nastavení název, který popisuje záměr spuštění nastavení (například **spustit nastavení: pět minut spustit**).

6.  V okně Vlastnosti změňte parametry spuštění. Můžete například změnit pro spuštění dobu trvání **00:05:00** spustit svůj test na pět minut.

    > [!NOTE]
    > Úplný seznam vlastností parametrů běhu a jejich popisy najdete v tématu [vlastnosti nastavení spustit Test zatížení](../test/load-test-run-settings-properties.md).

     Aby byl přidaný parametr spuštění použit, nastavte jej jako aktivní. Další informace najdete v tématu [postup: Vyberte Active nastavení spouštění pro zátěžový Test](../test/how-to-select-the-active-run-setting-for-a-load-test.md).

## <a name="see-also"></a>Viz také

- [Konfigurace běhu zátěžových testů](../test/configure-load-test-run-settings.md)
- [Určení sad čítačů a mezních pravidel pro počítače v zátěžovém testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)