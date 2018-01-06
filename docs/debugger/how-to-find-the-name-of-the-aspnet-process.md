---
title: "Postupy: hledání názvu procesu ASP.NET | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- ASP.NET debugging, ASP.NET process
- ASP.NET process
ms.assetid: 931a7597-b0f0-4a28-931d-46e63344435f
caps.latest.revision: "29"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: aspnet
ms.openlocfilehash: e542e58bab483a1f20029bb66a073ae07d45afba
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-find-the-name-of-the-aspnet-process"></a>Postupy: Hledání názvu procesu ASP.NET
Pro připojení k spuštěný [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] aplikace, musíte znát název [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] proces:  

-   Pokud používáte jádro ASP.NET na IIS nebo IIS Express, je název procesu dotnet.exe.

-   Pokud spustíte ASP.NET na IIS 6.0 později, je název w3wp.exe.  
  
-   Pokud používáte ve starší verzi služby IIS, ASP.NET, je název aspnet_wp.exe.

-   Pokud používáte ASP.NET na IIS Express, je název iisexpress.exe.
  
Pro aplikace vytvořené s použitím verze sady Visual Studio před sady Visual Studio 2012 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] kód může nacházet v systému souborů a běh testovací server WebDev.WebServer.exe nebo WebDev.WebServer40.exe. V takovém případě se musí připojit k WebDev.WebServer.exe nebo WebDev.WebServer40.exe místo [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] procesu. Tento scénář se vztahuje pouze na místní ladění.
  
Starší aplikace ASP spustit uvnitř inetinfo.exe proces služby IIS, když běží v procesu.  

### <a name="to-determine-the-iis-version-under-which-the-application-is-running"></a>Určení verze služby IIS, pod kterým je aplikace spuštěna  

1.  Ujistěte se, že je aplikace spuštěna a poté ze sady Visual Studio, použijte [připojit k procesu](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md) příkaz.

2.  Zadejte název procesu jako w3wp.exe rychle najít procesy v první písmeno **dostupné procesy** seznamu.

    K dispozici procesy ze seznamu v tomto tématu označí, jaké verze služby IIS jsou k dispozici, a které proces běží vaše aplikace.

    > [!NOTE]
    > Od verze Visual Studio 2017, můžete do vyhledávacího pole pro vyhledávání pro název procesu.
  
## <a name="see-also"></a>Viz také  
 [Připojit k spuštěných procesů](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)  
 [Předpoklady pro vzdálené ladění webových aplikací](../debugger/prerequistes-for-remote-debugging-web-applications.md)   
 [Požadavky na systém](../debugger/aspnet-debugging-system-requirements.md)   
 [Ladění aplikací ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)