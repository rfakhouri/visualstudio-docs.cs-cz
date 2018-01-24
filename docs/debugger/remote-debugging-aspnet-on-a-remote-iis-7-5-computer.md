---
title: "Vzdálené ladění technologie ASP.NET v počítači vzdálené služby IIS | Microsoft Docs"
ms.custom: remotedebugging
ms.date: 07/26/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9cb339b5-3caf-4755-aad1-4a5da54b2a23
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: aspnet
ms.openlocfilehash: 6f11ec81c740a6930ce4eaef16d4e4e389aaca47
ms.sourcegitcommit: 65f85389047c5a1938b6d5243ccba8d4f14362ba
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2018
---
# <a name="remote-debug-aspnet-on-a-remote-iis-computer"></a>Vzdálené ladění technologie ASP.NET v počítači vzdálené služby IIS
K ladění aplikace ASP.NET, která byla nasazena do služby IIS, instalaci a spuštění nástrojů pro vzdálenou na počítači, kde jste nasadili aplikace a pak připojte k běžící aplikaci ze sady Visual Studio.

![Součásti vzdáleného ladicího programu](../debugger/media/remote-debugger-aspnet.png "Remote_debugger_components")

Tato příručka vysvětluje, jak nastavit a konfigurovat aplikaci Visual Studio 2017 ASP.NET MVC 4.5.2, nasazení pro službu IIS a připojení vzdáleného ladicího programu ze sady Visual Studio. Vzdálené ladění ASP.NET Core, najdete v tématu [vzdáleného ladění ASP.NET Core na počítači se službou IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md). Pro službu Azure App Service, můžete snadno nasadit a ladění předem nakonfigurované instance služby IIS pomocí [ladicí program snímku](../debugger/debug-live-azure-applications.md) (.NET 4.6.1 vyžaduje), nebo [připojení ladicího programu z Průzkumníka serveru](../debugger/remote-debugging-azure.md).

Tyto postupy jsme otestovali na tyto konfigurace serveru:
* Windows Server 2012 R2 a služby IIS 8 (pro Windows Server 2008 R2, server postup se liší)

## <a name="requirements"></a>Požadavky

Vzdáleného ladicího programu je podporována v systému Windows Server, počínaje systémem Windows Server 2008 Service Pack 2. Úplný seznam požadavků, najdete v části [požadavky](../debugger/remote-debugging.md#requirements_msvsmon).

> [!NOTE]
> Mezi dvěma počítači připojené prostřednictvím proxy serveru se nepodporuje ladění. Ladění nad vysokou latencí nebo připojení s malou šířkou pásma, například telefonického Internetu, nebo přes Internet napříč zemích se nedoporučuje a může selhat nebo být příliš pomalé.

## <a name="create-the-aspnet-452-application-on-the-visual-studio-computer"></a>Vytvoření projektu ASP.NET 4.5.2 aplikace na počítači Visual Studio
  
1. Vytvoření nové aplikace MVC ASP.NET. (**Soubor > Nový > projekt**, pak vyberte ** Visual C# > Web > webové aplikace ASP.NET. V **ASP.NET 4.5.2** část šablony, vyberte **MVC**. Ujistěte se, že **povolení podpory Docker** není vybraná a že **ověřování** je nastaven na **bez ověřování**. Název projektu **MyASPApp**.)

2. Otevřete soubor HomeController.cs a nastavte zarážky `About()` metoda.

## <a name="bkmk_configureIIS"></a>Instalace a konfigurace služby IIS v systému Windows Server

[!INCLUDE [remote-debugger-install-iis-role](../debugger/includes/remote-debugger-install-iis-role.md)]

## <a name="update-browser-security-settings-on-windows-server"></a>Aktualizovat nastavení zabezpečení prohlížeče v systému Windows Server

V závislosti na nastavení zabezpečení se může ušetřit čas přidat následující důvěryhodných serverů na prohlížeč, abyste si můžete snadno stáhnout software popsané v tomto kurzu. Může být potřeba přístup k těchto lokalit:

- microsoft.com
- go.microsoft.com
- download.microsoft.com
- visualstudio.com

Pokud používáte Internet Explorer, můžete přidat důvěryhodných serverů přechodem na **Možnosti Internetu > zabezpečení > důvěryhodných serverů > lokality**. Tyto kroky jsou u jiných prohlížečů. (Pokud budete muset stáhnout starší verze vzdáleného ladicího programu z my.visualstudio.com, některé další důvěryhodných serverů jsou nutné k přihlášení.)

Při stahování softwaru, může dojít k žádosti o udělení oprávnění ke spouštění různých skripty webu a prostředky. Ve většině případů není tyto další prostředky nutné k instalaci softwaru.

## <a name="BKMK_deploy_asp_net"></a>Instalace technologie ASP.NET 4.5 na Windows serveru

Pokud potřebujete podrobnější informace k instalaci technologie ASP.NET ve službě IIS, najdete v části [IIS 8.0 pomocí technologie ASP.NET 3.5 a technologii ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45).

1. Instalace webové platformy (WebPI) použít k instalaci technologie ASP.NET 4.5 (z uzlu serveru v systému Windows Server 2012 R2, zvolte **získat nové komponenty webové platformy** a poté vyhledejte ASP.NET)

    ![RemoteDBG_IIS_AspNet_45](../debugger/media/remotedbg_iis_aspnet_45.png "RemoteDBG_IIS_AspNet_45")

    > [!NOTE]
    > Pokud používáte Windows Server 2008 R2, nainstalujte technologii ASP.NET 4 místo použití tohoto příkazu:

     **C:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -ir**

2. Restartování systému (nebo spuštění **net stop byl /y** následuje **net start w3svc** z příkazového řádku a pokračovat tam ke změně systému cesta).

## <a name="BKMK_install_webdeploy"></a>(Volitelné) Nasazení webu instalace 3.6 v systému Windows Server

[!INCLUDE [remote-debugger-install-web-deploy](../debugger/includes/remote-debugger-install-web-deploy.md)]

## <a name="BKMK_deploy_asp_net"></a>Konfigurace webu ASP.NET na počítač s Windows serverem

1. Otevřete Průzkumníka Windows a vytvořte novou složku, **C:\Publish**, kde později nasadíte projekt ASP.NET.

2. Otevřete **Internetová informační služba (IIS) Manager**. (V levém podokně Správce serveru, vyberte **IIS**. Pravým tlačítkem na server a vyberte **Správce Internetové informační služby (IIS)**.)

3. V části **připojení** v levém podokně přejděte do **lokality**.

4. Vyberte **Default Web Site**, zvolte **základní nastavení**a nastavte **fyzická cesta** k **C:\Publish**.

5. Klikněte pravým tlačítkem myši **Default Web Site** uzel a vyberte možnost **přidat aplikaci**.

6. Nastavte **Alias** do **MyASPApp**, přijměte výchozí nastavení fondu aplikací (**DefaultAppPool**) a nastavte **fyzická cesta** k  **C:\Publish**.

7. V části **připojení**, vyberte **fondy aplikací**. Otevřete **DefaultAppPool** a nastavte hodnotu pole fondu aplikací na **ASP.NET v4.0** (ASP.NET 4.5 není možnost pro fond aplikací).

8. S lokalitou vybrané ve Správci služby IIS, zvolte **upravit oprávnění**a ujistěte se, že IUSR, IIS_IUSRS nebo uživateli nakonfigurovanému pro fond aplikací je oprávněný uživatel s oprávněními Číst a spouštět. Pokud žádná z těchto uživatelů jsou v něm, přidejte jako uživatel s právy ke čtení a spouštění IUSR.

## <a name="bkmk_webdeploy"></a>(Volitelné) Publikujte a nasaďte aplikace pomocí nasazení webu ze sady Visual Studio

[!INCLUDE [remote-debugger-deploy-app-web-deploy](../debugger/includes/remote-debugger-deploy-app-web-deploy.md)]

Navíc budete muset přečíst v části na [řešení potíží s porty](#bkmk_openports).

## <a name="optional-publish-and-deploy-the-app-by-publishing-to-a-local-folder-from-visual-studio"></a>(Volitelné) Publikujte a nasaďte aplikaci pomocí publikování do místní složky ze sady Visual Studio

Můžete také publikovat a nasazení aplikace pomocí systému souborů nebo jiných nástrojů.

1. (ASP.NET 4.5.2) Ujistěte se, že soubor web.config obsahuje seznam správnou verzi rozhraní .NET Framework.  Například pokud cílíte ASP.NET 4.5.2, ujistěte se, že tato verze je uveden v souboru web.config.
  
    ```xml
    <system.web>
      <compilation debug="true" targetFramework="4.5.2" />
      <httpRuntime targetFramework="4.5.2" />
      <httpModules>
        <add name="ApplicationInsightsWebTracking" type="Microsoft.ApplicationInsights.Web.ApplicationInsightsHttpModule, Microsoft.AI.Web" />
      </httpModules>
    </system.web>
  
    ```

    Verze by měl být například 4.0 při instalaci ASP.NET 4 místo 4.5.2.

[!INCLUDE [remote-debugger-deploy-app-local](../debugger/includes/remote-debugger-deploy-app-local.md)]

## <a name="BKMK_msvsmon"></a>Stáhněte a nainstalujte nástroje pro vzdálenou v systému Windows Server

V tomto kurzu používáme Visual Studio 2017.

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

> [!TIP]
> V některých případech může být nejúčinnější ke spuštění vzdáleného ladicího programu ze sdílené složky. Další informace najdete v tématu [spuštění vzdáleného ladicího programu ze sdílené složky](../debugger/remote-debugging.md#fileshare_msvsmon).
  
## <a name="BKMK_setup"></a>Nastavení vzdáleného ladicího programu v systému Windows Server

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> Pokud potřebujete přidat oprávnění pro všechny další uživatele, změna režimu ověřování, nebo číslo portu pro vzdáleného ladicího programu, najdete v části [konfigurovat vzdálený ladicí program](../debugger/remote-debugging.md#configure_msvsmon).

Informace o spuštění jako služba vzdáleného ladicího programu najdete v tématu [spuštěn jako služba vzdáleného ladicího programu](../debugger/remote-debugging.md#bkmk_configureService).

## <a name="BKMK_attach"></a>Připojení k aplikaci ASP.NET z počítače, Visual Studio

1. Otevřete v sadě Visual Studio počítači, **MyASPApp** řešení.
2. V sadě Visual Studio, klikněte na tlačítko **ladění > připojit k procesu** (Ctrl + Alt + P).

    > [!TIP]
    > V aplikaci Visual Studio 2017, může do stejného procesu dříve připojen k pomocí připojte **ladění > připojte k procesu...** (Shift + Alt + P). 

3. Nastavte hodnotu pole kvalifikátor na  **\<název vzdáleného počítače >: 4022**.
4. Klikněte na tlačítko **aktualizovat**.
    Měli byste vidět některé procesy, které se zobrazí v **dostupné procesy** okno.

    Pokud nevidíte žádné procesy, zkuste pomocí IP adresy místo název vzdáleného počítače (port je vyžadováno). Můžete použít `ipconfig` v příkazovém řádku, potřebujete adresu IPv4.

5. Zkontrolujte **Zobrazit procesy od všech uživatelů**.
6. Zadejte první písmeno názvu procesu a rychle tak najít **w3wp.exe** pro technologii ASP.NET 4.5.

    ![RemoteDBG_AttachToProcess](../debugger/media/remotedbg_attachtoprocess.png "RemoteDBG_AttachToProcess")

7. Klikněte na tlačítko **připojení**

8. Otevřete web vzdáleného počítače. V prohlížeči přejděte na **http://\<název vzdáleného počítače >**.
    
    Měli byste vidět webová stránka ASP.NET.
9. V běžící aplikaci ASP.NET, klikněte na odkaz **o** stránky.

    Zarážce by měl být dosáhl v sadě Visual Studio.

## <a name="bkmk_openports"></a>Řešení potíží: Otevřete požadované porty v systému Windows Server

Ve většině nastavení jsou otevřené požadované porty při instalaci ASP.NET a vzdáleného ladicího programu. Potřebujete však ověřte, že jsou otevřené porty.

> [!NOTE]
> Ve virtuálním počítači Azure, musíte otevřít porty prostřednictvím [skupinu zabezpečení sítě](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80). 

Požadované porty:

- 80 - požadované pro službu IIS
- 8172 – (volitelné) požadované pro nasazení webu pro nasazení aplikace z Visual Studia
- 4022 - požadované pro vzdálené ladění z Visual Studio 2017 (viz [přiřazení portu vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md) podrobné informace.
- UDP 3702 - port (volitelné) zjišťování umožňuje **najít** tlačítko při připojování k vzdáleného ladicího programu v sadě Visual Studio.

1. Chcete-li otevřít port v systému Windows Server, otevřete **spustit** nabídky, vyhledejte **brány Windows Firewall s pokročilým zabezpečením**.

2. Zvolte **příchozí pravidla > nové pravidlo > Port**. Zvolte **Další** a v části **určité místní porty**, zadejte číslo portu, klikněte na **Další**, pak **povolit připojení**, klikněte na tlačítko Další, a Přidejte název (**IIS**, **Web Deploy**, nebo **msvsmon**) pro příchozí pravidlo.

    Pokud chcete další informace o konfiguraci brány Windows Firewall, najdete v části [konfigurace brány Windows Firewall pro vzdálené ladění](../debugger/configure-the-windows-firewall-for-remote-debugging.md).

3. Vytvořte další pravidla pro požadované porty.