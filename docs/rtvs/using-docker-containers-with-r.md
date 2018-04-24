---
title: R a Docker kontejnery
description: Jak nastavit Docker kontejnery pro R a připojit se k nim pomocí sady Visual Studio.
ms.date: 12/04/2017
ms.prod: visual-studio-dev15
ms.technology: vs-rtvs
ms.topic: conceptual
author: kraigb
ms.author: kraigb
ms.reviewer: karthiknadig
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: d7034476e3346e4f3d4e24713a62920487845440
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="using-docker-containers-with-r-tools-for-visual-studio"></a>Pomocí Docker kontejnery s R Tools pro Visual Studio

R nástrojů pro Visual Studio (RTVS) verze 1.3 +, spolu s instalace [Docker pro systém Windows](https://www.docker.com/docker-windows), podporuje práci s kontejnery Docker.

## <a name="creating-a-container"></a>Vytvoření kontejneru

1. Vyberte **kontejnery...**  tlačítko v pravém horním rohu **pracovních prostorů** okno (**R nástroje > Windows > pracovní prostory**). Okno vás upozorní, pokud nemáte Docker pro systém Windows nainstalován a obsahuje odkaz pro stahování. Instalace Docker může vyžadovat restartování počítače.

    ![Okno pracovní prostory v R Tools pro Visual Studio (VS2017) pomocí příkazu kontejnery](media/container-workspaces-window.png)

1. V **kontejnery** vyberte **vytvořit**:

    ![Vytvoření příkazu v okně kontejnery](media/containers-window-create.png)

1. Dokončení požadované informace v dialogovém okně a vyberte **vytvořit**. Přihlašovací údaje, které zadáte, se taky používají k vytvoření účtu v systému Linux, pomocí kterého se přihlásit později.

    ![Zadáte název kontejneru a přihlašovacích údajů při vytváření kontejneru](media/containers-window-create-fill.png)

1. To může trvat nějakou dobu RTVS vytvořit bitovou kopii. **Výstup** oken v sadě Visual Studio zobrazí průběhu, ale může se nesmí být provádění mnohem během zdlouhavé image stáhne; buďte připraveni počkejte. Jakmile je integrovaný bitovou kopii, RTVS spustí kontejneru a zobrazí se v **kontejneru** okno. Ovládací prvky vpravo zastavení, odeberte, nebo restartujte kontejneru.

    ![Kontejnery okno zobrazující kontejner dokončené](media/containers-window-created.png)

## <a name="connecting-to-a-container"></a>Připojení do kontejneru

1. **Místní spuštění kontejnery** části **pracovních prostorů** kontejnery spuštěn démon RTVS na portu 5444 zobrazí okno. (Viz [vzdáleného R Server pro Linux](setting-up-remote-r-service-on-linux.md) podrobnosti o konfiguraci démona.)

    ![Pracovní prostory okno zobrazuje dostupné kontejnery](media/workspaces-window-running-containers.png)

1. Pro připojení do kontejneru, dvakrát klikněte na název kontejneru nebo kliknutím na tlačítko Předat dál šipku záhlavím vpravo. Při připojení, uvidíte **R interaktivní** okno (najdete v části [práce s R interaktivních okna](interactive-repl-for-r-in-visual-studio.md)):

    ![Pracovní prostory a okna REPL otevřen pro kontejner](media/workspaces-window-container-connected.png)

## <a name="using-custom-built-images"></a>Používat uživatelské Image

RTVS zjistí a umožňuje správu kontejnery, které jsou vytvořené pomocí uživatelské Image, jako jsou popsané v následující soubor docker microsoft/rtvs image. Základní image použít se zde má rtvs démon, R 3.4.2 a běžné balíčky R předem nainstalované. **Poznámka:**: Změňte uživatelské jméno a heslo, které jsou zobrazeny zde podle potřeby.

```docker
FROM microsoft/rtvs:1.3-ub1604-r3.4.2
RUN useradd --create-home ruser1
RUN echo "ruser1:foobar" | chpasswd

#Install additional R packages. You may have to install OS dependencies, see package info or error messages during build.
#RUN Rscript --vanilla -e "install.packages(c('AzureML','wordcloud'), repos = 'http://cran.us.r-project.org');"
```

Použijte následující příkaz k vytvoření bitové kopie, změna názvu kontejneru ( `--name` argument) podle potřeby:

```bash
docker build -t my-rtvs-image:latest .
docker run -p 6056:5444 --name my-rtvs-container my-rtvs-image:latest rtvsd
```

`-p 6056:5444` Argument mapy portu 6056 interní port 5444, která RTVS využívá ke zjištění rtvs démona. Každý kontejner, který zveřejňuje port kontejneru 5444, je uvedena ve **pracovních prostorů** okno. Pak můžete použít **pracovních prostorů** okna připojit ke kontejneru pomocí `<<unix>>\ruser1` jako uživatelské jméno a "foobar" jako heslo, pokud jste zadali v souboru docker jiná pověření.
