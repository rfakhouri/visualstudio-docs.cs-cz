---
title: Spustit jako správce
ms.date: 06/05/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, user permissions
- user permissions
- administrative privileges
- permissions
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 89ba7338645ab6cc421716832a3d6f424bb57dfc
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/07/2018
ms.locfileid: "34844388"
---
# <a name="user-permissions-and-visual-studio"></a>Oprávnění uživatele a Visual Studio

Z důvodů zabezpečení byste měli spustit Visual Studio jako normální uživatelské kdykoli je to možné.

> [!WARNING]
> Je třeba zajistit, aby nebylo kompilováno, spouštěno nebo laděno jakékoli řešení systému Visual Studio, které nebylo získáno od důvěryhodné osoby nebo z důvěryhodného zdroje.

Můžete to udělat téměř vše v prostředí Visual Studio IDE jako normální uživatel. Je třeba oprávnění správce pro dokončit následující úlohy:

|Oblast|Úloha|Další informace|
|----------|----------|--------------------------|
|Instalace|Nainstalujte Visual Studio.|[Instalace sady Visual Studio](../install/install-visual-studio.md)|
||Instalace, aktualizovat nebo odebrat místní obsah nápovědy.|[Instalace a Správa místního obsahu nápovědy](../ide/install-and-manage-local-content.md)|
|Typy aplikací|Vývoj řešení pro službu SharePoint.|[Požadavky na vývoj řešení služby SharePoint](../sharepoint/requirements-for-developing-sharepoint-solutions.md)|
|Sada nástrojů|Přidání klasického modelu COM ovládacích prvků do **sada nástrojů**.|[Panel nástrojů](../ide/reference/toolbox.md)|
|Sestavování|Události po sestavení, které registraci komponenty použijte.|[Vlastní kroky sestavení pochopit a události sestavení](/cpp/ide/understanding-custom-build-steps-and-build-events)|
||Při sestavování projektů C++, zahrnují kroku registrace.||
|Ladění|Ladění aplikace, které běží se zvýšenými oprávněními.|[Nastavení a příprava ladicího programu](../debugger/debugger-settings-and-preparation.md)|
||Ladění aplikace, které účet spustit v rámci jiného uživatele, jako webové stránky ASP.NET.|[Ladění aplikací ASP.NET a AJAX](../debugger/debugging-aspnet-and-ajax-applications.md)|
||Ladění pro aplikace prohlížeče XAML (XBAP) v zóně.|[WPF hostitele (PresentationHost.exe)](/dotnet/framework/wpf/app-development/wpf-host-presentationhost-exe)|
||Použití emulátoru k ladění projekty cloudových služeb pro Microsoft Azure.|[Ladění cloudové služby v sadě Visual Studio](/azure/vs-azure-tools-debug-cloud-services-virtual-machines)|
||Nastavení brány firewall pro vzdálené ladění.|[Vzdálené ladění](../debugger/remote-debugging.md)|
|Nástroje pro měření výkonu|Profilace aplikace|[Průvodce začátečníka profilací výkonu](../profiling/beginners-guide-to-performance-profiling.md)|
|Nasazení|Nasazení webové aplikace na Internetové informační služby (IIS) na místním počítači.|[Nasazení webové aplikace ASP.NET pomocí sady Visual Studio](/aspnet/web-forms/overview/older-versions-getting-started/deployment-to-a-hosting-provider/)|

## <a name="run-visual-studio-as-an-administrator"></a>Visual Studio spustit jako správce

Pokud potřebujete spustit sadu Visual Studio jako správce, otevřete prostředí IDE takto:

> [!NOTE]
> Tyto pokyny jsou určené pro Windows 10. Jsou podobné pro jiné verze systému Windows.

1. Otevřete **spustit** nabídce a posuňte se Visual Studio 2017.

1. Klikněte pravým tlačítkem nebo kontextu nabídce **Visual Studio 2017**, vyberte **Další** > **spustit jako správce**.

   Při spuštění sady Visual Studio, **(správce)** se zobrazí po název produktu v záhlaví.

Můžete také upravit zástupce aplikace vždy spustit s oprávněním správce.

## <a name="see-also"></a>Viz také:

- [Port, migrace a upgrade projektů sady Visual Studio](../porting/port-migrate-and-upgrade-visual-studio-projects.md)
- [Instalace sady Visual Studio](../install/install-visual-studio.md)