---
title: Úpravy sady Visual Studio
titleSuffix: ''
description: Zjistěte, jak upravit sadu Visual Studio, krok za krokem.
ms.custom: H1Hack27Feb2017,seodec18
ms.date: 07/31/2019
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
ms.openlocfilehash: 593af04805870fcbd505d4004d9984d2a806f7a3
ms.sourcegitcommit: c90a998716b3dfa614dedc61a1bea515364efbec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/23/2019
ms.locfileid: "70000931"
---
# <a name="modify-visual-studio-by-adding-or-removing-workloads-and-components"></a>Změna sady Visual Studio přidáním nebo odebráním úloh a součástí

::: moniker range="vs-2019"

Aplikaci Visual Studio můžete snadno upravit tak, aby obsahovala pouze to, co chcete, pokud chcete. Provedete to tak, že otevřete Instalační program pro Visual Studio a přidáte nebo odeberete úlohy a součásti.

::: moniker-end

::: moniker range="vs-2017"

Nejenže jsme zjednodušili si můžete přizpůsobit Visual Studio tak, aby odpovídaly úkoly, které chcete dosáhnout, jsme také snadněji příliš přizpůsobení sady Visual Studio. Uděláte to tak, začněte nový instalační program sady Visual Studio a proveďte požadované změny.

::: moniker-end

Tady je způsob.

## <a name="modify-workloads"></a>Upravit úlohy

 Úlohy obsahují funkce, které potřebujete pro programovací jazyk nebo platformu, kterou používáte. Upravit sadu Visual Studio tak, aby podporoval práce, kterou chcete provést, pokud chcete to udělat pomocí úlohy.

>[!IMPORTANT]
>Instalovat, aktualizovat nebo upravit sadu Visual Studio, musíte se přihlásit pomocí účtu, který má oprávnění správce. Další informace naleznete v tématu [uživatelská oprávnění a aplikace Visual Studio](../ide/user-permissions-and-visual-studio.md).

>[!TIP]
> Následující postup předpokládá, že máte připojení k Internetu. Další informace o tom, jak upravit dříve vytvořenou instalaci sady Visual Studio v [režimu offline](create-an-offline-installation-of-visual-studio.md) , naleznete na stránce [aktualizace ovládacího prvku pro síťová nasazení sady Visual Studio](controlling-updates-to-visual-studio-deployments.md) .

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

     ![Otevřete instalační program pro Visual Studio z Windows](media/vs-2019/vs-installer-windows-start.png "Otevřete instalační program pro Visual Studio")

     > [!NOTE]
     > Instalační program pro Visual Studio můžete najít také v následujícím umístění:
     >
     > `C:\Program Files (x86)\Microsoft Visual Studio\Installer\vs_installer.exe`

    Než budete pokračovat, bude pravděpodobně nutné aktualizovat instalační program. Pokud ano, postupujte podle pokynů.

1. V instalačním programu vyhledejte edici sady Visual Studio, kterou jste nainstalovali, a pak zvolte možnost **Upravit**.

     ![Aktualizace nebo změna sady Visual Studio](media/vs-2019/vs-installer-modify.png "Aktualizace nebo změna sady Visual Studio 2019")

1. Na kartě **úlohy** vyberte nebo zrušte výběr úloh, které chcete nainstalovat nebo odinstalovat.

    ![Dialogové okno instalace sady Visual Studio 2019](media/vs-2019/vs-installer-modify-workloads.png "Výběr úlohy v aplikaci Visual Studio 2019")

1. Zvolte, jestli chcete **při stahování** přijmout výchozí instalaci, nebo možnost **Stáhnout vše a pak nainstalovat** .

    ![Možnosti instalace sady Visual Studio 2019](media/vs-2019/vs-installer-choose-install-or-download.png "Zvolit instalaci během stahování nebo ke stažení a pozdější instalaci")

    Možnost stáhnout vše a pak nainstalovat je užitečná, pokud si chcete stáhnout nejdřív a pak nainstalovat později.

1. Klikněte na tlačítko **Upravit**.

1. Až budou nové úlohy a komponenty nainstalované, vyberte **Spustit** z instalační program pro Visual Studio.

::: moniker-end

## <a name="modify-individual-components"></a>Upravit jednotlivé komponenty

Pokud nechcete instalovat úlohy pro přizpůsobení instalace sady Visual Studio, zvolte kartu **jednotlivé komponenty** z instalační program pro Visual Studio, vyberte, co chcete, a pak postupujte podle pokynů.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Aktualizace sady Visual Studio](update-visual-studio.md)
* [Aktualizace síťové instalace sady Visual Studio](update-a-network-installation-of-visual-studio.md)
* [Aktualizace sady Visual Studio na standardních hodnotách údržby](update-servicing-baseline.md)
* [Řízení aktualizací nasazení sady Visual Studio založené na síti](controlling-updates-to-visual-studio-deployments.md)
* [ID součástí & úloh](workload-and-component-ids.md)
* [Odinstalace sady Visual Studio](uninstall-visual-studio.md)
