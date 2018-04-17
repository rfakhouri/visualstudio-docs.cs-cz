---
title: Nastavení vzdálené služby R v systému Linux
description: Postup nastavení vzdálené služby R na Ubuntu a subsystému Windows pro Linux.
ms.custom: ''
ms.date: 12/04/2017
ms.technology:
- devlang-r
dev_langs:
- R
ms.topic: conceptual
author: kraigb
ms.author: kraigb
ms.reviewer: karthiknadig
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: ea41a192a5a39c0245bcb6d67f45331b7b021116
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="remote-r-service-for-linux"></a>Služba vzdálené R pro Linux

Vzdálená služba R pro Linux je aktuálně zabalené jako démon rtvs. Démon je podporované a otestovat Ubuntu 16.04, 16.10 plochy LTS, serveru a subsystému Windows pro spuštění Ubuntu Linux. Hromadným Tento článek obsahuje pokyny pro nastavení vzdálené služby R na tyto různými systémy.

Po konfiguraci vzdáleného počítače, bude následující postup k této službě připojit R nástrojů pro Visual Studio (RTVS):

1. Vyberte **R nástroje > Windows > pracovní prostory** otevřete **pracovních prostorů** okno.
1. Vyberte **přidat připojení**.
1. Zadejte název připojení a zadejte jeho adresu URL, jako třeba `https://localhost:5444` (subsystému Windows pro Linux) nebo `https://public-ip:5444` (kontejner Azure). Vyberte **Uložit** při dokončení.
1. Vyberte ikonu připojení nebo dvakrát klikněte na položku připojení.
1. Zadejte přihlašovací údaje. Uživatelské jméno musí mít předponu `<<unix>>\` jako v `<<unix>>\ruser1` (podle potřeby pro všechna připojení ke vzdáleným počítačům Linux).
1. Pokud používáte certifikát podepsaný svým držitelem, může se zobrazit upozornění. Zpráva obsahuje pokyny k odstranění upozornění.

## <a name="setting-up-remote-r-service"></a>Nastavení vzdálené služby R

Tato část popisuje následující možnosti:

- [Fyzický počítač Ubuntu](#physical-ubuntu-computer)
- [Ubuntu Server virtuálního počítače nebo vědecké zpracování dat virtuálních počítačů v Azure](#ubuntu-server-vm-or-data-science-vm-on-azure)
- [Místní nebo vzdálené kontejner Docker (čistá sestavení)](#local-or-remote-docker-container-clean-build)
- [Kontejner systémem Azure kontejner instancí](#container-running-on-azure-container-instances)

V každém případě vzdálený počítač musí mít jednu z následujících R překladače nainstalován:

- [Otevřete Microsoft R](https://mran.microsoft.com/open/)
- [CRAN r. pro Windows](https://cran.r-project.org/bin/linux/ubuntu/)

### <a name="physical-ubuntu-computer"></a>Fyzický počítač Ubuntu

1. Po přihlášení do počítače, stáhněte tarball rtvs démon:

    ```bash
    wget -O rtvs-daemon.tar.gz https://aka.ms/r-remote-services-linux-binary-current
    tar -xvzf rtvs-daemon.tar.gz
    ```

1. Spusťte instalační skript:

    ```bash
    sudo ./rtvs-install
    ```

    Pro tichou automatizaci použít `sudo ./rtvs-install -s`.

1. Povolení a spuštění služby:

    ```bash
    sudo systemctl enable rtvsd
    sudo systemctl start rtvsd
    ```

1. Nakonfigurujte certifikát protokolu SSL (povinné pro produkční prostředí). Ve výchozím nastavení, používá rtvs démon `ssl-cert-snakeoil.pem` a `ssl-cert-snakeoil.pem` vygenerované `ssl-cert` balíčku. Během instalace, jejich zkombinované do `ssl-cert-snakeoil.pfx`. Pro produkční účely používejte certifikát SSL získali od správce. Certifikát SSL můžete nakonfigurovat tím, že poskytuje `.pfx` souboru a volitelné import heslo v: `/etc/rtvs/rtvsd.config.json`.

1. (Volitelné) Zkontrolujte, zda je spuštěna služba:

    ```bash
    ps -A -f | grep rtvsd
    ```

    Pokud nevidíte proces spuštěný v uživatelské jméno `rtvssvc`. Spusťte ji pomocí následujícího příkazu:

    ```bash
    sudo systemctl start rtvsd
    ```

1. Další konfigurace démona rtvs najdete v tématu `man rtvsd`.

### <a name="ubuntu-server-vm-or-data-science-vm-on-azure"></a>Ubuntu Server virtuálního počítače nebo vědecké zpracování dat virtuálních počítačů v Azure

#### <a name="create-a-vm"></a>Vytvoření virtuálního počítače

1. Přihlaste se k [portál Azure](https://portal.azure.com).
1. Přejděte na virtuální počítače a pak vyberte **přidat**.
1. V seznamu dostupných imagí virtuálních počítačů vyhledejte a vyberte jednu z následujících akcí:
    - Ubuntu Server: `Ubuntu Server 16.04 LTS`
    - Vědecké zpracování dat virtuálních počítačů: `Linux Data Science` (viz [datové vědy virtuální počítače](https://azure.microsoft.com/services/virtual-machines/data-science-virtual-machines/) podrobnosti)
1. Nastavit model nasazení na `Resource manager` a vyberte **vytvořit**.
1. Zvolte název pro virtuální počítač, zadejte uživatelské jméno a heslo (je vyžadováno heslo, jako SSH není podporována veřejného klíče přihlášení).
1. Proveďte další požadované změny do konfigurace virtuálního počítače.
1. Zvolte velikost virtuálního počítače, ověřte konfiguraci a vyberte **vytvořit**. Po vytvoření virtuálního počítače, přejděte k další části.

#### <a name="configure-the-vm"></a>Konfigurace virtuálního počítače

1. V modulu VM **sítě** přidejte 5444 jako Povolené portu pro příchozí spojení. Pokud chcete používat jiný port, změnit nastavení v konfiguračním souboru démon RTVS (`/etc/rtvs/rtvsd.config.json`).
1. (Volitelné) Nastavení názvu DNS; Můžete také použít adresu IP.
1. Připojte k virtuálnímu počítači pomocí SSH klienta, jako je například PuTTY pro systém WIndows.
1. Postupujte podle pokynů [Ubuntu fyzické počítače](#physical-ubuntu-computer) výše.

### <a name="windows-subsystem-for-linux-wsl"></a>Subsystém Windows pro Linux (WSL)

1. Postupujte podle pokynů instalace WSL pro buď [Windows 10](https://msdn.microsoft.com/commandline/wsl/install-win10) nebo [systému Windows Server](https://msdn.microsoft.com/en-us/commandline/wsl/install-on-server).
1. V systému Windows spusťte bash a postupujte podle předchozích pokynů [Ubuntu fyzické počítače](#physical-ubuntu-computer) s jednou výjimkou. Krok 3, spusťte službu pomocí příkazu `rtvsd`místo protože WSL aktuálně nepodporuje rozhraní systemd/systemctl.

### <a name="local-or-remote-docker-container-clean-build"></a>Místní nebo vzdálené kontejner Docker (čistá sestavení)

1. Vytvořte soubor Docker s níže, obsah, který se nainstaluje služba démona vzdálené R a nejnovější verzi R. **Poznámka**: Tento skript vytvoří uživatele názvem "ruser1" s heslem "foobar", který lze upravit podle potřeby v poslední dva `RUN` příkazy.

    ```docker
    FROM ubuntu:16.04

    ARG DEBIAN_FRONTEND=noninteractive

    RUN apt-get update \
     && apt-get install -y software-properties-common python-software-properties \
     && apt-get install -y apt-transport-https \
     && rm -rf /var/lib/apt/lists/*

    RUN sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list' \
     && apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 417A0893 \
     && sh -c 'echo "deb https://cran.revolutionanalytics.com/bin/linux/ubuntu xenial/" > /etc/apt/sources.list.d/cran-r.list' \
     && apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E084DAB9 \
     && rm -rf /var/lib/apt/lists/* \
     && apt-get clean

    RUN apt-get update --fix-missing && apt-get update \
     && apt-get install -y dotnet-dev-1.0.4 libexplain51 libzip4 libc6 git lshw ssl-cert wget \
     && rm -rf /var/lib/apt/lists/*

    # install R
    RUN apt-get update && apt-get install -y r-base-dev
    RUN apt upgrade -y

    # install rtvs-daemon
    RUN wget -O rtvs-daemon.tar.gz https://aka.ms/r-remote-services-linux-binary-current && tar -xvzf rtvs-daemon.tar.gz && ./rtvs-install -s

    RUN useradd --create-home ruser1
    RUN echo "ruser1:foobar" | chpasswd

    EXPOSE 5444
    ```

1. Sestavte a spusťte soubor docker:

    ```bash
    docker build -t myrimage .
    docker run -p 5444:5444 myrimage rtvsd
    ```

1. Pro připojení k obsahuje z RTVS, použijte `https://localhost:5444` jako cestu, uživatelské jméno `<<unix>>\ruser1`a heslo `foobar`. Pokud kontejneru je spuštěn ve vzdáleném počítači, použijte `https://remote-host-name:5444` cestou místo. Port může změnit aktualizace `/etc/rtvs/rtvsd.config.json`.

### <a name="container-running-on-azure-container-instances"></a>Kontejner systémem Azure kontejner instancí

1. Postupujte podle pokynů v [místního nebo vzdáleného kontejner Docker (čistá sestavení)](#local-or-remote-docker-container-clean-build) na vytvoření bitové kopie.
1. Nabízená kontejner Docker hub nebo kontejneru úložiště Azure.
1. Spuštění rozhraní příkazového řádku Azure a přihlaste se pomocí `az login` příkaz.
1. Použití `az container create` příkaz pro vytvoření kontejneru, pomocí `--command-line "rtvsd"` Pokud jste nenastavili kontejneru ke spuštění `rtvsd` jako `systemd` služby. V níže uvedeném příkazu musí být na úložiště Docker hub bitovou kopii. Kontejner úložiště Azure můžete taky přidáním kontejneru úložiště přihlašovacích údajů argumentů na příkazový řádek.

    ```bash
    az container create --image myimage:latest --name myaz-container --resource-group myaz-container-res --ip-address public --port 5444 --cpu 2 --memory 4 --command-line "rtvsd"
    ```
1. Použití `az container list` příkaz a zkontrolujte stav. Vyhledejte `provisioningState`: `Succeeded`.
1. Pokud zřizování byly úspěšné, můžete teď připojit ke kontejneru. Vyhledejte v veřejnou IP adresu, `ipAddress` pole, které používáte s přihlašovacími údaji v souboru docker připojit ke kontejneru z RTVS.

