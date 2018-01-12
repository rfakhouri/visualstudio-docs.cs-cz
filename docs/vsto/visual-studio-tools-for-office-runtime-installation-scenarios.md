---
title: "Visual Studio Tools for Office Runtime instalace scénáře | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords: Visual Studio Tools for Office runtime, installation scenarios
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 9c63f5e4cef88ed927326b69f1fa389e34b06c8b
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="visual-studio-tools-for-office-runtime-installation-scenarios"></a>Scénáře instalace nástrojů Visual Studio Tools for Office runtime
  Můžete nainstalovat sadu Visual Studio 2010 Tools for Office Runtime třemi způsoby:  
  
-   Při instalaci sady Visual Studio.  
  
-   Při instalaci aplikace Microsoft Office.  
  
-   Když nainstalujete sadu Visual Studio 2010 Tools for Office Runtime redistributable.  
  
 Součásti režimu runtime, které jsou nainstalovány záviset na konfiguraci počítače a scénáře instalace.  
  
## <a name="runtime-components-that-are-installed-in-each-installation-scenario"></a>Součásti režimu runtime, které jsou nainstalovány v každém scénáři instalace  
 Visual Studio 2010 Tools for Office Runtime má tři komponenty: zavaděč řešení Office, Office rozšíření pro rozhraní .NET Framework 3.5 a Office rozšíření pro [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější. Při instalaci modulu runtime, je vždy nainstalován zavaděč řešení Office. Instalace Office rozšíření pro rozhraní .NET Framework závisí na konfiguraci počítače a scénáře instalace. Pokud jedno z rozšíření Office nelze nainstalovat po první instalaci modulu runtime, modul runtime automaticky nainstaluje chybějící rozšíření Office později, pokud jsou splněny některé požadavky. Tato funkce modulu runtime se nazývá *na požádání nainstalovat*.  
  
 V následující tabulce jsou součástí modulu runtime, které jsou nainstalované ve výchozím nastavení v každém scénáři instalace modulu runtime. Další informace o scénářích se zobrazí později.  
  
|Scénáře instalace modulu runtime|Zavaděč řešení Office|Rozšíření Office pro rozhraní .NET Framework 3.5|Office rozšíření pro[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)]|Office rozšíření pro[!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)]|  
|-----------------------------------|----------------------------|--------------------------------------------------|---------------------------------------------------------------------------------------|---------------------------------------------------------------------------|  
|S [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] a novější|Ano|Ano, pokud rozhraní .NET Framework 3.5 je již nainstalován.|Ano|Ano|  
|S[!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]|Ano|Ano, pokud rozhraní .NET Framework 3.5 je již nainstalován.|Ne|Ne|  
|Office 2010 Service Pack 1 (SP1) nebo novější|Ano|Ano, pokud rozhraní .NET Framework 3.5 je již nainstalován.|Ano, pokud [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] je již nainstalován.|Ne|  
|S modulem runtime redistributable|Ano|Ano, pokud rozhraní .NET Framework 3.5 je již nainstalován.|Ano, pokud [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] je již nainstalován.|Ano, pokud [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] je již nainstalován.|  
  
### <a name="installing-the-runtime-with-visual-studio-or-the-microsoft-office-developer-tools-for-visual-studio"></a>Instalace modulu Runtime s Visual Studio nebo Microsoft Office Developer Tools pro sadu Visual Studio  
 Při instalaci doplňku Office developer tools v sadě Visual Studio, Office rozšíření pro [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] a [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] jsou vždy nainstalován ve vývojovém počítači. Rozšíření Office pro rozhraní .NET Framework 3.5 jsou nainstalované jenom v případě, že rozhraní .NET Framework 3.5 je již na vývojovém počítači. Pokud je po instalaci nainstalovat rozhraní .NET Framework 3.5 [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)], modul runtime automaticky nainstaluje Office rozšíření pro rozhraní .NET Framework 3.5 při prvním vytvoření projektu Office cílí na rozhraní .NET Framework 3.5.  
  
> [!WARNING]  
>  Nelze vytvořit projekt sady Office, který cílí na rozhraní .NET Framework 3.5 pomocí [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)] nebo novější.  
  
 Další informace o tom, jak nainstalujte Office developer tools najdete v tématu [postupy: Konfigurace počítače pro vývoj řešení pro Office](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md).  
  
### <a name="installing-the-runtime-with-office"></a>Instalace modulu Runtime s Office  
 Při instalaci Office je Office rozšíření pro rozhraní .NET Framework 3.5 instalují, pokud rozhraní .NET Framework 3.5 je již přítomna na počítači. Při instalaci rozhraní .NET Framework 3.5 po Office, modul runtime rozšíření Office automaticky nainstaluje rozhraní .NET Framework 3.5 první čas, kdy aplikace Office se pokusí načíst řešení s cílem rozhraní .NET Framework 3.5.  
  
 Office rozšíření pro [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo později nejsou nainstalovány s Office, i v případě [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo novější se již nachází při instalaci Office.  
  
 Office rozšíření pro [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] jsou nainstalovány v sadě Office. Koncoví uživatelé mohou získat Office rozšíření pro [!INCLUDE[net_v45](../vsto/includes/net-v45-md.md)] nainstalováním služby Windows update.  
  
 K zajištění, že uživatelé mají potřebnými rozšířeními ke používat vaši aplikaci, zahrnují nejnovější verzi sady Visual Studio 2010 Tools for Office Runtime redistributable předpokladem pro vaše řešení. Další informace o požadavcích najdete v tématu [požadavky řešení Office na nasazení](http://msdn.microsoft.com/en-us/9f672809-43a3-40a1-9057-397ce3b5126e).  
  
### <a name="installing-the-runtime-by-using-the-runtime-redistributable"></a>Instalace modulu Runtime s použitím modulu Runtime Redistributable  
 Modul runtime můžete nainstalovat spuštěním sady Visual Studio 2010 Tools for Office Runtime redistributable ručně nebo zahrnutím redistributable předpokladem je při nasazení řešení Office.  
  
 Při instalaci modulu runtime s použitím sady Visual Studio 2010 Tools for Office Runtime redistributable, Office rozšíření pro rozhraní .NET Framework 3.5 a Office rozšíření pro [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] nebo později instalují Pokud odpovídající verze rozhraní .NET Framework se již nachází v počítači. Pokud v počítači chybí jedna z těchto verzí rozhraní .NET Framework, když je nainstalován modul runtime, rozšíření Office pro chybějící verzi rozhraní .NET Framework nejsou nainstalovány v daném čase. Pokud instalujete chybějící verzi rozhraní .NET Framework později, modul runtime automaticky nainstaluje odpovídající rozšíření Office při příštím řešení, které vyžaduje rozšíření je nainstalována (Pokud byl nainstalován modul runtime s řešením, který byl nasazen s použitím technologie ClickOnce) nebo načíst (Pokud je modul runtime byl nainstalován s řešením, který byl nasazen pomocí Instalační služby systému Windows).  
  
 Další informace týkající se požadované součásti v řešení ClickOnce najdete v tématu [postupy: instalace požadavky v počítačích koncových uživatelů pro spuštění řešení pro systém Office](http://msdn.microsoft.com/en-us/74dd2c52-838f-4abf-b2b4-4d7b0c2a0a98). Další informace o tom, jak ručně nainstalovat modul runtime z redistribuovatelného balíčku najdete v tématu [postupy: instalace sady Visual Studio Tools pro sadu Office Runtime Redistributable](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md).  
  
## <a name="see-also"></a>Viz také  
 [Visual Studio Tools for Office Runtime – přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Sestavení v nástrojích Visual Studio Tools for Office runtime](../vsto/assemblies-in-the-visual-studio-tools-for-office-runtime.md)  
  
  