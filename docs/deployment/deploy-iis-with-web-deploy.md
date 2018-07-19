---
title: Nasazení do služby IIS pomocí nasazení webu ASP.NET
ms.custom: ''
ms.date: 06/04/2018
ms.technology: vs-ide-deployment
ms.topic: tutorial
ms.assetid: 9cb339b5-3caf-4755-aad1-4a5da54b2a23
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
ms.openlocfilehash: 4705ca6e72001f8930e2fa4270515df53e1213a8
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/17/2018
ms.locfileid: "39080847"
---
# <a name="deploy-aspnet-to-a-remote-iis-computer-using-web-deploy-in-visual-studio"></a>Nasazení technologie ASP.NET ke vzdálenému počítači služby IIS pomocí nasazení webu v sadě Visual Studio

Tento článek vysvětluje, jak nastavit a nakonfigurovat aplikaci s Visual Studio 2017 ASP.NET MVC 4.5.2 a nasaďte ji do služby IIS. Tento článek obsahuje kroky k nastavení základní konfiguraci služby IIS na Windows serveru a nasazení aplikace v sadě Visual Studio. Tyto kroky jsou zahrnuty, abyste měli jistotu, že server vyžaduje nainstalované součásti a že jste připravení nasadit. Pokud provádíte nasazení aplikace ASP.NET Core, některé postup se liší. Nasazení aplikace ASP.NET Core najdete v tématu [publikování aplikace do služby IIS pomocí importu nastavení publikování](../deployment/tutorial-import-publish-settings-iis.md) pokyny. V některých scénářích technologie ASP.NET a ASP.NET Core je rychlejší nasazení do služby IIS pomocí importu nastavení publikování.

Tyto postupy jsme otestovali na tyto konfigurace serveru:
* Windows Server 2012 R2 a služby IIS 8 (pro Windows Server 2008 R2, server postup se liší)

## <a name="create-the-aspnet-452-application-on-the-visual-studio-computer"></a>Vytvoření projektu ASP.NET 4.5.2 aplikace na počítači aplikace Visual Studio
  
1. Na počítači se systémem Visual Studio, zvolte **souboru** > **nový projekt**.

1. V části **Visual C#** nebo **jazyka Visual Basic**, zvolte **webové**a potom v prostředním podokně zvolte buď **webová aplikace ASP.NET (.NET Framework)** a potom klikněte na tlačítko **OK**.

    Pokud nevidíte zadaný projekt šablony, klikněte na tlačítko **otevřít instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. Spustí se instalační program pro Visual Studio. Viz požadavky v tomto článku k identifikaci požadované úlohy sady Visual Studio, které je nutné nainstalovat.

1. Zvolte **MVC** (.NET Framework) a ujistěte se, že **bez ověřování** je vybrána a potom klikněte na tlačítko **OK**.

1. Zadejte název, například **MyWebApp** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt.

1. Zvolte **sestavení** > **sestavit řešení** k sestavení projektu.

## <a name="install-and-configure-iis-on-windows-server"></a>Instalace a konfigurace služby IIS v systému Windows Server

[!INCLUDE [remote-debugger-install-iis-role](../debugger/includes/remote-debugger-install-iis-role.md)]

## <a name="update-browser-security-settings-on-windows-server"></a>Aktualizovat nastavení zabezpečení prohlížeče ve Windows serveru

Pokud je povolená konfigurace rozšířeného zabezpečení aplikace Internet Explorer (je povolená ve výchozím nastavení), budete muset přidat některé domény jako důvěryhodné servery, které chcete stáhnout, některé součásti webového serveru. Přidat důvěryhodné servery tak, že přejdete do **Možnosti Internetu** > **zabezpečení** > **důvěryhodných serverů** > **lokalit** . Přidejte následující domény.

- microsoft.com
- go.microsoft.com
- download.microsoft.com
- IIS.NET

Když si stáhnete software, se může zobrazit žádosti o udělení oprávnění k načítání různých skriptů na webu a prostředky. Některé z těchto zdrojů nejsou vyžadovány, ale pro zjednodušení procesu, klikněte na tlačítko **přidat** po zobrazení výzvy.

## <a name="install-aspnet-45-on-windows-server"></a>Instalace technologie ASP.NET 4.5 na Windows serveru

Pokud chcete podrobnější informace k instalaci technologie ASP.NET ve službě IIS, přečtěte si téma [IIS 8.0 ASP.NET 3.5 a technologii ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45).

1. V levém podokně ve Správci serveru vyberte **IIS**. Klikněte pravým tlačítkem na server a vyberte **Správce Internetové informační služby (IIS)**.

1. Pomocí instalačního programu webové platformy (WebPI) k instalaci technologie ASP.NET 4.5 (z uzlu serveru ve Windows serveru 2012 R2, zvolte **získat nové komponenty webové platformy** a vyhledejte technologie ASP.NET)

    ![RemoteDBG_IIS_AspNet_45](../debugger/media/remotedbg_iis_aspnet_45.png "RemoteDBG_IIS_AspNet_45")

    > [!NOTE]
    > Pokud používáte Windows Server 2008 R2, nainstalujte technologii ASP.NET 4 místo použití tohoto příkazu:

     **C:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -ir**

2. Restartování systému (nebo když spouští **net stop byla /y** následovaný **net start w3svc** z příkazového řádku ke sbírání změnit CESTU v systému).

## <a name="install-web-deploy-36-on-windows-server"></a>Nainstalovat Webdeploy 3.6 v systému Windows Server

[!INCLUDE [remote-debugger-install-web-deploy](../debugger/includes/remote-debugger-install-web-deploy.md)]

## <a name="configure-aspnet-web-site-on-the-windows-server-computer"></a>Konfigurace webu ASP.NET na počítač s Windows serverem

1. Otevřete Průzkumníka Windows a vytvořte novou složku **C:\Publish**, kde bude později nasadit projekt ASP.NET.

2. Pokud ho ještě není otevřený, otevřete **Správce Internetové informační služby (IIS)**. (V levém podokně ve Správci serveru vyberte **IIS**. Klikněte pravým tlačítkem na server a vyberte **Správce Internetové informační služby (IIS)**.)

3. V části **připojení** v levém podokně přejděte do **lokality**.

4. Vyberte **výchozí webový server**, zvolte **základní nastavení**a nastavte **fyzická cesta** k **C:\Publish**.

5. Klikněte pravým tlačítkem myši **výchozí webový server** uzel a vyberte možnost **přidat aplikaci**.

6. Nastavte **Alias** pole **MyASPApp**, přijměte výchozí nastavení fondu aplikací (**DefaultAppPool**) a nastavte **fyzická cesta** k  **C:\Publish**.

7. V části **připojení**vyberte **fondy aplikací**. Otevřít **DefaultAppPool** a nastavte pole fond aplikací na **ASP.NET v4.0** (ASP.NET 4.5 není možné zvolit pro fond aplikací).

8. Vybrání ve Správci služby IIS lokality vyberte **upravit oprávnění**a ujistěte se, že IUSR, IIS_IUSRS nebo uživatel nakonfigurovaný pro fond aplikací je oprávněný uživatel s oprávněními Číst a spouštět. Pokud žádný z těchto uživatelů není k dispozici, přidejte jako uživatel s oprávněním Číst a spouštět IUSR.

## <a name="publish-and-deploy-the-app-using-web-deploy-from-visual-studio"></a>Publikujte a nasaďte aplikaci pomocí nasazení webu ze sady Visual Studio

[!INCLUDE [deploy-app-web-deploy](../deployment/includes/deploy-app-web-deploy.md)]

Potřebujete také, přečtěte si následující část o odstraňování potíží porty.

## <a name="troubleshoot-open-required-ports-on-windows-server"></a>Řešení potíží: Otevřené požadované porty ve Windows serveru

Ve většině nastavení jsou otevřené požadované porty instalace technologie ASP.NET a Web Deploy. Ale budete muset ověřit, že jsou otevřené porty.

> [!NOTE]
> Na Virtuálním počítači Azure, musíte otevřít porty prostřednictvím [skupinu zabezpečení sítě](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80). 

Požadované porty:

* 80 – požadováno pro službu IIS
* 8172 - požadované pro nasazení webu k nasazování aplikací ze sady Visual Studio

1. Chcete-li otevřít port v systému Windows Server, otevřete **spustit** nabídky, vyhledejte **brány Windows Firewall s pokročilým zabezpečením**.

2. Klikněte na tlačítko **příchozí pravidla** > **nové pravidlo** > **Port**. Zvolte **Další** a v části **určité místní porty**, zadejte číslo portu, klikněte na tlačítko **Další**, pak **povolit připojení**, klikněte na tlačítko Další, a Přidat název (**IIS**, **Webdeploy**, nebo **msvsmon**) pro příchozí pravidlo.

    Pokud chcete další informace o konfiguraci brány Windows Firewall, najdete v článku [konfigurace brány Windows Firewall pro vzdálené ladění](../debugger/configure-the-windows-firewall-for-remote-debugging.md).

3. Vytvořte další pravidla pro požadované porty.

## <a name="next-steps"></a>Další kroky

V tomto kurzu se vytvoří soubor nastavení publikování, importovat do sady Visual Studio a nasazení aplikace ASP.NET do služby IIS. Můžete také nasadit pomocí importu nastavení publikování.

> [!div class="nextstepaction"]
> [Nasazení do služby IIS pomocí importu nastavení publikování](../deployment/tutorial-import-publish-settings-iis.md)
