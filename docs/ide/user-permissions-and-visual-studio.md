---
title: Oprávnění uživatele a Visual Studio
ms.date: 11/04/2016
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
ms.openlocfilehash: 168fb9441080a9c8f61d703485b0274d91dc3189
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/03/2018
---
# <a name="user-permissions-and-visual-studio"></a>Oprávnění uživatele a Visual Studio

Z důvodu bezpečnosti by měl být systém Visual Studio spuštěn s normálním uživatelským přístupem, kdykoli je to možné.

> [!WARNING]
> Je třeba zajistit, aby nebylo kompilováno, spouštěno nebo laděno jakékoli řešení systému Visual Studio, které nebylo získáno od důvěryhodné osoby nebo z důvěryhodného zdroje.

V režimu normálního uživatele lze v integrovaném vývojovém prostředí IDE aplikace Visual Studio provádět téměř cokoli, ale pro provedení následujících úkolů je potřeba mít administrátorská oprávnění:

|Oblast|Úloha|Další informace|
|----------|----------|--------------------------|
|Instalace|Nainstalujte Visual Studio.|[Instalace sady Visual Studio](../install/install-visual-studio.md)|
||Instalace, aktualizace nebo odebrání obsahu místní nápovědy|[Instalace a Správa místního obsahu](../ide/install-and-manage-local-content.md)|
|Typy aplikací|Vývoj řešení pro službu SharePoint.|[Požadavky na vývoj řešení služby SharePoint](/office-dev/office-dev/requirements-for-developing-sharepoint-solutions)|
||Získání licence pro vývojáře [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)].|[Získat licenci vývojáře](http://go.microsoft.com/fwlink/?LinkID=241313)|
|Sada nástrojů|Přidání klasického modelu COM ovládacích prvků do **sada nástrojů**.|[Panel nástrojů](../ide/reference/toolbox.md)|
|Doplňky|Instalace a používání doplňků, které byly vytvořeny pomocí klasického modelu COM v rozhraní IDE|[Vytváření doplňků a průvodců](http://msdn.microsoft.com/Library/c5a47c21-6668-4de3-898d-afa969317e73)|
|Sestavování|Použití událostí po sestavení, které registrují komponentu|[Vlastní kroky sestavení pochopit a události sestavení](/cpp/ide/understanding-custom-build-steps-and-build-events)|
||Zahrnutí registračního kroku do sestavování projektů v jazyce C++|[Vlastní kroky sestavení pochopit a události sestavení](/cpp/ide/understanding-custom-build-steps-and-build-events)|
|Ladění|Ladění aplikací spouštěných se zvýšenými oprávněními|[Nastavení a příprava ladicího programu](../debugger/debugger-settings-and-preparation.md)|
||Ladění aplikací, které běží pod jiným uživatelským účtem, jako jsou weby ASP.NET|[Ladění aplikací ASP.NET a AJAX](../debugger/debugging-aspnet-and-ajax-applications.md)|
||Ladění v zóně pro aplikace prohlížeče XAML (XBAP)|[Hostitel WPF (PresentationHost.exe)](/dotnet/framework/wpf/app-development/wpf-host-presentationhost-exe)|
||Pomocí emulátoru k ladění projekty cloudových služeb pro Microsoft Azure.|[Ladění cloudové služby v sadě Visual Studio](http://go.microsoft.com/fwlink/?LinkId=266725)|
||Konfigurace brány firewall pro vzdálené ladění|[Vzdálené ladění](../debugger/remote-debugging.md)|
|Nástroje pro měření výkonu|Profilace aplikace|[Průvodce začátečníka profilací výkonu](../profiling/beginners-guide-to-performance-profiling.md)|
|Nasazení|Nasazení webové aplikace do Internetové informační služby (IIS) v místním počítači|[Nasadit webovou aplikaci ASP.NET do hostujícího zprostředkovatele pomocí sady Visual Studio nebo Visual Web Developer: nasazení do IIS jako testovacího prostředí](http://go.microsoft.com/fwlink/?LinkId=266478)|

## <a name="run-visual-studio-as-an-administrator"></a>Visual Studio spustit jako správce

Sadu Visual Studio můžete spustit s oprávněními správce při každém spuštění rozhraní IDE nebo můžete upravit zástupce sady tak, aby se vždy spustila s oprávněními správce. Další informace naleznete v nápovědě pro Windows.

### <a name="run-visual-studio-with-administrative-permissions"></a>Visual Studio spustit s oprávněním správce

Tyto pokyny jsou určené pro Windows 10. Jsou podobné pro jiné verze systému Windows.

1. Otevřete **spustit** nabídce a posuňte se Visual Studio 2017.

1. Klikněte pravým tlačítkem nebo kontextu nabídce **Visual Studio 2017**, vyberte **Další** > **spustit jako správce**.

     Při spuštění sady Visual Studio, **(správce)** se zobrazí po název produktu v záhlaví.

## <a name="see-also"></a>Viz také

- [Port, migrace a upgrade projektů sady Visual Studio](../porting/port-migrate-and-upgrade-visual-studio-projects.md)
- [Instalace sady Visual Studio](../install/install-visual-studio.md)