---
title: Vzdálené ladění ASP.NET Core v počítači vzdálené služby IIS | Microsoft Docs
ms.custom: remotedebugging
ms.date: 05/21/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 573a3fc5-6901-41f1-bc87-557aa45d8858
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 607f4bb2bcce3d8895a4a07df8d70c866e7a6aab
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34746927"
---
# <a name="remote-debug-aspnet-core-on-a-remote-iis-computer-in-visual-studio-2017"></a>Vzdálené ladění ASP.NET Core na počítači vzdálené služby IIS v Visual Studio 2017
K ladění aplikace ASP.NET, která byla nasazena do služby IIS, instalaci a spuštění nástrojů pro vzdálenou na počítači, kde jste nasadili aplikace a pak připojte k běžící aplikaci ze sady Visual Studio.

![Součásti vzdáleného ladicího programu](../debugger/media/remote-debugger-aspnet.png "Remote_debugger_components")

Tato příručka vysvětluje, jak nastavit a konfigurovat Visual Studio 2017 ASP.NET Core, nasazení pro službu IIS a připojení vzdáleného ladicího programu ze sady Visual Studio. Vzdálené ladění ASP.NET 4.5.2, najdete v tématu [vzdáleného ladění ASP.NET na počítači se službou IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md). Také můžete nasazovat a ladění ve službě IIS pomocí Azure. Pro službu Azure App Service, můžete snadno nasadit a ladění předem nakonfigurované instance služby IIS a vzdáleného ladicího programu buď pomocí [ladicí program snímku](../debugger/debug-live-azure-applications.md) nebo [připojení ladicího programu z Průzkumníka serveru](../debugger/remote-debugging-azure.md).

Tyto postupy jsme otestovali na tyto konfigurace serveru:
* Windows Server 2012 R2 a služby IIS 8
* Windows Server 2016 a IIS 10

## <a name="requirements"></a>Požadavky

Mezi dvěma počítači připojené prostřednictvím proxy serveru se nepodporuje ladění. Ladění nad vysokou latencí nebo připojení s malou šířkou pásma, například telefonického Internetu, nebo přes Internet napříč zemích se nedoporučuje a může selhat nebo být příliš pomalé. Úplný seznam požadavků, najdete v části [požadavky](../debugger/remote-debugging.md#requirements_msvsmon).

## <a name="app-already-running-in-iis"></a>Aplikace už běží ve službě IIS?

Tento článek obsahuje kroky nastavení základní konfiguraci služby IIS v systému Windows server a nasazení aplikace z Visual Studia. Tyto kroky jsou zahrnuty a ujistěte se, že server má požadované součásti nainstalovat aplikaci spuštěním správně a že jste připravení vzdáleného ladění.

* Pokud vaše aplikace běží ve službě IIS a chcete stáhnout vzdáleného ladicího programu a spusťte ladění, přejděte na [stáhněte a nainstalujte nástroje pro vzdálenou v systému Windows Server](#BKMK_msvsmon).

* Pokud chcete zobrazit nápovědu k Ujistěte se, že aplikace je nastavena, nasazení a správně fungovat ve službě IIS tak, aby můžete ladit, postupujte podle pokynů v tomto tématu.

## <a name="create-the-aspnet-core-application-on-the-visual-studio-2017-computer"></a>Vytvoření aplikace ASP.NET Core v počítači Visual Studio 2017 

1. Vytvoření nové aplikace ASP.NET Core. (**Soubor > Nový > projekt**, pak vyberte **Visual C# > Web > webové aplikace ASP.NET Core**).

    V **ASP.NET Core** část šablony, vyberte **webové aplikace**.

2. Ujistěte se, že **technologii ASP.NET 2.0 základní** je vybraná, který **povolení podpory Docker** je **není** vybrané a že **ověřování** je nastaven na **Bez ověřování**.

3. Název projektu **MyASPApp** a klikněte na tlačítko **OK** k vytvoření nové řešení.

4. Otevřete soubor About.cshtml.cs a nastavte zarážky `OnGet` – metoda (v starší šablony, otevřete místo nich HomeController.cs a nastavit bod přerušení `About()` metoda).

## <a name="bkmk_configureIIS"></a> Instalace a konfigurace služby IIS v systému Windows Server

[!INCLUDE [remote-debugger-install-iis-role](../debugger/includes/remote-debugger-install-iis-role.md)]

## <a name="update-browser-security-settings-on-windows-server"></a>Aktualizovat nastavení zabezpečení prohlížeče v systému Windows Server

Pokud je konfigurace rozšířeného zabezpečení aplikace je povoleno v aplikaci Internet Explorer (je povolená ve výchozím nastavení), budete muset přidat některé domény jako důvěryhodných serverů, abyste mohli stáhnout některé součásti webového serveru. Přidání důvěryhodných serverů přechodem na **Možnosti Internetu > zabezpečení > důvěryhodných serverů > lokality**. Přidejte následující domény.

- microsoft.com
- go.microsoft.com
- download.microsoft.com
- IIS.NET

Při stahování softwaru, může dojít k žádosti o udělení oprávnění ke spouštění různých skripty webu a prostředky. Některé z těchto prostředků nejsou vyžadovány, ale chcete zjednodušit proces, klikněte na tlačítko **přidat** po zobrazení výzvy.

## <a name="install-aspnet-core-on-windows-server"></a>Instalace jádra ASP.NET v systému Windows Server

1. Nainstalujte [hostování v rozhraní .NET Core systému Windows Server](https://aka.ms/dotnetcore-2-windowshosting) sady v hostitelském systému. Sada nainstaluje .NET Core Runtime, knihovny .NET Core a modulu jádra ASP.NET. Další podrobné pokyny najdete v tématu [publikování do služby IIS](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration).

    > [!NOTE]
    > Pokud systém nemá připojení k Internetu, získejte a nainstalujte *[Microsoft Visual C++ 2015 Redistributable](https://www.microsoft.com/download/details.aspx?id=53840)* před instalací sady hostování v rozhraní .NET Core systému Windows Server.

3. Restartování systému (nebo spuštění **net stop byl /y** následuje **net start w3svc** z příkazového řádku a pokračovat tam ke změně systému cesta).

## <a name="choose-a-deployment-option"></a>Vyberte možnost nasazení

Pokud pomoc při nasazení aplikace do služby IIS, zvažte tyto možnosti:

* Nasaďte vytvořením soubor nastavení publikování ve službě IIS a importu nastavení v sadě Visual Studio. V některých scénářích to je rychlý způsob, jak nasadit vaši aplikaci. Když vytvoříte soubor nastavení publikování, oprávnění se nastaví automaticky ve službě IIS.

* Nasaďte publikování do místní složky a kopírování výstupu upřednostňovanou metodou do složky připravené aplikace ve službě IIS.

## <a name="optional-deploy-using-a-publish-settings-file"></a>(Volitelné) Nasazení pomocí soubor nastavení publikování

Tuto možnost můžete vytvořit soubor nastavení publikování a importujte ho do sady Visual Studio.

> [!NOTE]
> Tato metoda nasazení používá nasazení webu. Pokud chcete nakonfigurovat nasazení webu ručně v sadě Visual Studio místo importu nastavení, můžete nainstalovat webové nasazení 3.6 místo 3.6 nasazení webové pro hostování servery. Ale pokud ručně nakonfigurujete nasazení webu, budete muset Ujistěte se, že je aplikaci složky na serveru nakonfigurovat pomocí správné hodnoty a oprávnění (viz [nakonfigurovat web ASP.NET s](#BKMK_deploy_asp_net)).

### <a name="install-and-configure-web-deploy-for-hosting-servers-on-windows-server"></a>Instalace a konfigurace nasazení webu pro hostování servery v systému Windows Server

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/install-web-deploy-with-hosting-server.md)]

### <a name="create-the-publish-settings-file-in-iis-on-windows-server"></a>Vytvořte soubor nastavení publikování ve službě IIS v systému Windows Server

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/create-publish-settings-iis.md)]

### <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Import nastavení publikování v sadě Visual Studio a nasazení

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/import-publish-settings-vs.md)]

Po aplikaci nasadí úspěšně, by se měl spustit automaticky. Pokud aplikace se nespustí ze sady Visual Studio, spusťte aplikaci ve službě IIS. Pro ASP.NET Core, musíte zajistit, že fond aplikací pole pro **DefaultAppPool** je nastaven na **bez spravovaného kódu**.

1. V **nastavení** dialogové okno, povolte ladění kliknutím **Další**, vyberte **ladění** konfigurace a potom zvolte **odebrat další soubory v Cílový** pod **publikování souboru** možnosti.

    > [!NOTE]
    > Pokud si zvolíte konfigurace verze, můžete zakázat ladění v *web.config* souboru při publikování.

1. Klikněte na tlačítko **Uložit** a poté jej znovu publikovat aplikace.

## <a name="optional-deploy-by-publishing-to-a-local-folder"></a>(Volitelné) Nasazení pomocí publikování do místní složky

Tuto možnost můžete použít k nasazení své aplikace, pokud chcete kopírovat aplikace do služby IIS pomocí prostředí Powershell, RoboCopy, nebo chcete ručně zkopírovat soubory.

### <a name="BKMK_deploy_asp_net"></a> Konfigurace webu ASP.NET na počítač s Windows serverem

1. Otevřete Průzkumníka Windows a vytvořte novou složku, **C:\Publish**, kde později nasadíte projekt ASP.NET.

2. Pokud již není otevřený, otevřete **Správce Internetové informační služby (IIS)**. (V levém podokně Správce serveru, vyberte **IIS**. Pravým tlačítkem na server a vyberte **Správce Internetové informační služby (IIS)**.)

3. V části **připojení** v levém podokně přejděte do **lokality**.

4. Vyberte **Default Web Site**, zvolte **základní nastavení**a nastavte **fyzická cesta** k **C:\Publish**.

4. Klikněte pravým tlačítkem myši **Default Web Site** uzel a vyberte možnost **přidat aplikaci**.

5. Nastavte **Alias** do **MyASPApp**, přijměte výchozí nastavení fondu aplikací (**DefaultAppPool**) a nastavte **fyzická cesta** k  **C:\Publish**.

6. V části **připojení**, vyberte **fondy aplikací**. Otevřete **DefaultAppPool** a nastavte hodnotu pole fondu aplikací na **bez spravovaného kódu**.

7. Klikněte pravým tlačítkem na novou lokalitu ve Správci služby IIS, zvolte **upravit oprávnění**a ujistěte se, že IUSR, IIS_IUSRS nebo uživatel nakonfigurovaný pro přístup do webové aplikace je oprávněný uživatel s oprávněními Číst a spouštět.

    Pokud nevidíte jeden z těchto uživatelů s přístupem, projít kroky k přidání IUSR jako uživatel s právy ke čtení a spouštění.

### <a name="publish-and-deploy-the-app-by-publishing-to-a-local-folder-from-visual-studio"></a>Publikujte a nasaďte aplikaci pomocí publikování do místní složky ze sady Visual Studio

Můžete také publikovat a nasazení aplikace pomocí systému souborů nebo jiných nástrojů.

[!INCLUDE [remote-debugger-deploy-app-local](../debugger/includes/remote-debugger-deploy-app-local.md)]

## <a name="BKMK_msvsmon"></a> Stáhněte a nainstalujte nástroje pro vzdálenou v systému Windows Server

V tomto kurzu používáme Visual Studio 2017.

Pokud máte potíže při otevření stránky s stahování vzdáleného ladicího programu, najdete v části [odblokovat stahování souboru](../debugger/remote-debugging.md#unblock_msvsmon) nápovědu.

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

> [!TIP]
> V některých případech může být nejúčinnější ke spuštění vzdáleného ladicího programu ze sdílené složky. Další informace najdete v tématu [spuštění vzdáleného ladicího programu ze sdílené složky](../debugger/remote-debugging.md#fileshare_msvsmon).
  
## <a name="BKMK_setup"></a> Nastavení vzdáleného ladicího programu v systému Windows Server

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> Pokud potřebujete přidat oprávnění pro všechny další uživatele, změna režimu ověřování, nebo číslo portu pro vzdáleného ladicího programu, najdete v části [konfigurovat vzdálený ladicí program](../debugger/remote-debugging.md#configure_msvsmon).

Informace o spuštění jako služba vzdáleného ladicího programu najdete v tématu [spuštěn jako služba vzdáleného ladicího programu](../debugger/remote-debugging.md#bkmk_configureService).

## <a name="BKMK_attach"></a> Připojení k aplikaci ASP.NET z počítače, Visual Studio

1. Na počítači, Visual Studio, otevřete řešení, které se pokoušíte ladění (**MyASPApp** Pokud jsou proveďte všechny kroky v tomto článku).
2. V sadě Visual Studio, klikněte na tlačítko **ladění > připojit k procesu** (Ctrl + Alt + P).

    > [!TIP]
    > V aplikaci Visual Studio 2017, může do stejného procesu dříve připojen k pomocí připojte **ladění > připojte k procesu...** (Shift + Alt + P). 

3. Nastavte hodnotu pole kvalifikátor na  **\<název vzdáleného počítače >: 4022**.
4. Klikněte na tlačítko **aktualizovat**.
    Měli byste vidět některé procesy, které se zobrazí v **dostupné procesy** okno.

    Pokud nevidíte žádné procesy, zkuste pomocí IP adresy místo název vzdáleného počítače (port je vyžadováno). Můžete použít `ipconfig` v příkazovém řádku, potřebujete adresu IPv4.

    Pokud chcete použít **najít** tlačítko, budete muset [otevřete UDP port 3702](#bkmk_openports) na serveru.

5. Zkontrolujte **Zobrazit procesy od všech uživatelů**.
6. Zadejte první písmeno názvu procesu a rychle tak najít **dotnet.exe** (pro ASP.NET Core).

    ![RemoteDBG_AttachToProcess](../debugger/media/remotedbg_attachtoprocess_aspnetcore.png "RemoteDBG_AttachToProcess")

7. Klikněte na tlačítko **připojit**.

8. Otevřete web vzdáleného počítače. V prohlížeči přejděte na **http://\<název vzdáleného počítače >**.
    
    Měli byste vidět webová stránka ASP.NET.

9. V běžící aplikaci ASP.NET, klikněte na odkaz **o** stránky.

    Zarážce by měl být dosáhl v sadě Visual Studio.

## <a name="bkmk_openports"></a> Řešení potíží: Otevřete požadované porty v systému Windows Server

Ve většině nastavení jsou otevřené požadované porty při instalaci ASP.NET a vzdáleného ladicího programu. Potřebujete však ověřte, že jsou otevřené porty.

> [!NOTE]
> Ve virtuálním počítači Azure, musíte otevřít porty prostřednictvím [skupinu zabezpečení sítě](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80). 

Požadované porty:

- 80 - požadované pro službu IIS
- 4022 - požadované pro vzdálené ladění z Visual Studio 2017 (viz [přiřazení portu vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md) podrobné informace.
- 8172 – (volitelné) vyžaduje se pro nasazení webu pro nasazení aplikace z Visual Studia.
- UDP 3702 - port (volitelné) zjišťování umožňuje **najít** tlačítko při připojování k vzdáleného ladicího programu v sadě Visual Studio.

1. Chcete-li otevřít port v systému Windows Server, otevřete **spustit** nabídky, vyhledejte **brány Windows Firewall s pokročilým zabezpečením**.

2. Zvolte **příchozí pravidla > nové pravidlo > Port**a potom klikněte na **Další**. (UDP 3702, zvolte **odchozí pravidla** místo.)

3. V části **určité místní porty**, zadejte číslo portu, klikněte na **Další**.

4. Klikněte na tlačítko **povolit připojení**, klikněte na tlačítko **Další**.

5. Vyberte jeden nebo více typů sítě povolit pro port a klikněte na tlačítko **Další**.

    Typ, který jste vybrali musí zahrnovat sítě, ke které je připojený vzdáleného počítače.
6. Přidejte název (například **IIS**, **Web Deploy**, nebo **msvsmon**) pro příchozí pravidlo a klikněte na tlačítko **Dokončit**.

    Měli byste vidět nové pravidlo v seznamu pravidel příchozí nebo odchozí pravidla.

    Pokud chcete další informace o konfiguraci brány Windows Firewall, najdete v části [konfigurace brány Windows Firewall pro vzdálené ladění](../debugger/configure-the-windows-firewall-for-remote-debugging.md).

3. Vytvořte další pravidla pro požadované porty.
