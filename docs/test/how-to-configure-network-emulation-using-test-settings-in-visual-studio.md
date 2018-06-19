---
title: Konfigurace emulace sítě s využitím testovacích nastavení v sadě Visual Studio
ms.date: 10/03/2016
ms.topic: conceptual
helpviewer_keywords:
- test settings, network emulation
ms.assetid: ff275cfb-5df9-4710-9a91-9caabaaad34f
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 66877397912fca0fbd3996c2dab146b040a047b3
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31972417"
---
# <a name="how-to-configure-network-emulation-using-test-settings-in-visual-studio"></a>Postupy: Konfigurace emulace sítě s využitím testovacích nastavení v sadě Visual Studio

Můžete nakonfigurovat adaptér diagnostických dat, který má testovat aplikaci v různých prostředích sítě ze sady Visual Studio. Lze ji také konfigurace na testování zatížení umělé sítě, nebo problémové místo, při spuštění testů.

> [!WARNING]
> Pokud spouštíte testy na skutečné síti, která je typu pomalejší než síť, kterou jsou emulace, bude i nadále spustit test nižší rychlostí sítě. Emulaci můžete pouze zpomalit síťové prostředí, není urychlit.

 Následující postup popisuje postup konfigurace emulace sítě s z editoru konfigurace. Tento postup platí pro editor konfigurací v nástroji Microsoft Test Manager a sady Visual Studio.

> [!NOTE]
> Adaptér diagnostických dat emulace sítě platí pouze pro nastavení testů v sadě Visual Studio. Pro nastavení testů v nástroji Microsoft Test Manager se nepoužívá.

Účet, který má oprávnění správce musí použít pro emulace sítě. Pokud jste vybrali emulace sítě pro roli místní, který spouští manuálních testů, je nutné spustit nástroje Microsoft Test Manager pomocí oprávnění správce. Pokud jste vybrali emulace sítě pro jiné role, je nutné ověřit, že testovacího agenta na počítači pro tuto roli používá uživatelský účet, který je členem skupiny administrators. Další informace o tom, jak nastavení účtu pro agenta test agent najdete v tématu [instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md).

> [!NOTE]
> Účet Network Service, což je výchozí účet pro test agenta, není členem skupiny administrators.

 **Skutečné emulace sítě s**

 Visual Studio použije softwarový skutečné emulace sítě s u všech typů testu. To zahrnuje zátěžové testy. Skutečné emulace sítě s simuluje síťové podmínky přímé manipulace s síťových paketů. Emulátor true sítě můžete emulují chování drátové a bezdrátové sítě pomocí spolehlivé fyzického propojení, jako je například na Ethernetu. Následující atributy sítě jsou součástí skutečné emulace sítě s:

-   Doba odezvy v síti (latence)

-   Množství dostupné šířky pásma

-   Chování služby Řízení front

-   Ztráta paketů

-   Změna pořadí paketů

-   Chyba šíření.

 Skutečné emulace sítě s taky poskytuje flexibilitu při filtrování síťových paketů na základě IP adresy nebo protokoly, například TCP, UDP a protokolu ICMP.

 Skutečné emulace sítě s lze založené na síti vývojáři a testerům, sada emulovat požadované testovacím prostředí, vyhodnocení výkonu, odhadnout účinky změny nebo rozhodnutí o technologii optimalizace. V porovnání s výskytu test hardwaru, skutečné emulace sítě s je výrazně levnější a flexibilnější řešení.

## <a name="configure-network-emulation-for-your-test-settings"></a>Konfigurace emulace sítě s pro nastavení testu
 Před provedením kroků v tomto postupu, otevřete nastavení testů ze sady Visual Studio a pak vyberte **datové a diagnostické** stránky.

### <a name="to-configure-network-emulation-for-your-test-settings"></a>Konfigurace emulace sítě pro nastavení testu

1.  Vyberte role, kterou chcete použít k emulaci konkrétní síť.

    > [!NOTE]
    > Budete muset nakonfigurovat adaptér emulace sítě s pouze na role klienta nebo role serveru. Není nutné používat adaptér na obě role. Adaptér emuluje šumu sítě, která má vliv na komunikaci mezi obě role, takže není nutné ji použít v obou. Pokud to není nezbytné, měli byste vybrat roli klienta pro adaptér emulace sítě s, aby se zabránilo další režii v roli serveru.

2.  Vyberte **emulace sítě s** a potom zvolte **konfigurace**.

     Zobrazí se dialogové okno Konfigurace emulace sítě.

3.  Vyberte šipku vedle **vyberte profil sítě používat**a vyberte typ sítě, který chcete emulovat při spuštění testu (například **kabel DSL 768Kps**).

    > [!WARNING]
    > Pokud spouštíte testy na skutečné síti, která je typu pomalejší než síť, která jsou emulace, bude i nadále spustit test nižší rychlostí sítě. Emulaci můžete pouze zpomalit síťové prostředí, není urychlit.

4.  Pokud jste zahrnuli adaptér diagnostických dat emulace sítě v nastavení testu a máte v úmyslu použít na místním počítači, pak je třeba také svázat ovladač emulace sítě jeden ze síťových adaptérů váš počítač. Ovladač emulace sítě je vyžadována pro adaptér diagnostických dat emulace sítě funkce. Ovladač emulace sítě je nainstalován a vázána na váš adaptér dvěma způsoby:

    -   **Ovladač emulace sítě s Microsoft Visual Studio Test Agent nainstalovat:** Microsoft Visual Studio Test Agent lze použít na vzdálených počítačích a v místním počítači. Když instalujete Visual Studio agentem Test Agent, proces instalace zahrnuje krok konfigurace, která se váže k síťové kartě ovladač emulace sítě. Další informace najdete v tématu [instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md).

    -   **Ovladač emulace sítě s Microsoft Visual Studio Test Professional nainstalovat:** při použití emulace sítě poprvé, budete vyzváni k vytvoření vazby ovladač emulace sítě síťové karty.

    > [!TIP]
    > Můžete také nainstalovat ovladač emulace sítě z příkazového řádku na místním počítači bez instalace agenta pro testovací sady Visual Studio pomocí následujícího příkazu:   **/VSTestConfig NETWORKEMULATION Install**

## <a name="see-also"></a>Viz také

- [Shromažďování diagnostických informací s použitím nastavení testu](../test/collect-diagnostic-information-using-test-settings.md)
- [Spouštění manuálních testů (VSTS)](/vsts/manual-test/getting-started/run-manual-tests)