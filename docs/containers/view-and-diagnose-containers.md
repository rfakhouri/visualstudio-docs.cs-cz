---
title: Protokoly kontejnerů, proměnné prostředí, přístup k systému souborů &
description: Popisuje, jak vylepšit schopnost ladit a diagnostikovat aplikace založené na kontejnerech v aplikaci Visual Studio pomocí okna nástroje, které vám umožní zjistit, co se v kontejnerech hostujících vaší aplikaci nachází.
author: ghogen
ms.author: ghogen
ms.topic: conceptual
ms.date: 05/06/2019
ms.technology: vs-azure
monikerRange: vs-2019
ms.openlocfilehash: 3fb9a52f990a2e492c63a6e71a7cc2063110c816
ms.sourcegitcommit: 44e9b1d9230fcbbd081ee81be9d4be8a485d8502
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2019
ms.locfileid: "70179834"
---
# <a name="how-to-view-and-diagnose-containers-in-visual-studio"></a>Postup zobrazení a diagnostiky kontejnerů v aplikaci Visual Studio

Můžete zobrazit, co se chystá v kontejnerech, které hostují vaši aplikaci pomocí okna **kontejnery** . Pokud jste použili k používání příkazového řádku ke spuštění příkazů Docker k zobrazení a diagnostice toho, co se v kontejnerech chystá, toto okno poskytuje pohodlnější způsob, jak monitorovat kontejnery bez nutnosti opustit prostředí Visual Studio IDE.

> [!NOTE]
> Okno kontejnery je aktuálně dostupné jako rozšíření verze Preview, které si můžete [Stáhnout](https://aka.ms/vscontainerspreview) pro Visual Studio 2019.

## <a name="prerequisites"></a>Požadavky

- [Docker Desktop](https://hub.docker.com/editions/community/docker-ce-desktop-windows)
- Instalace sady [Visual Studio 2019](https://visualstudio.microsoft.com/downloads)
- Instalace [rozšíření okna kontejnerů](https://aka.ms/vscontainerspreview)

## <a name="view-information-about-your-containers"></a>Zobrazit informace o kontejnerech

Okno **kontejnery** se automaticky otevře při spuštění kontejnerového projektu .NET. Chcete-li zobrazit kontejnery v aplikaci Visual Studio kdykoli, použijte **kombinaci kláves CTRL**+**Q** k aktivaci vyhledávacího pole aplikace Visual Studio `Containers` a zadejte a vyberte první položku. Můžete také otevřít okno **kontejnery** z hlavní nabídky. Použijte cestu nabídky k **zobrazení** > **jiných** > **kontejnerů**Windows.  

![Snímek obrazovky s kartou prostředí v okně kontejnery](media/view-and-diagnose-containers/container-window.png)

Na levé straně se zobrazí seznam kontejnerů na místním počítači. Kontejnery spojené s vaším řešením jsou uvedené v části **kontejnery řešení**. Napravo se zobrazí podokno s kartami pro **prostředí**, **porty**, **protokoly**a **soubory**.

> [!TIP]
> V aplikaci Visual Studio můžete snadno přizpůsobit, kde je ukotveno okno nástrojů **kontejnery** . Viz [přizpůsobení rozložení oken v aplikaci Visual Studio](/visualstudio/ide/customizing-window-layouts-in-visual-studio). Ve výchozím nastavení je okno **kontejnery** ukotveno v okně **kukátka** při spuštění ladicího programu.

## <a name="view-environment-variables"></a>Zobrazit proměnné prostředí

Karta **prostředí** zobrazuje proměnné prostředí v kontejneru. Pro kontejner vaší aplikace můžete tyto proměnné nastavit mnoha způsoby, například v souboru Dockerfile, v souboru. env nebo pomocí možnosti-e při spuštění kontejneru pomocí příkazu Docker.

![Snímek obrazovky s kartou prostředí v okně kontejnery](media/view-and-diagnose-containers/container-environment-vars.png)

> [!NOTE]
> Jakékoli změny proměnných prostředí se neprojeví v reálném čase. Proměnné prostředí na této kartě jsou také proměnné prostředí systému v kontejneru a neodrážejí proměnné uživatelského prostředí, které jsou místní pro aplikaci.

## <a name="view-port-mappings"></a>Zobrazit mapování portů

Na kartě **porty** můžete kontrolovat mapování portů, které jsou platné pro váš kontejner.

![Snímek obrazovky s kartou porty v okně kontejnery](media/view-and-diagnose-containers/container-ports.png)

Dobře známé porty jsou propojené, takže pokud je na portu dostupný obsah, můžete kliknutím na odkaz otevřít prohlížeč.

## <a name="view-logs"></a>Zobrazení protokolů

Na kartě **protokoly** se zobrazují výsledky `docker logs` příkazu. Ve výchozím nastavení karta zobrazuje streamy stdout a stderr na kontejneru, ale můžete nakonfigurovat výstup. Podrobnosti najdete v tématu [protokolování Docker](https://docs.docker.com/config/containers/logging/).  Ve výchozím nastavení zaproudí protokoly na kartě **protokoly** , ale můžete ji zakázat kliknutím na tlačítko **zastavit** na kartě.

![Snímek obrazovky s kartou Logs v okně kontejnery](media/view-and-diagnose-containers/containers-logs.jpg)

Chcete-li vymazat protokoly, použijte tlačítko **Vymazat** na kartě **protokoly** .  Chcete-li získat všechny protokoly, použijte tlačítko **aktualizovat** .

> [!NOTE]
> Visual Studio automaticky přesměruje stdout a stderr do okna **výstupu** , takže kontejnery spouštěné ze sady Visual Studio (to znamená, že kontejnery v části **kontejnery řešení** ) nezobrazí protokoly na této kartě. místo toho použijte okno **výstup** .

## <a name="view-the-filesystem"></a>Zobrazit systém souborů

Na kartě **soubory** můžete zobrazit systém souborů kontejneru, včetně složky aplikace, která obsahuje váš projekt.

![Snímek obrazovky s kartou soubory v okně kontejnery](media/view-and-diagnose-containers/container-filesystem.png)

Chcete-li otevřít soubory v aplikaci Visual Studio, vyhledejte soubor a dvakrát na něj klikněte nebo klikněte pravým tlačítkem a vyberte možnost **otevřít**. Visual Studio otevře soubory v režimu jen pro čtení.

![Snímek obrazovky otevřeného souboru pro zobrazení v aplikaci Visual Studio](media/view-and-diagnose-containers/container-file-open.png)

Pomocí karty **soubory** můžete zobrazit protokoly aplikací, jako jsou protokoly IIS, konfigurační soubory a další soubory obsahu v systému souborů kontejneru.

## <a name="start-stop-and-remove-containers"></a>Spustit, zastavit a odebrat kontejnery

Ve výchozím nastavení okno **kontejnery** zobrazuje všechny kontejnery v počítači, který je nástrojem Docker. Pomocí tlačítek na panelu nástrojů můžete spustit, zastavit nebo odebrat (odstranit) kontejner, který již nechcete.  Tento seznam se dynamicky aktualizuje při vytváření nebo odebírání kontejnerů.

## <a name="next-steps"></a>Další kroky

Další informace o nástrojích kontejnerů, které jsou dostupné v aplikaci Visual Studio, najdete v tématu [Přehled nástrojů kontejnerů](overview.md).

## <a name="see-also"></a>Viz také:

[Vývoj kontejnerů v aplikaci Visual Studio](/visualstudio/containers)

[Tržiště rozšíření pro Visual Studio](https://marketplace.visualstudio.com/)
