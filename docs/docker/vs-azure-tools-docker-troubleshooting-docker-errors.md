---
title: Řešení potíží s chybami klienta Docker ve Windows | Dokumentace Microsoftu
description: Řešení problémů, které zaznamenáte při používání sady Visual Studio k vytvoření a nasazení webové aplikace do Docker ve Windows pomocí sady Visual Studio 2017.
services: azure-container-service
author: devinb
manager: douge
ms.custom: seodec18
ms.assetid: 346f70b9-7b52-4688-a8e8-8f53869618d3
ms.service: multiple
ms.devlang: dotnet
ms.topic: conceptual
ms.workload: multiple
ms.date: 10/13/2017
ms.author: devinb
ms.openlocfilehash: 0551c67ee86f0d63655c584905a5a6280f450901
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/24/2019
ms.locfileid: "54868502"
---
# <a name="troubleshoot-visual-studio-2017-development-with-docker"></a>Řešení potíží při vývoji v sadě Visual Studio 2017 pomocí Dockeru

Když pracujete se sadou Visual Studio Tools for Docker, může dojít k potížím při sestavování nebo ladění aplikace. Níže jsou některé běžné kroků pro řešení potíží.

## <a name="volume-sharing-is-not-enabled-enable-volume-sharing-in-the-docker-ce-for-windows-settings--linux-containers-only"></a>Sdílení svazků není povolené. Povolte sdílení svazků v nastavení Dockeru CE pro Windows (pouze pro kontejnery Linuxu)

K vyřešení tohoto problému:

1. Klikněte pravým tlačítkem na **Docker pro Windows** v oznamovací oblasti a pak vyberte **nastavení**.
1. Vyberte **sdílené jednotky** a sdílené složky systémové jednotce spolu s na jednotku, ve které se nachází projektu.

> [!NOTE]
> Pokud se zdá, že sdílené soubory, můžete stále chcete-li znovu povolit sdílení svazků, klikněte na odkaz "Resetovat přihlašovací údaje …" v dolní části dialogového okna. Chcete-li pokračovat po resetování přihlašovacích údajů, budete muset restartovat Visual Studio.

![sdílené jednotky](media/vs-azure-tools-docker-troubleshooting-docker-errors/shareddrives.png)

> [!TIP]
> Visual Studio 2017 verze 15.6 a vyšší výzvu, při **sdílené jednotky** nejsou nakonfigurované.

### <a name="container-type"></a>Typ kontejneru

Při přidávání podpory Docker do projektu, zvolte Windows nebo Linuxem kontejneru. Hostitele Docker musí běžet stejný typ kontejneru. Chcete-li změnit typ kontejneru v běžící instanci Dockeru, klikněte pravým tlačítkem na ikonu Dockeru na hlavním panelu a vyberte **přepnout na kontejnery Windows...**  nebo **přepnout na kontejnery Linuxu...** .

## <a name="unable-to-start-debugging"></a>Nelze spustit ladění

Jedním z důvodů může souviset s tím, že komponenty zastaralé ladění ve složce profilu uživatele. Spusťte následující příkazy k odebrání těchto složek tak, aby se stáhnou nejnovější ladění komponenty na příští relaci ladění.

- del %userprofile%\vsdbg
- del %userprofile%\onecoremsvsmon

## <a name="errors-specific-to-networking-when-debugging-your-application"></a>Chyby specifické pro sítě při ladění aplikace

Pokuste se spustit skript ke stažení z [sítě hostitele kontejneru vyčištění](https://github.com/MicrosoftDocs/Virtualization-Documentation/tree/master/windows-server-container-tools/CleanupContainerHostNetworking), která obnoví komponenty související se sítí na hostitelském počítači.

## <a name="mounts-denied"></a>Připojení byl odepřen

Při použití Dockeru pro macOS, pravděpodobně dojde k chybě odkazující na složku /usr/local/share/dotnet/sdk/NuGetFallbackFolder. Přidat složku na kartě Sdílení souborů v Dockeru

## <a name="microsoftdockertools-github-repo"></a>Úložiště GitHub Microsoft/DockerTools

V případě jiných problémů dojde, naleznete v tématu [Microsoft/DockerTools](https://github.com/microsoft/dockertools/issues) problémy.