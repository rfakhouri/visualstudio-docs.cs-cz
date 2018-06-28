---
title: Vzdálené ladění jádra ASP.NET na IIS a Azure | Microsoft Docs
ms.custom: remotedebugging
ms.date: 05/21/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: a6c04b53-d1b9-4552-a8fd-3ed6f4902ce6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- aspnet
- dotnetcore
- azure
ms.openlocfilehash: cc889accc116fb2115ae56155a190ed6ea2d3fc0
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37058438"
---
# <a name="remote-debug-aspnet-core-on-iis-in-azure-in-visual-studio-2017"></a>Vzdálené ladění jádra ASP.NET ve službě IIS v Azure v Visual Studio 2017

Tato příručka vysvětluje, jak nastavit a konfigurace aplikace Visual Studio 2017 ASP.NET Core, ho nasadit do Azure pomocí služby IIS a připojení vzdáleného ladicího programu ze sady Visual Studio.

Doporučený způsob vzdáleného ladění na platformě Azure, závisí na váš scénář:

* K ladění ASP.NET Core v Azure App Service, najdete v části [Azure ladění aplikace pomocí ladicího programu snímku](../debugger/debug-live-azure-applications.md). Toto je doporučená metoda.
* Chcete-li ladit ASP.NET Core v Azure App Service pomocí funkce tradičnější ladění, postupujte podle kroků v tomto tématu (naleznete v části [vzdáleného ladění na Azure App Service](#remote_debug_azure_app_service)).

    V tomto scénáři je nutné nasadit aplikace do Azure ze sady Visual Studio, ale není potřeba ručně instalaci nebo konfiguraci služby IIS nebo vzdáleného ladicího programu (tyto součásti jsou reprezentované pomocí čáry s koncovými body), jak je znázorněno na následujícím obrázku.

    ![Součásti vzdáleného ladicího programu](../debugger/media/remote-debugger-azure-app-service.png "Remote_debugger_components")

* K ladění služby IIS na virtuální počítač Azure, postupujte podle kroků v tomto tématu (naleznete v části [vzdáleného ladění na virtuální počítač Azure](#remote_debug_azure_vm)). To umožňuje použít vlastní konfiguraci služby IIS, ale kroky instalace a nasazení jsou složitější.

    Pro virtuální počítač Azure je nutné nasadit aplikace do Azure ze sady Visual Studio a také musíte ručně nainstalovat roli služby IIS a vzdáleného ladicího programu, jak je znázorněno na následujícím obrázku.

    ![Součásti vzdáleného ladicího programu](../debugger/media/remote-debugger-azure-vm.png "Remote_debugger_components")

* Chcete-li ladit ASP.NET Core na Azure Service Fabric, přečtěte si téma [ladění vzdálené aplikace Service Fabric](/azure/service-fabric/service-fabric-debugging-your-application#debug-a-remote-service-fabric-application).

> [!WARNING]
> Nezapomeňte odstranit prostředky Azure, které vytvoříte, když jste dokončili kroky v tomto kurzu. Tímto způsobem můžete účtovány poplatky zbytečné.


### <a name="requirements"></a>Požadavky

Mezi dvěma počítači připojené prostřednictvím proxy serveru se nepodporuje ladění. Ladění nad vysokou latencí nebo připojení s malou šířkou pásma, jako je například telefonického Internetu, nebo přes Internet napříč zemích se nedoporučuje a může selhat nebo být příliš pomalé. Úplný seznam požadavků, najdete v části [požadavky](../debugger/remote-debugging.md#requirements_msvsmon).

## <a name="create-the-aspnet-core-application-on-the-visual-studio-2017-computer"></a>Vytvoření aplikace ASP.NET Core v počítači Visual Studio 2017 

1. Vytvoření nové aplikace ASP.NET Core. (Vyberte **soubor > Nový > projekt**, pak vyberte **Visual C# > Web > webové aplikace ASP.NET Core**).

    V **ASP.NET Core** část šablony, vyberte **webové aplikace**.

2. Ujistěte se, že **technologii ASP.NET 2.0 základní** je vybraná, který **povolení podpory Docker** je **není** vybrané a že **ověřování** je nastaven na **Bez ověřování**.

3. Název projektu **MyASPApp** a klikněte na tlačítko **OK** k vytvoření nové řešení.

4. Otevřete soubor About.cshtml.cs a nastavte zarážky `OnGet` – metoda (v starší šablony, otevřete místo nich HomeController.cs a nastavit bod přerušení `About()` metoda).

## <a name="remote_debug_azure_app_service"></a> Vzdálené ladění ASP.NET Core v Azure App Service

Ze sady Visual Studio můžete rychle publikovat a ladění aplikace do zcela zřizované instance služby IIS. Ale je přednastavení konfiguraci služby IIS a si nemůžete přizpůsobit. Další podrobné pokyny naleznete v tématu [nasazení webové aplikace ASP.NET Core do Azure pomocí sady Visual Studio](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs). (Pokud potřebujete vlastní nastavení služby IIS, vyzkoušejte ladění na [virtuálního počítače Azure](#remote_debug_azure_vm).) 

#### <a name="to-deploy-the-app-and-remote-debug-using-server-explorer"></a>K nasazení aplikace a vzdálené ladění pomocí Průzkumníka serveru

1. V sadě Visual Studio, klikněte pravým tlačítkem na uzel projektu a zvolte **publikovat**.

    Pokud jste dříve nakonfigurovali žádné profily publikování **publikovat** podokně se zobrazí. Klikněte na tlačítko **nový profil**.

1. Zvolte **Azure App Service** z **publikovat** dialogové okno, vyberte **vytvořit nový**a postupujte podle pokynů k publikování.

    Podrobné pokyny najdete v tématu [nasazení webové aplikace ASP.NET Core do Azure pomocí sady Visual Studio](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs).

    ![Publikování do Azure App Service](../debugger/media/remotedbg_azure_app_service_profile.png)

1. Otevřete **Průzkumníka serveru** (**zobrazení** > **Průzkumníka serveru**), klikněte pravým tlačítkem myši na instanci služby App Service a zvolte **připojit ladicí program**.

1. V běžící aplikaci ASP.NET, klikněte na odkaz **o** stránky.

    Zarážce by měl být dosáhl v sadě Visual Studio.

    Je to! Další kroky v tomto tématu se týkají vzdáleného ladění na virtuální počítač Azure.

## <a name="remote_debug_azure_vm"></a> Vzdálené ladění ASP.NET Core ve virtuálním počítači Azure

Můžete vytvořit virtuální počítač Azure pro Windows Server a pak nainstalovat a nakonfigurovat službu IIS a ostatní součásti požadovaný software. To trvá déle než nasazení Azure App Service a vyžaduje proveďte zbývající kroky v tomto kurzu.

První, postupujte podle pokynů popsaných v [instalace a spuštění služby IIS](/azure/virtual-machines/windows/quick-create-portal).

Když otevřete port 80 ve skupině zabezpečení sítě, také otevřete port 4022 pro vzdáleného ladicího programu. Tímto způsobem, nebudete muset otevřít později.

### <a name="app-already-running-in-iis-on-the-azure-vm"></a>Aplikaci již spuštěnou ve službě IIS na virtuální počítač Azure?

Tento článek obsahuje kroky nastavení základní konfiguraci služby IIS v systému Windows server a nasazení aplikace z Visual Studia. Tyto kroky jsou zahrnuty a ujistěte se, zda má server požadované součásti nainstalovat aplikaci spuštěním správně a že jste připravení vzdáleného ladění.

* Pokud vaše aplikace běží ve službě IIS a chcete stáhnout vzdáleného ladicího programu a spusťte ladění, přejděte na [stáhněte a nainstalujte nástroje pro vzdálenou v systému Windows Server](#BKMK_msvsmon).

* Pokud chcete zobrazit nápovědu k Ujistěte se, že aplikace je nastavena, nasazení a správně fungovat ve službě IIS tak, aby můžete ladit, postupujte podle pokynů v tomto tématu.

### <a name="update-browser-security-settings-on-windows-server"></a>Aktualizovat nastavení zabezpečení prohlížeče v systému Windows Server

Pokud je konfigurace rozšířeného zabezpečení aplikace je povoleno v aplikaci Internet Explorer (je povolená ve výchozím nastavení), budete muset přidat některé domény jako důvěryhodných serverů, abyste mohli stáhnout některé součásti webového serveru. Přidání důvěryhodných serverů přechodem na **Možnosti Internetu > zabezpečení > důvěryhodných serverů > lokality**. Přidejte následující domény.

- microsoft.com
- go.microsoft.com
- download.microsoft.com
- IIS.NET

Při stahování softwaru, může dojít k žádosti o udělení oprávnění ke spouštění různých skripty webu a prostředky. Některé z těchto prostředků nejsou vyžadovány, ale chcete zjednodušit proces, klikněte na tlačítko **přidat** po zobrazení výzvy.

### <a name="install-aspnet-core-on-windows-server"></a>Instalace jádra ASP.NET v systému Windows Server

1. Nainstalujte [hostování v rozhraní .NET Core systému Windows Server](https://aka.ms/dotnetcore-2-windowshosting) sady v hostitelském systému. Sady nainstaluje rozhraní .NET Core Runtime, knihovny .NET Core a modulu jádra ASP.NET. Další podrobné pokyny najdete v tématu [publikování do služby IIS](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration).

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

Při importu nastavení publikování, můžete tuto část přeskočit.

1. Otevřete **Správce Internetové informační služby (IIS)** a přejděte na **lokality**.

2. Klikněte pravým tlačítkem myši **Default Web Site** uzel a vyberte možnost **přidat aplikaci**.

3. Nastavte **Alias** do **MyASPApp** a pole fondu aplikací, které chcete **bez spravovaného kódu**. Nastavte **fyzická cesta** k **C:\Publish** (kde později nasadíte projekt ASP.NET).

4. S lokalitou vybrané ve Správci služby IIS, zvolte **upravit oprávnění**a ujistěte se, že IUSR, IIS_IUSRS nebo uživateli nakonfigurovanému pro fond aplikací je oprávněný uživatel s oprávněními Číst a spouštět.

    Pokud nevidíte jeden z těchto uživatelů s přístupem, projít kroky k přidání IUSR jako uživatel s právy ke čtení a spouštění.

### <a name="optional-publish-and-deploy-the-app-by-publishing-to-a-local-folder-from-visual-studio"></a>(Volitelné) Publikujte a nasaďte aplikaci pomocí publikování do místní složky ze sady Visual Studio

Pokud nepoužíváte nasazení webu, musíte publikovat a nasazení aplikace pomocí systému souborů nebo jiných nástrojů. Začněte vytvořením balíčku pomocí systému souborů a potom můžete buď balíček nasadit ručně nebo použít jiné nástroje, například PowerShell, XCopy nebo RoboCopy. V této části předpokládáme, že jsou ruční kopírování balíčku, pokud nepoužíváte nasazení webu.

[!INCLUDE [remote-debugger-deploy-app-local](../debugger/includes/remote-debugger-deploy-app-local.md)]

### <a name="BKMK_msvsmon"></a> Stáhněte a nainstalujte nástroje pro vzdálenou v systému Windows Server

V tomto kurzu používáme Visual Studio 2017.

Pokud máte potíže při otevření stránky s stahování vzdáleného ladicího programu, najdete v části [odblokovat stahování souboru](../debugger/remote-debugging.md#unblock_msvsmon) nápovědu.

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
### <a name="BKMK_setup"></a> Nastavení vzdáleného ladicího programu v systému Windows Server

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> Pokud potřebujete přidat oprávnění pro všechny další uživatele, změna režimu ověřování, nebo číslo portu pro vzdáleného ladicího programu, najdete v části [konfigurovat vzdálený ladicí program](../debugger/remote-debugging.md#configure_msvsmon).

### <a name="BKMK_attach"></a> Připojení k aplikaci ASP.NET z počítače, Visual Studio

1. Na počítači, Visual Studio, otevřete řešení, které se pokoušíte ladění (**MyASPApp** pokud postupujete podle kroků v tomto článku).
2. V sadě Visual Studio, klikněte na tlačítko **ladění > připojit k procesu** (Ctrl + Alt + P).

    > [!TIP]
    > V aplikaci Visual Studio 2017 lze znovu připojit do stejného procesu dříve připojen k pomocí **ladění > připojte k procesu...** (Shift + Alt + P). 

3. Nastavte hodnotu pole kvalifikátor na  **\<název vzdáleného počítače >: 4022**.
4. Klikněte na tlačítko **aktualizovat**.
    Měli byste vidět některé procesy, které se zobrazí v **dostupné procesy** okno.

    Pokud nevidíte žádné procesy, zkuste pomocí IP adresy místo název vzdáleného počítače (port je vyžadováno). Můžete použít `ipconfig` v příkazovém řádku, potřebujete adresu IPv4.

    Pokud chcete použít **najít** tlačítko, budete muset [otevřete UDP port 3702](#bkmk_openports) na serveru.

5. Zkontrolujte **Zobrazit procesy od všech uživatelů**.

6. Zadejte první písmeno názvu procesu a rychle tak najít *dotnet.exe* (pro ASP.NET Core).
   
   Pro aplikace ASP.NET Core předchozí název procesu byla *dnx.exe*.

    ![RemoteDBG_AttachToProcess](../debugger/media/remotedbg_attachtoprocess_aspnetcore.png "RemoteDBG_AttachToProcess")

7. Klikněte na tlačítko **připojit**.

8. Otevřete web vzdáleného počítače. V prohlížeči přejděte na **http://\<název vzdáleného počítače >**.
    
    Měli byste vidět webová stránka ASP.NET.
9. V běžící aplikaci ASP.NET, klikněte na odkaz **o** stránky.

    Zarážce by měl být dosáhl v sadě Visual Studio.

### <a name="bkmk_openports"></a> Řešení potíží: Otevřete požadované porty v systému Windows Server

Ve většině nastavení jsou otevřené požadované porty při instalaci ASP.NET a vzdáleného ladicího programu. Ale Pokud řešíte problémy při nasazení a aplikace se nachází za bránou firewall, musíte ověřit, že jsou otevřené správné porty.

Ve virtuálním počítači Azure, musíte otevřít porty prostřednictvím [skupinu zabezpečení sítě](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80-for-web-traffic). 

Požadované porty:

- 80 - požadované pro službu IIS
- 4022 - požadované pro vzdálené ladění z Visual Studio 2017 (viz [přiřazení portu vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md) Další informace).
- UDP 3702 - port (volitelné) zjišťování umožňuje **najít** tlačítko při připojování k vzdáleného ladicího programu v sadě Visual Studio.

Kromě toho, tyto porty musí být otevřen již při instalaci ASP.NET:
- 8172 – (volitelné) požadované pro nasazení webu pro nasazení aplikace z Visual Studia

