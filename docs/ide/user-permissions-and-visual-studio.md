---
title: Spustit jako správce
ms.date: 06/05/2018
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, user permissions
- user permissions
- administrative privileges
- permissions
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 97ecddfa317eb522a8ce29a53482df5581912dad
ms.sourcegitcommit: 673b9364fc9a96b027662dcb4cf5d61cab60ef11
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/21/2019
ms.locfileid: "69891236"
---
# <a name="user-permissions-and-visual-studio"></a>Uživatelská oprávnění a Visual Studio

Z důvodu zabezpečení byste měli spustit sadu Visual Studio jako normálního uživatele, kdykoli to bude možné.

> [!WARNING]
> Je třeba zajistit, aby nebylo kompilováno, spouštěno nebo laděno jakékoli řešení systému Visual Studio, které nebylo získáno od důvěryhodné osoby nebo z důvěryhodného zdroje.

V integrovaném vývojovém prostředí sady Visual Studio můžete udělat skoro všechno jako normální uživatel. K dokončení následujících úloh potřebujete oprávnění správce:

|Oblast|Úloha|Další informace|
|----------|----------| - |
|Instalace|Nainstalujte Visual Studio.|[Instalace sady Visual Studio](../install/install-visual-studio.md)|
||Instalace, aktualizace nebo odebrání místního obsahu aplikace Help.|[Nainstalovat a spravovat místní obsah obsahu Help](../help-viewer/install-manage-local-content.md)|
|Sada nástrojů|Přidání klasických ovládacích prvků modelu COM do **sady nástrojů**.|[Panel nástrojů](../ide/reference/toolbox.md)|
|Sestavování|Použijte události po sestavení, které registrují komponentu.|[Porozumění vlastním postupům sestavení a událostem sestavení](/cpp/build/understanding-custom-build-steps-and-build-events)|
||Při sestavování C++ projektů zahrňte krok registrace.||
|Ladění|Ladění aplikací, které běží se zvýšenými oprávněními.|[Nastavení a příprava ladicího programu](../debugger/debugger-settings-and-preparation.md)|
||Ladění aplikací, které běží pod jiným uživatelským účtem, jako jsou ASP.NET websites.|[Ladění aplikací ASP.NET a AJAX](../debugger/how-to-enable-debugging-for-aspnet-applications.md)|
||Ladění v zóně pro aplikace prohlížeče XAML (XBAP)|[Hostitel WPF (PresentationHost. exe)](/dotnet/framework/wpf/app-development/wpf-host-presentationhost-exe)|
||Použijte emulátor k ladění projektů cloudových služeb pro Microsoft Azure.|[Ladění cloudové služby v aplikaci Visual Studio](/azure/vs-azure-tools-debug-cloud-services-virtual-machines)|
||Nakonfigurujte bránu firewall pro vzdálené ladění.|[Vzdálené ladění](../debugger/remote-debugging.md)|
|Nástroje pro měření výkonu|Připojení k aplikaci se zvýšenými oprávněními.|[Příručka pro začátečníky k profilaci výkonu](../profiling/beginners-guide-to-performance-profiling.md)|
||Použijte Profiler GPU.|[Profilace GPU](../profiling/gpu-usage.md)|
|Nasazení|Nasazení webové aplikace do Internetová informační služba (IIS) na místním počítači.|[Nasazení webové aplikace v ASP.NET pomocí sady Visual Studio](/aspnet/web-forms/overview/older-versions-getting-started/deployment-to-a-hosting-provider/)|

## <a name="run-visual-studio-as-an-administrator"></a>Spustit Visual Studio jako správce

Pokud potřebujete spustit Visual Studio jako správce, postupujte podle těchto kroků a otevřete integrované vývojové prostředí (IDE):

> [!NOTE]
> Tyto pokyny jsou pro Windows 10. Jsou podobné pro jiné verze systému Windows.

::: moniker range="vs-2017"

1. Otevřete nabídku **Start** a přejděte na Visual Studio 2017.

1. V **aplikaci Visual Studio 2017**pravým tlačítkem nebo v místní nabídce vyberte **Další** > **Spustit jako správce**.

   Při spuštění sady Visual Studio **(správce)** se zobrazí za názvem produktu v záhlaví programu.

::: moniker-end

::: moniker range=">=vs-2019"

1. Otevřete nabídku **Start** a přejděte na Visual Studio 2019.

1. V **aplikaci Visual Studio 2019**pravým tlačítkem nebo v místní nabídce vyberte **Další** > **Spustit jako správce**.

   Při spuštění sady Visual Studio **(správce)** se zobrazí za názvem produktu v záhlaví programu.

::: moniker-end

Můžete také upravit zástupce aplikace tak, aby se vždy spouštěl s oprávněními správce.

## <a name="see-also"></a>Viz také:

- [Port, migrace a upgrade projektů sady Visual Studio](../porting/port-migrate-and-upgrade-visual-studio-projects.md)
- [Instalace sady Visual Studio](../install/install-visual-studio.md)