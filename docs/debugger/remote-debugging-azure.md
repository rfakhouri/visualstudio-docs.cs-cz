---
title: Vzdálené ladění jádra ASP.NET na IIS a Azure | Microsoft Docs
ms.custom: remotedebugging
ms.date: 08/14/2017
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
ms.openlocfilehash: 3a6e25d98c2560c9cfd6901d30a7a5252398f6fc
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
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

Ze sady Visual Studio můžete rychle publikovat a ladění aplikace do zcela zřizované instance služby IIS. Ale je přednastavení konfiguraci služby IIS a si nemůžete přizpůsobit. Další podrobné pokyny naleznete v tématu [nasazení webové aplikace ASP.NET Core do Azure pomocí sady Visual Studio](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs). (Pokud potřebujete vlastní nastavení služby IIS, vyzkoušejte ladění na [virtuálního počítače Azure](#BKMK_azure_vm).) 

#### <a name="to-deploy-the-app-and-remote-debug-using-server-explorer"></a>K nasazení aplikace a vzdálené ladění pomocí Průzkumníka serveru

1. V sadě Visual Studio, klikněte pravým tlačítkem na uzel projektu a zvolte **publikovat**.

2. Zvolte **Microsoft Azure App Service** z **publikovat** dialogové okno, vyberte **vytvořit nový**a postupujte podle pokynů k publikování.

    Podrobné pokyny najdete v tématu [nasazení webové aplikace ASP.NET Core do Azure pomocí sady Visual Studio](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs).

3. Otevřete **Průzkumníka serveru** (**zobrazení** > **Průzkumníka serveru**), klikněte pravým tlačítkem myši na instanci služby App Service a zvolte **připojit ladicí program**.

4. V běžící aplikaci ASP.NET, klikněte na odkaz **o** stránky.

    Zarážce by měl být dosáhl v sadě Visual Studio.

    Je to! Další kroky v tomto tématu se týkají vzdáleného ladění na virtuální počítač Azure.

## <a name="remote_debug_azure_vm"></a> Vzdálené ladění ASP.NET Core ve virtuálním počítači Azure

Můžete vytvořit virtuální počítač Azure pro Windows Server a pak nainstalovat a nakonfigurovat službu IIS a ostatní součásti požadovaný software. To trvá déle než nasazení Azure App Service a vyžaduje proveďte zbývající kroky v tomto kurzu.

První, postupujte podle pokynů popsaných v [instalace a spuštění služby IIS](/azure/virtual-machines/windows/quick-create-portal).

Když otevřete port 80 ve skupině zabezpečení sítě, také otevřete port 4022 pro vzdáleného ladicího programu. Tímto způsobem, nebudete muset otevřít později.

### <a name="update-browser-security-settings-on-windows-server"></a>Aktualizovat nastavení zabezpečení prohlížeče v systému Windows Server

V závislosti na nastavení zabezpečení prohlížeče ho může ušetřit čas přidat následující důvěryhodných serverů na prohlížeč, abyste rychleji si můžete stáhnout software popsané v tomto kurzu. Může být potřeba přístup k těchto lokalit:

- microsoft.com
- go.microsoft.com
- download.microsoft.com
- visualstudio.com
- IIS.NET

Pokud používáte Internet Explorer, můžete přidat důvěryhodných serverů přechodem na **Možnosti Internetu > zabezpečení > důvěryhodných serverů > lokality**. Tyto kroky jsou u jiných prohlížečů. (Pokud budete muset stáhnout starší verze vzdáleného ladicího programu z my.visualstudio.com, některé další důvěryhodných serverů jsou nutné k přihlášení.)

Při stahování softwaru, může dojít k žádosti o udělení oprávnění ke spouštění různých skripty webu a prostředky. Ve většině případů není tyto další prostředky nutné k instalaci softwaru.

### <a name="install-aspnet-core-on-windows-server"></a>Instalace jádra ASP.NET v systému Windows Server

1. Nainstalujte [hostování v rozhraní .NET Core systému Windows Server](https://aka.ms/dotnetcore-2-windowshosting) sady v hostitelském systému. Sady nainstaluje rozhraní .NET Core Runtime, knihovny .NET Core a modulu jádra ASP.NET. Další podrobné pokyny najdete v tématu [publikování do služby IIS](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration).

    > [!NOTE]
    > Pokud systém nemá připojení k Internetu, získejte a nainstalujte *[Microsoft Visual C++ 2015 Redistributable](https://www.microsoft.com/download/details.aspx?id=53840)* před instalací sady hostování v rozhraní .NET Core systému Windows Server.

3. Restartování systému (nebo spuštění **net stop byl /y** následuje **net start w3svc** z příkazového řádku a pokračovat tam ke změně systému cesta).

### <a name="BKMK_install_webdeploy"></a> (Volitelné) Nasazení webu instalace 3.6 v systému Windows Server

[!INCLUDE [remote-debugger-install-web-deploy](../debugger/includes/remote-debugger-install-web-deploy.md)]

### <a name="BKMK_deploy_asp_net"></a> Konfigurace webu ASP.NET na počítač s Windows serverem

1. Otevřete **Správce Internetové informační služby (IIS)** a přejděte na **lokality**.

2. Klikněte pravým tlačítkem myši **Default Web Site** uzel a vyberte možnost **přidat aplikaci**.

3. Nastavte **Alias** do **MyASPApp** a pole fondu aplikací, které chcete **bez spravovaného kódu**. Nastavte **fyzická cesta** k **C:\Publish** (kde později nasadíte projekt ASP.NET).

4. S lokalitou vybrané ve Správci služby IIS, zvolte **upravit oprávnění**a ujistěte se, že IUSR, IIS_IUSRS nebo uživateli nakonfigurovanému pro fond aplikací je oprávněný uživatel s oprávněními Číst a spouštět.

    Pokud nevidíte jeden z těchto uživatelů s přístupem, projít kroky k přidání IUSR jako uživatel s právy ke čtení a spouštění.

### <a name="bkmk_webdeploy"></a> (Volitelné) Publikujte a nasaďte aplikace pomocí nasazení webu ze sady Visual Studio

Pokud jste nainstalovali, nasazení webu pomocí služby instalace webové platformy, můžete nasadit aplikace přímo ze sady Visual Studio.

1. Spuštění sady Visual Studio se zvýšenými oprávněními a znovu ho otevřete projektu.

    To může být nutné k nasazení vaší aplikace pomocí nástroje nasazení webu.

2. V **Průzkumníku řešení**, klikněte pravým tlačítkem na uzel projektu a vyberte **publikovat**.

3. Pro **vyberte cíl publikování**, vyberte **virtuální počítač Microsoft Azure** a klikněte na tlačítko **publikovat**.

    ![RemoteDBG_Publish_IISl](../debugger/media/remotedbg_azure_vm_profile.png "RemoteDBG_Publish_IIS")

4. V dialogovém okně vyberte virtuální počítač Azure, který jste vytvořili dříve.

4. Zadejte parametry konfigurace oprava pro nastavení virtuálního počítače Azure a služby IIS.

    ![RemoteDBG_Publish_WebDeployl](../debugger/media/remotedbg_iis_webdeploy_config.png "RemoteDBG_Publish_WebDeploy")

    Pokud název hostitele se nepřekládá při pokusu o ověření v další kroky **Server** textové pole, zkuste IP adresu. Nezapomeňte použít port 80 v **Server** textové pole a ujistěte se, že port 80 je otevřen v bráně firewall.

6. Klikněte na tlačítko **Další**, vyberte **ladění** konfigurace a zvolte **odebrat další soubory v cílovém umístění** pod **publikování souboru** Možnosti.

5. Klikněte na tlačítko **Prev**a potom zvolte **ověřením**. Pokud nastavení připojení ověří, můžete použít k publikování.

6. Klikněte na tlačítko **publikovat** k publikování aplikace.

    Karta Výstup se zobrazí, pokud je úspěšné publikování a prohlížeči se otevře aplikace.

    Pokud dojde k chybě zmínit, Web Deploy, znovu zkontrolovat kroky instalace nasazení webu a zajistěte, aby [správné, jsou otevřené porty](#bkmk_openports) jsou na serveru.

    Pokud aplikace nasadí úspěšně, ale nefunguje správně, spusťte opětovnou kontrolu IIS i projektu sady Visual Studio se musí používat stejnou verzi technologie ASP.NET. Pokud tedy není problém, může být problém s konfigurace služby IIS nebo konfiguraci webu. V systému Windows Server otevřete web ze služby IIS pro další specifické chybové zprávy a pak znovu zkontrolovat dřívějších krocích.

### <a name="optional-publish-and-deploy-the-app-by-publishing-to-a-local-folder-from-visual-studio"></a>(Volitelné) Publikujte a nasaďte aplikaci pomocí publikování do místní složky ze sady Visual Studio

Pokud nepoužíváte nasazení webu, musíte publikovat a nasazení aplikace pomocí systému souborů nebo jiných nástrojů. Začněte vytvořením balíčku pomocí systému souborů a potom můžete buď balíček nasadit ručně nebo použít jiné nástroje, například PowerShell, XCopy nebo RoboCopy. V této části předpokládáme, že jsou ruční kopírování balíčku, pokud nepoužíváte nasazení webu.

[!INCLUDE [remote-debugger-deploy-app-local](../debugger/includes/remote-debugger-deploy-app-local.md)]

### <a name="BKMK_msvsmon"></a> Stáhněte a nainstalujte nástroje pro vzdálenou v systému Windows Server

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]
  
### <a name="BKMK_setup"></a> Nastavení vzdáleného ladicího programu v systému Windows Server

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

> [!NOTE]
> Pokud potřebujete přidat oprávnění pro všechny další uživatele, změna režimu ověřování, nebo číslo portu pro vzdáleného ladicího programu, najdete v části [konfigurovat vzdálený ladicí program](../debugger/remote-debugging.md#configure_msvsmon).

### <a name="BKMK_attach"></a> Připojení k aplikaci ASP.NET z počítače, Visual Studio

1. Otevřete v sadě Visual Studio počítači, **MyASPApp** řešení.
2. V sadě Visual Studio, klikněte na tlačítko **ladění > připojit k procesu** (Ctrl + Alt + P).

    > [!TIP]
    > V aplikaci Visual Studio 2017 lze znovu připojit do stejného procesu dříve připojen k pomocí **ladění > připojte k procesu...** (Shift + Alt + P). 

3. Nastavte hodnotu pole kvalifikátor na  **\<název vzdáleného počítače >: 4022**.
4. Klikněte na tlačítko **aktualizovat**.
    Měli byste vidět některé procesy, které se zobrazí v **dostupné procesy** okno.

    Pokud nevidíte žádné procesy, zkuste pomocí IP adresy místo název vzdáleného počítače (port je vyžadováno). Můžete použít `ipconfig` v příkazovém řádku, potřebujete adresu IPv4.

    Pokud chcete použít **najít** tlačítko, budete muset [otevřete UDP port 3702](#bkmk_openports) na serveru.

5. Zkontrolujte **Zobrazit procesy od všech uživatelů**.
6. Zadejte první písmeno názvu procesu a rychle tak najít **dotnet.exe** (pro ASP.NET Core).
    >Poznámka: Pro aplikace ASP.NET Core se předchozí název procesu dnx.exe.

    ![RemoteDBG_AttachToProcess](../debugger/media/remotedbg_attachtoprocess_aspnetcore.png "RemoteDBG_AttachToProcess")

7. Klikněte na tlačítko **připojit**.

8. Otevřete web vzdáleného počítače. V prohlížeči přejděte na **http://\<název vzdáleného počítače >**.
    
    Měli byste vidět webová stránka ASP.NET.
9. V běžící aplikaci ASP.NET, klikněte na odkaz **o** stránky.

    Zarážce by měl být dosáhl v sadě Visual Studio.

### <a name="bkmk_openports"></a> Řešení potíží: Otevřete požadované porty v systému Windows Server

Ve většině nastavení jsou otevřené požadované porty při instalaci ASP.NET a vzdáleného ladicího programu. Ale Pokud řešíte problémy při nasazení a aplikace se nachází za bránou firewall, musíte ověřit, že jsou otevřené správné porty.

Ve virtuálním počítači Azure, musíte otevřít porty prostřednictvím [skupinu zabezpečení sítě](/azure/virtual-machines/virtual-machines-windows-hero-role#open-port-80). 

Požadované porty:

- 80 - požadované pro službu IIS
- 4022 - požadované pro vzdálené ladění z Visual Studio 2017 (viz [přiřazení portu vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md) Další informace).
- UDP 3702 - port (volitelné) zjišťování umožňuje **najít** tlačítko při připojování k vzdáleného ladicího programu v sadě Visual Studio.

Kromě toho, tyto porty musí být otevřen již při instalaci ASP.NET:
- 8172 – (volitelné) požadované pro nasazení webu pro nasazení aplikace z Visual Studia

