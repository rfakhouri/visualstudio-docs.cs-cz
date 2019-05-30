---
title: Protokoly kontejneru, proměnné prostředí a přístup k systému souborů
description: Popisuje, jak Zlepšete svou schopnost ladění a Diagnostika aplikací založených na kontejnerech v sadě Visual Studio pomocí panelu nástrojů Pokud chcete zobrazit, co se děje uvnitř kontejnerů, které hostují vaši aplikaci.
author: ghogen
ms.author: ghogen
ms.topic: conceptual
ms.date: 05/06/2019
ms.technology: vs-azure
monikerRange: vs-2019
ms.openlocfilehash: b8e8e2db3f8f6e5aa60f3fa593caf017c349dca8
ms.sourcegitcommit: 117ece52507e86c957a5fd4f28d48a0057e1f581
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/28/2019
ms.locfileid: "66261197"
---
# <a name="how-to-view-and-diagnose-containers-in-visual-studio"></a>Postup zobrazení a Diagnostika kontejnerů v sadě Visual Studio

Můžete zobrazit, co se děje v kontejnerech, které hostují vaši aplikaci s použitím **kontejnery** okna. Pokud jste zvyklí pomocí příkazového řádku spouštět příkazy Dockeru k zobrazení a diagnostikovat, co se děje s kontejnery, toto okno poskytuje pohodlnější způsob pro monitorování kontejnerů, aniž byste museli opustit integrované vývojové prostředí sady Visual Studio.

> [!NOTE]
> Okno kontejneru je aktuálně k dispozici jako rozšíření ve verzi Preview, které je možné [Stáhnout](https://aka.ms/vscontainerspreview) pro Visual Studio 2019.

## <a name="prerequisites"></a>Požadavky

- [Desktop dockeru](https://hub.docker.com/editions/community/docker-ce-desktop-windows)
- Install [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)
- Nainstalujte [kontejnery okno rozšíření](https://aka.ms/vscontainerspreview)

## <a name="view-information-about-your-containers"></a>Zobrazení informací o kontejnerech

**Kontejnery** okno se automaticky otevře při spuštění kontejnerizované projektu .NET. Kdykoli zobrazit své kontejnery v sadě Visual Studio, použijte **Ctrl**+**Q** aktivovat hledání Visual Studio a zadejte `Containers` a zvolit první položku. Můžete také otevřít **kontejnery** okno v hlavní nabídce. Použijte cestu k nabídce **zobrazení** > **ostatní Windows** > **kontejnery**.  

![Snímek obrazovky prostředí karta v okně kontejnery](media/view-and-diagnose-containers/container-window.png)

Na levé straně se zobrazí seznam kontejnerů na místním počítači. Kontejnery přidružené k řešení se zobrazí pod **řešení kontejnerů**. Na pravé straně se zobrazí podokno s kartami pro **prostředí**, **porty**, **protokoly**, a **soubory**.

> [!TIP]
> Kde můžete snadno přizpůsobit **kontejnery** okna nástroje je ukotven v sadě Visual Studio. Zobrazit [přizpůsobení rozložení oken v sadě Visual Studio](/visualstudio/ide/customizing-window-layouts-in-visual-studio). Ve výchozím nastavení **kontejnery** je okno ukotveno s **Watch** okno při spuštění ladicího programu.

## <a name="view-environment-variables"></a>Zobrazit proměnné prostředí

**Prostředí** karta zobrazuje proměnné prostředí v kontejneru. Pro vaše aplikace kontejneru, můžete tyto proměnné můžete nastavit mnoha způsoby, například v souboru Dockerfile, v souboru .env nebo pomocí možnosti -e při spuštění kontejneru pomocí příkazu Docker.

![Snímek obrazovky prostředí karta v okně kontejnery](media/view-and-diagnose-containers/container-environment-vars.png)

> [!NOTE]
> Všechny změny do proměnných prostředí, se neprojeví v reálném čase. Také proměnné prostředí na této kartě jsou proměnné prostředí v kontejneru systému a neodrážejí vůči aplikaci lokální proměnné prostředí uživatele.

## <a name="view-port-mappings"></a>Zobrazení mapování portů

Na **porty** kartu, můžete zkontrolovat, které jsou v platnosti kontejneru mapování portů.

![Snímek obrazovky s porty karta v okně kontejnery](media/view-and-diagnose-containers/container-ports.png)

Známé porty jsou propojené, takže pokud není obsah dostupný na portu, můžete kliknout na odkaz k otevření prohlížeče.

## <a name="view-logs"></a>Zobrazení protokolů

**Protokoly** karta zobrazuje výsledky `docker logs` příkazu. Ve výchozím nastavení karta zobrazuje stdout a stderr datových proudů v kontejneru, ale můžete nakonfigurovat výstup. Podrobnosti najdete v tématu [protokolování Dockeru](https://docs.docker.com/config/containers/logging/).  Ve výchozím nastavení **protokoly** kartu datové proudy protokoly, ale který můžete zakázat výběrem **Zastavit** tlačítko na kartě.

![Snímek obrazovky s protokoly karta v okně kontejnery](media/view-and-diagnose-containers/containers-logs.jpg)

Pokud chcete vymazat protokoly, použijte **vymazat** tlačítko **protokoly** kartu.  Chcete-li získat všechny protokoly, použijte **aktualizovat** tlačítko.

> [!NOTE]
> Visual Studio automaticky přesměruje stdout a stderr do **výstup** okna, kontejnery spuštění ze sady Visual Studio (to znamená, že kontejnery v **řešení kontejnerů** části) nezobrazí protokoly na této kartě; použít **výstup** okno místo.

## <a name="view-the-filesystem"></a>Zobrazení systému souborů

Na **soubory** kartu, můžete zobrazit systému souborů kontejneru, včetně aplikace, která obsahuje projekt.

![Karta souborů snímků obrazovky v okně kontejnery](media/view-and-diagnose-containers/container-filesystem.png)

Pro otevření souborů v sadě Visual Studio, přejděte k souboru a dvojím kliknutím ho, nebo klikněte pravým tlačítkem myši a zvolte **otevřete**. Visual Studio otevře soubory v režimu jen pro čtení.

![Snímek obrazovky se soubor otevřen pro zobrazení v sadě Visual Studio](media/view-and-diagnose-containers/container-file-open.png)

Použití **soubory** kartu, můžete zobrazit protokoly aplikací, jako jsou protokoly služby IIS, konfigurační soubory a další soubory obsahu v systému souborů vašeho kontejneru.

## <a name="start-stop-and-remove-containers"></a>Spuštění, zastavení a odstranění kontejnerů

Ve výchozím nastavení **kontejnery** okno zobrazuje všechny kontejnery, které v počítači, který spravuje Dockeru. Můžete použít tlačítka Spustit, zastavit nebo odstranit (delete) kontejner už nechcete.  Tento seznam se aktualizuje dynamicky, jako jsou kontejnery vytvořené nebo odebrat.

## <a name="next-steps"></a>Další kroky

Další informace o kontejneru nástrojů dostupných v sadě Visual Studio najdete [přehled nástrojů pro kontejner](overview.md).

## <a name="see-also"></a>Viz také:

[Kontejner vývoje v sadě Visual Studio](/visualstudio/containers)

[Extensions Marketplace for Visual Studio](https://marketplace.visualstudio.com/)
