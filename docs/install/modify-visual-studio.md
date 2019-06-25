---
title: Úpravy sady Visual Studio
titleSuffix: ''
description: Zjistěte, jak upravit sadu Visual Studio, krok za krokem.
ms.custom: H1Hack27Feb2017,seodec18
ms.date: 06/25/2019
ms.topic: conceptual
helpviewer_keywords:
- modify Visual Studio
- change visual studio
- changing Visual Studio
- customize Visual Studio
ms.assetid: 3399ea7b-a291-4a9e-80a1-b861a21afa1d
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 287ad470a94689b92cacb443c2b5f88eb30f5a70
ms.sourcegitcommit: 01c3c9dcade5d913bde2c7efa8c931a7b04e6cd0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2019
ms.locfileid: "67365405"
---
# <a name="modify-visual-studio-by-adding-or-removing-workloads-and-components"></a>Upravit sadu Visual Studio přidáním nebo odebráním úlohy a komponenty

::: moniker range="vs-2019"

Je snadné úpravy sady Visual Studio tak, že obsahují pouze co chcete, kdykoli budete chtít. Uděláte to tak, otevřete instalačního programu sady Visual Studio k přidání nebo odebrání úlohy a komponenty.

::: moniker-end

::: moniker range="vs-2017"

Nejenže jsme zjednodušili si můžete přizpůsobit Visual Studio tak, aby odpovídaly úkoly, které chcete dosáhnout, jsme také snadněji příliš přizpůsobení sady Visual Studio. Uděláte to tak, začněte nový instalační program sady Visual Studio a proveďte požadované změny.

::: moniker-end

Tady je způsob.

## <a name="modify-workloads"></a>Upravit úlohy

 Úlohy obsahují funkce, které potřebujete pro programovací jazyk nebo platformu, kterou používáte. Upravit sadu Visual Studio tak, aby podporoval práce, kterou chcete provést, pokud chcete to udělat pomocí úlohy.

>[!IMPORTANT]
>Instalovat, aktualizovat nebo upravit sadu Visual Studio, musíte se přihlásit pomocí účtu, který má oprávnění správce. Další informace najdete v tématu [uživatelská oprávnění a sada Visual Studio](../ide/user-permissions-and-visual-studio.md).

>[!TIP]
> Následující postup předpokládá, že máte připojení k Internetu. Další informace o tom, jak upravit dříve vytvořenou [offline instalaci](create-an-offline-installation-of-visual-studio.md) sady Visual Studio, najdete v článku [řízení aktualizací nasazení sady Visual Studio založené na síti](controlling-updates-to-visual-studio-deployments.md) stránky.

::: moniker range="vs-2017"

1. Najdete instalační program sady Visual Studio v počítači.

     Například v počítači se systémem Windows 10, vyberte **Start**a poté přejděte k označení **V**, kde je hodnota uvedena jako **instalační program sady Visual Studio**.

     ![Instalační program sady Visual Studio](media/vs2017-locate-the-visual-studio-installer.PNG "vyhledejte instalační program sady Microsoft Visual Studio")

     >[!NOTE]
     >V některých počítačích může instalační program sady Visual Studio uvedené pod písmenem **"M"** jako **instalační program Visual Studio**.<br/><br/> Alternativně můžete najít instalační program sady Visual Studio v následujícím umístění: `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

1. Klikněte nebo klepněte sem a můžete spustit instalační program a klikněte na tlačítko **změnit**.

     ![Spustit nebo upravit sadu Visual Studio](media/modify-visual-studio.png "upravit Visual Studio 2017")

     Pokud už máte čekající aktualizace, je tlačítko Upravit na jiném místě. Tímto způsobem můžete upravit sady Visual Studio bez aktualizace, rozhodnete tak učinit. Klikněte na tlačítko **Další**a klikněte na tlačítko **změnit**.

     ![Aktualizovat nebo upravit sadu Visual Studio](media/modify-or-update-visual-studio.png "aktualizace nebo změna sady Visual Studio 2017")

1. Z **úlohy** obrazovky, vyberte nebo zrušte výběr úlohy, které chcete nainstalovat nebo odinstalovat.

    ![Visual Studio 2017 instalačním programu](media/vs2017-modify-workloads.PNG "zvolte úlohu v sadě Visual Studio 2017")

1. Zvolte **změnit** znovu.

1. Po instalaci nové úlohy a komponenty, zvolte **spuštění**.

::: moniker-end

::: moniker range="vs-2019"

1. Najdete instalační program sady Visual Studio v počítači.

     Například v počítači se systémem Windows 10, vyberte **Start**a poté přejděte k označení **V**, kde je hodnota uvedena jako **instalační program sady Visual Studio**.

     ![Spusťte instalační program sady Visual Studio](media/vs2019-visual-studio-installer.png "spusťte instalační program sady Visual Studio")

     > [!NOTE]
     > Instalační program sady Visual Studio můžete najít také v následujícím umístění:
     >
     > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

    Budete muset aktualizovat instalační program pokračovat. Pokud ano, postupujte podle pokynů.

1. V instalačním programu, vyhledejte edici sady Visual Studio, který jste nainstalovali a klikněte na tlačítko **změnit**.

     ![Aktualizovat nebo upravit sadu Visual Studio](media/vs-2019/vs-installer-modify.png "aktualizace nebo změna sady Visual Studio 2017")

1. V **úlohy** kartu, vyberte nebo zrušte výběr úlohy, které chcete nainstalovat nebo odinstalovat.

    ![Dialogové okno nastavení aplikace Visual Studio 2019](media/vs-2019/vs-installer-modify-workloads.png "zvolte úlohu v aplikaci Visual Studio 2019")

1. Zvolte, jestli chcete přijmout výchozí nastavení **nainstalovat při stahování** možnost nebo **vše stáhnout, potom nainstalovat** možnost.

    ![Možnosti instalace aplikace Visual Studio 2019](media/vs-2019/vs-installer-choose-install-or-download.png "se rozhodnete nainstalovat při stahování nebo nejdřív stáhnout a nainstalovat později")

    "Vše stáhnout, potom nainstalovat" možnost je užitečný, pokud budete chtít nejdřív stáhnout a nainstalovat později.

1. Zvolte **upravit**.

1. Po instalaci nové úlohy a komponenty, zvolte **spuštění** z instalačního programu sady Visual Studio.

::: moniker-end

## <a name="modify-individual-components"></a>Upravit jednotlivé komponenty

Pokud nechcete nainstalovat úloh k přizpůsobení instalace sady Visual Studio, zvolte **jednotlivé komponenty** kartu z instalačního programu sady Visual Studio, vyberte, co chcete a pak postupujte podle pokynů.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Aktualizace sady Visual Studio](update-visual-studio.md)
* [Aktualizace síťové instalace sady Visual Studio](update-a-network-installation-of-visual-studio.md)
* [Aktualizace sady Visual Studio na směrný plán údržby](update-servicing-baseline.md)
* [Řízení aktualizací nasazení sady Visual Studio založené na síti](controlling-updates-to-visual-studio-deployments.md)
* [Odinstalace sady Visual Studio](uninstall-visual-studio.md)
