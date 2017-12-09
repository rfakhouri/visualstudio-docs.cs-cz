---
title: "Vzdálené ladění v sadě Visual Studio | Microsoft Docs"
ms.custom: remotedebugging
ms.date: 08/14/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: hero-article
f1_keywords: vs.debug.remote.overview
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords: remote debugging, setup
ms.assetid: 5a94ad64-100d-43ca-9779-16cb5af86f97
caps.latest.revision: "65"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0d945c28e7fe703c80776a5f1ff124ab6e0a8bf9
ms.sourcegitcommit: ebe9fb5eda724936f7a059d35d987c29dffdb50d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/07/2017
---
# <a name="remote-debugging"></a>Vzdálené ladění
Můžete ladit aplikace z Visual Studia, která byla nasazena do jiného počítače. K tomu použít vzdáleného ladicího programu sady Visual Studio.

Podrobné pokyny pro vzdálené ladění naleznete v následujících tématech.

|Scénář|Odkaz|
|-|-|-|
|ASP.NET|[Vzdálené ladění ASP.NET Core](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md) nebo [vzdáleného ladění ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)|
|C# nebo Visual Basic|[Vzdálené ladění jazyka C# nebo projektu jazyka Visual Basic](remote-debugging-csharp.md)|
|C++|[Vzdálené ladění projektu jazyka C++](remote-debugging-cpp.md)|
|Univerzální aplikace pro Windows (UWP)|[Ladění nainstalovaným balíčkem aplikace](debug-installed-app-package.md)|
|Azure|[Vzdálené ladění technologie ASP.NET v Azure](remote-debugging-azure.md)|
|Azure Service Fabric|[Ladění vzdáleného aplikace Service Fabric](/azure/service-fabric/service-fabric-debugging-your-application#debug-a-remote-service-fabric-application).|

Pokud jste právě chcete stáhnout a nainstalovat vzdáleného ladicího programu a nepotřebujete žádné další pokyny pro váš scénář, postupujte podle kroků v tomto článku.
  
## <a name="download-and-install-the-remote-tools"></a>Stáhněte a nainstalujte nástroje pro vzdálenou  

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

### <a name="fileshare_msvsmon"></a>(Volitelné) Ke spuštění vzdáleného ladicího programu ze sdílené složky

Můžete najít vzdáleného ladicího programu (**msvsmon.exe**) na počítači s Visual Studio Community, Professional nebo Enterprise již nainstalován. V některých případech je nejjednodušší způsob, jak nastavení vzdáleného ladění spuštění vzdáleného ladicího programu (msvsmon.exe) ze sdílené složky. Omezení využití najdete v části stránky nápovědy vzdáleného ladicího programu (**pomoci > využití** v vzdáleného ladicího programu).

1. Najít **msvsmon.exe** v adresáři odpovídající vaší verzí sady Visual Studio. Pro Visual Studio Enterprise 2017:

      **Program soubory (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\Remote Debugger\x86\msvsmon.exe**
      
      **Program soubory (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\Remote Debugger\x64\msvsmon.exe**

2. Sdílené složky **vzdáleného ladicího programu** složky v počítači, Visual Studio.

3. Na vzdáleném počítači, spusťte **msvsmon.exe**. Postupujte podle [pokyny](#bkmk_setup).

> [!TIP] 
> Instalace pomocí příkazového řádku a odkaz na příkazový řádek najdete v tématu na stránce nápovědy pro **msvsmon.exe** zadáním ``msvsmon.exe /?`` v příkazovém řádku na počítači s nainstalovanou sadu Visual Studio (nebo na **pomoci > využití**v vzdáleného ladicího programu).
  
## <a name="requirements_msvsmon"></a>Požadavky

[!INCLUDE [remote-debugger-requirements](../debugger/includes/remote-debugger-requirements.md)]
  
## <a name="set-up-the-remote-debugger"></a>Nastavení vzdáleného ladicího programu  

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

### <a name="configure_msvsmon"></a>Konfigurovat vzdálený ladicí program  
Po prvním spuštění ho můžete změnit některé aspekty konfigurace vzdáleného ladicího programu.
  
-   Pokud potřebujete přidat oprávnění pro ostatní uživatele, který chcete připojit k vzdáleného ladicího programu, zvolte **nástroje > oprávnění**. K udělení nebo odebrání oprávnění je potřeba mít oprávnění správce.

     > [!IMPORTANT] 
     > Můžete spustit vzdáleného ladicího programu u uživatelského účtu, který se liší od uživatelského účtu, který používáte v sadě Visual Studio počítači, ale musíte přidat jiný uživatelský účet oprávnění vzdáleného ladicího programu. 

     Alternativně můžete spustit vzdálený ladicí program z příkazového řádku **/ povolit \<uživatelské jméno >** parametr: **msvsmon / povolit \< username@computer>**.
  
-   Pokud potřebujete změnit režim ověřování nebo číslo portu, nebo zadejte hodnotu časového limitu pro nástrojů pro vzdálenou: Zvolte **nástroje > Možnosti**.  
  
     V seznamu čísel portů, které jsou ve výchozím nastavení používá, najdete v části [přiřazení portu vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md).  
  
     > [!WARNING]
     >  Můžete také spustit nástroje Remote Tools v režimu bez ověřování, ale tento režim se rozhodně nedoporučuje. Při spuštění v tomto režimu není žádné zabezpečení sítě. Vyberte režim ověřování ne jenom v případě, že jste si jisti, že síť není riziku škodlivý nebo nepřátelských přenosů.

##  <a name="bkmk_configureService"></a>(Volitelné) Konfigurovat vzdálený ladicí program jako služby
Pro ladění v technologii ASP.NET a dalších prostředích s serveru, se musí spustit vzdáleného ladicího programu jako správce nebo, je vždy spuštěn, chcete-li spuštěn jako služba vzdáleného ladicího programu.
  
 Pokud chcete konfigurovat vzdálený ladicí program jako službu, postupujte podle těchto kroků.  
  
1.  Najít **Průvodce konfigurací vzdáleného ladicího programu** (rdbgwiz.exe). (To je samostatná aplikace ze vzdáleného ladicího programu.) Je k dispozici, pouze při instalaci nástrojů pro vzdálenou. Nenainstaluje se sadou Visual Studio.  
  
2.  Spusťte Průvodce konfigurací. Po první stránka se zobrazí, klikněte na tlačítko **Další**.  
  
3.  Zkontrolujte **Visual Studio 2015 vzdálený ladicí program spuštěn jako služba** zaškrtávací políčko.  
  
4.  Přidejte název uživatelského účtu a heslo.  
  
     Je nutné přidat **přihlásit jako službu** uživatelské právo k tomuto účtu (Najít **místní zásady zabezpečení** (secpol.msc) v **spustit** stránky nebo okna (nebo typ  **secpol** na příkazovém řádku). Po zobrazení dialogového okna, klikněte dvakrát na **přiřazení uživatelských práv**, vyhledejte **přihlásit jako službu** v pravém podokně. Dvojím kliknutím. Přidat uživatelský účet **vlastnosti** a klikněte na **OK**). Klikněte na tlačítko **Další**.  
  
5.  Vyberte typ sítě, která chcete nástrojů pro vzdálenou komunikaci s. Musí být vybrán alespoň jeden typ sítě. Pokud jsou počítače připojené přes domény, měli byste vybrat první položka. Pokud jsou počítače připojené přes domácí nebo pracovní skupině, měli byste vybrat druhý nebo třetí položek. Klikněte na tlačítko **Další**.  
  
6.  Pokud se spuštění služby, zobrazí se **úspěšně jste dokončili Průvodce Visual Studio vzdáleného ladicího programu konfigurace**. Pokud službu nelze spustit, zobrazí se **se nepodařilo dokončit Visual Studio vzdáleného ladicího programu Průvodce konfigurací**. Stránce také poskytuje některé tipy, jak provést, pokud chcete získat službu spustit.  
  
7.  Klikněte na tlačítko **Dokončit**.  
  
 V tomto okamžiku vzdáleného ladicího programu běží jako služba. Můžete to ověřit tak, že přejdete do **ovládací panely > služby** a hledá **Visual Studio 2015 vzdáleného ladicího programu**.  
  
 Můžete zastavit a spustit službu vzdáleného ladicího programu z **ovládací panely > služby**.

## <a name="set-up-debugging-with-remote-symbols"></a>Nastavení ladění se vzdálené symboly 

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)]
  
## <a name="see-also"></a>Viz také  
 [Prohlídka funkce ladicí program](../debugger/debugger-feature-tour.md)   
 [Konfigurace brány Windows Firewall pro vzdálené ladění](../debugger/configure-the-windows-firewall-for-remote-debugging.md)   
 [Přiřazení portů vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md)   
 [Vzdálené ladění ASP.NET Core v počítači vzdálené služby IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)  
 [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)
