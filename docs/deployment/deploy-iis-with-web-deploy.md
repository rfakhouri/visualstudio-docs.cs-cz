---
title: Nasazení technologie ASP.NET do služby IIS pomocí nástroje nasazení webu
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
ms.openlocfilehash: a63d9947f544ddff1de81aaf34ed62c9646fba3d
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/05/2018
ms.locfileid: "34794224"
---
# <a name="deploy-aspnet-to-a-remote-iis-computer-using-web-deploy-in-visual-studio"></a>Nasazení technologie ASP.NET do vzdáleného počítače IIS pomocí nástroje nasazení webu v sadě Visual Studio

Tento článek vysvětluje, jak nastavit a konfigurovat aplikaci Visual Studio 2017 ASP.NET MVC 4.5.2 a nasadíte ho do služby IIS. Tento článek obsahuje kroky nastavení základní konfiguraci služby IIS v systému Windows server a nasazení aplikace z Visual Studia. Tyto kroky jsou zahrnuty a ujistěte se, že server má požadované součásti nainstalované a že jste připravení nasadit. Pokud nasazujete aplikaci ASP.NET Core, některé kroky se liší. Nasazení aplikace ASP.NET Core najdete v tématu [publikování aplikace do služby IIS pomocí importu nastavení publikování](../deployment/tutorial-import-publish-settings-iis.md) pokyny. V některých scénářích ASP.NET a ASP.NET Core je rychlejší nasazení do služby IIS pomocí importu nastavení publikování.

Tyto postupy jsme otestovali na tyto konfigurace serveru:
* Windows Server 2012 R2 a služby IIS 8 (pro Windows Server 2008 R2, server postup se liší)

## <a name="create-the-aspnet-452-application-on-the-visual-studio-computer"></a>Vytvoření projektu ASP.NET 4.5.2 aplikace na počítači Visual Studio
  
1. V počítači s Visual Studio, vyberte **soubor > Nový projekt**.

1. V části **Visual C#** nebo **jazyka Visual Basic**, zvolte **webové**a potom v prostředním podokně vyberte buď **webové aplikace ASP.NET (rozhraní .NET Framework)** a pak klikněte na **OK**.

    Pokud nevidíte šablony zadaného projektu, klikněte **otevřete instalační program Visual Studio** odkaz v levém podokně **nový projekt** dialogové okno. Spustí se instalační program pro Visual Studio. Viz požadavky v tomto článku k identifikaci požadované sadě Visual Studio úloh, které je nutné nainstalovat.

1. Zvolte **MVC** (rozhraní .NET Framework) a ujistěte se, že **bez ověřování** je vybrána a potom klikněte na **OK**.

1. Zadejte název jako **MyWebApp** a klikněte na tlačítko **OK**.

    Visual Studio vytvoří projekt.

1. Zvolte **sestavení > Sestavit řešení** a tím projekt sestavit.

## <a name="bkmk_configureIIS"></a> Instalace a konfigurace služby IIS v systému Windows Server

[!INCLUDE [remote-debugger-install-iis-role](../debugger/includes/remote-debugger-install-iis-role.md)]

## <a name="update-browser-security-settings-on-windows-server"></a>Aktualizovat nastavení zabezpečení prohlížeče v systému Windows Server

Pokud je konfigurace rozšířeného zabezpečení aplikace je povoleno v aplikaci Internet Explorer (je povolená ve výchozím nastavení), budete muset přidat některé domény jako důvěryhodných serverů, abyste mohli stáhnout některé součásti webového serveru. Přidání důvěryhodných serverů přechodem na **Možnosti Internetu > zabezpečení > důvěryhodných serverů > lokality**. Přidejte následující domény.

- microsoft.com
- go.microsoft.com
- download.microsoft.com
- IIS.NET

Při stahování softwaru, může dojít k žádosti o udělení oprávnění ke spouštění různých skripty webu a prostředky. Některé z těchto prostředků nejsou vyžadovány, ale chcete zjednodušit proces, klikněte na tlačítko **přidat** po zobrazení výzvy.

## <a name="BKMK_deploy_asp_net"></a> Instalace technologie ASP.NET 4.5 na Windows serveru

Pokud potřebujete podrobnější informace k instalaci technologie ASP.NET ve službě IIS, najdete v části [IIS 8.0 pomocí technologie ASP.NET 3.5 a technologii ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45).

1. V levém podokně Správce serveru, vyberte **IIS**. Pravým tlačítkem na server a vyberte **Správce Internetové informační služby (IIS)**.

1. Instalace webové platformy (WebPI) použít k instalaci technologie ASP.NET 4.5 (z uzlu serveru v systému Windows Server 2012 R2, zvolte **získat nové komponenty webové platformy** a poté vyhledejte ASP.NET)

    ![RemoteDBG_IIS_AspNet_45](../debugger/media/remotedbg_iis_aspnet_45.png "RemoteDBG_IIS_AspNet_45")

    > [!NOTE]
    > Pokud používáte Windows Server 2008 R2, nainstalujte technologii ASP.NET 4 místo použití tohoto příkazu:

     **C:\Windows\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe -ir**

2. Restartování systému (nebo spuštění **net stop byl /y** následuje **net start w3svc** z příkazového řádku a pokračovat tam ke změně systému cesta).

## <a name="BKMK_install_webdeploy"></a> Nasazení webu instalace 3.6 v systému Windows Server

[!INCLUDE [remote-debugger-install-web-deploy](../debugger/includes/remote-debugger-install-web-deploy.md)]

## <a name="BKMK_deploy_asp_net"></a> Konfigurace webu ASP.NET na počítač s Windows serverem

1. Otevřete Průzkumníka Windows a vytvořte novou složku, **C:\Publish**, kde později nasadíte projekt ASP.NET.

2. Pokud již není otevřený, otevřete **Správce Internetové informační služby (IIS)**. (V levém podokně Správce serveru, vyberte **IIS**. Pravým tlačítkem na server a vyberte **Správce Internetové informační služby (IIS)**.)

3. V části **připojení** v levém podokně přejděte do **lokality**.

4. Vyberte **Default Web Site**, zvolte **základní nastavení**a nastavte **fyzická cesta** k **C:\Publish**.

5. Klikněte pravým tlačítkem myši **Default Web Site** uzel a vyberte možnost **přidat aplikaci**.

6. Nastavte **Alias** do **MyASPApp**, přijměte výchozí nastavení fondu aplikací (**DefaultAppPool**) a nastavte **fyzická cesta** k  **C:\Publish**.

7. V části **připojení**, vyberte **fondy aplikací**. Otevřete **DefaultAppPool** a nastavte hodnotu pole fondu aplikací na **ASP.NET v4.0** (ASP.NET 4.5 není možnost pro fond aplikací).

8. S lokalitou vybrané ve Správci služby IIS, zvolte **upravit oprávnění**a ujistěte se, že IUSR, IIS_IUSRS nebo uživateli nakonfigurovanému pro fond aplikací je oprávněný uživatel s oprávněními Číst a spouštět. Pokud žádná z těchto uživatelů jsou v něm, přidejte jako uživatel s právy ke čtení a spouštění IUSR.

## <a name="bkmk_webdeploy"></a> Publikujte a nasaďte aplikace pomocí nasazení webu ze sady Visual Studio

[!INCLUDE [deploy-app-web-deploy](../deployment/includes/deploy-app-web-deploy.md)]

Navíc budete muset přečíst v části na [řešení potíží s porty](#bkmk_openports).

## <a name="bkmk_openports"></a> Řešení potíží: Otevřete požadované porty v systému Windows Server

Ve většině nastavení jsou otevřené požadované porty při instalaci ASP.NET a nástroje nasazení webu. Potřebujete však ověřte, že jsou otevřené porty.

> [!NOTE]
> Ve virtuálním počítači Azure, musíte otevřít porty prostřednictvím [skupinu zabezpečení sítě](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80). 

Požadované porty:

* 80 - požadované pro službu IIS
* 8172 - požadované pro nasazení webu pro nasazení aplikace z Visual Studia

1. Chcete-li otevřít port v systému Windows Server, otevřete **spustit** nabídky, vyhledejte **brány Windows Firewall s pokročilým zabezpečením**.

2. Zvolte **příchozí pravidla > nové pravidlo > Port**. Zvolte **Další** a v části **určité místní porty**, zadejte číslo portu, klikněte na **Další**, pak **povolit připojení**, klikněte na tlačítko Další, a Přidejte název (**IIS**, **Web Deploy**, nebo **msvsmon**) pro příchozí pravidlo.

    Pokud chcete další informace o konfiguraci brány Windows Firewall, najdete v části [konfigurace brány Windows Firewall pro vzdálené ladění](../debugger/configure-the-windows-firewall-for-remote-debugging.md).

3. Vytvořte další pravidla pro požadované porty.

## <a name="next-steps"></a>Další kroky

V tomto kurzu vytvořili soubor nastavení publikování, importovat do sady Visual Studio a nasazení aplikace ASP.NET do služby IIS. Můžete taky nasadit pomocí importu nastavení publikování.

> [!div class="nextstepaction"]
> [Nasazení do služby IIS pomocí importu nastavení publikování](../deployment/tutorial-import-publish-settings-iis.md)