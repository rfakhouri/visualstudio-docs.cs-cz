---
title: "Oprávnění uživatele a Visual Studio | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio, user permissions
- user permissions
- administrative privileges
- permissions
ms.assetid: 70485ed7-6342-41bf-8250-7a6826e21b98
caps.latest.revision: "14"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: e044e3d89f7cbaae28ff0fd3cefe1c6fe4583c65
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="user-permissions-and-visual-studio"></a>Uživatelská oprávnění a sada Visual Studio
Z důvodu bezpečnosti by měl být systém Visual Studio spuštěn s normálním uživatelským přístupem, kdykoli je to možné.  

> [!WARNING]
>  Je třeba zajistit, aby nebylo kompilováno, spouštěno nebo laděno jakékoli řešení systému Visual Studio, které nebylo získáno od důvěryhodné osoby nebo z důvěryhodného zdroje.  

 V režimu normálního uživatele lze v integrovaném vývojovém prostředí IDE aplikace Visual Studio provádět téměř cokoli, ale pro provedení následujících úkolů je potřeba mít administrátorská oprávnění:  

|Oblast|Úloha|Další informace|  
|----------|----------|--------------------------|  
|Instalace|Nainstalujte Visual Studio.|[Instalaci sady Visual Studio](../install/install-visual-studio.md)|  
||Instalace, aktualizace nebo odebrání obsahu místní nápovědy|[Instalace a Správa místního obsahu](../ide/install-and-manage-local-content.md)|  
|Typy aplikací|Vývoj řešení pro službu SharePoint.|[Požadavky na vývoj řešení služby SharePoint](/office-dev/office-dev/requirements-for-developing-sharepoint-solutions)|  
||Získání licence pro vývojáře [!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)].|[Získat licenci vývojáře](http://go.microsoft.com/fwlink/?LinkID=241313)|  
|Sada nástrojů|Přidání klasického modelu COM ovládacích prvků na **sada nástrojů**.|[Pomocí sady nástrojů](../ide/using-the-toolbox.md)|  
|Doplňky|Instalace a používání doplňků, které byly vytvořeny pomocí klasického modelu COM v rozhraní IDE|[Vytváření doplňků a průvodců](http://msdn.microsoft.com/Library/c5a47c21-6668-4de3-898d-afa969317e73)|  
|Sestavování|Použití událostí po sestavení, které registrují komponentu|[Seznámení s kroky vlastního sestavení a událostí sestavení](/cpp/ide/understanding-custom-build-steps-and-build-events)|  
||Zahrnutí registračního kroku do sestavování projektů v jazyce C++|[Seznámení s kroky vlastního sestavení a událostí sestavení](/cpp/ide/understanding-custom-build-steps-and-build-events)|  
|Ladění|Ladění aplikací spouštěných se zvýšenými oprávněními|[Nastavení ladicího programu a příprava](../debugger/debugger-settings-and-preparation.md)|  
||Ladění aplikací, které běží pod jiným uživatelským účtem, jako jsou weby ASP.NET|[Ladění aplikací ASP.NET a AJAX](../debugger/debugging-aspnet-and-ajax-applications.md)|  
||Ladění v zóně pro aplikace prohlížeče XAML (XBAP)|[WPF hostitele (PresentationHost.exe)](/dotnet/framework/wpf/app-development/wpf-host-presentationhost-exe)|  
||Pomocí emulátoru k ladění projekty cloudových služeb pro Microsoft Azure.|[Ladění cloudové služby v sadě Visual Studio](http://go.microsoft.com/fwlink/?LinkId=266725)|  
||Konfigurace brány firewall pro vzdálené ladění|[Vzdálené ladění](../debugger/remote-debugging.md)|  
|Nástroje pro měření výkonu|Profilace aplikace|[Průvodce začátečníka profilací výkonu](../profiling/beginners-guide-to-performance-profiling.md)|  
|Nasazení|Nasazení webové aplikace do Internetové informační služby (IIS) v místním počítači|[Nasazení webové aplikace ASP.NET do poskytovatele hostování pomocí sady Visual Studio nebo Visual Web Developer: nasazení do IIS jako testovacího prostředí](http://go.microsoft.com/fwlink/?LinkId=266478)|

## <a name="running-visual-studio-as-an-administrator"></a>Spuštění sady Visual Studio jako správce  
 Sadu Visual Studio můžete spustit s oprávněními správce při každém spuštění rozhraní IDE nebo můžete upravit zástupce sady tak, aby se vždy spustila s oprávněními správce. Další informace naleznete v nápovědě pro Windows.  

#### <a name="to-run-visual-studio-with-administrative-permissions-on-includewin8debuggerincludeswin8mdmd-includewin81debuggerincludeswin81mdmd-includewinserver8debuggerincludeswinserver8mdmd-or-includewinblueserver2ideincludeswinblueserver2mdmd"></a>Spuštění sady Visual Studio s oprávněními pro správu [!INCLUDE[win8](../debugger/includes/win8_md.md)], [!INCLUDE[win81](../debugger/includes/win81_md.md)], [!INCLUDE[winserver8](../debugger/includes/winserver8_md.md)], nebo[!INCLUDE[winblue_server_2](../ide/includes/winblue_server_2_md.md)]  

1.  Na **spustit** zadejte **Visual Studio**. Měli byste vidět verzi nebo verze systému Visual Studio, které jste nainstalovali.  

2.  Vyberte verzi systému Visual Studio, kterou chcete spustit, a následně vyvolejte místní nabídku (zobrazí se v dolní části obrazovky). Zvolte **spustit jako správce**.  

     Při spuštění sady Visual Studio, **(správce)** se zobrazí po název produktu v záhlaví.  

#### <a name="to-run-visual-studio-with-administrative-permissions-on-includewin7debuggerincludeswin7mdmd-or-includewinsvr08r2debuggerincludeswinsvr08r2mdmd"></a>Spuštění sady Visual Studio s oprávněními pro správu [!INCLUDE[win7](../debugger/includes/win7_md.md)] nebo[!INCLUDE[winsvr08_r2](../debugger/includes/winsvr08_r2_md.md)]  

1.  Na **spustit** nabídce zvolte **všechny programy**.  

2.  V **Microsoft Visual Studio** *verze* vyberte složku **Visual Studio** *verze* otevřete místní nabídce a potom zvolte  **Spustit jako správce**.  

     Při spuštění sady Visual Studio, **(správce)** se zobrazí po název produktu v záhlaví.  

## <a name="see-also"></a>Viz také  
 [Portování, migrace a upgrade projektů sady Visual Studio](../porting/port-migrate-and-upgrade-visual-studio-projects.md)   
 [Instalaci sady Visual Studio](../install/install-visual-studio.md)
