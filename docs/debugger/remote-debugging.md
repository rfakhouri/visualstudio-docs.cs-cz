---
title: Vzdálené ladění v sadě Visual Studio | Dokumentace Microsoftu
ms.custom: remotedebugging
ms.date: 07/02/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.remote.overview
dev_langs:
- C++
- FSharp
- CSharp
- JScript
- VB
helpviewer_keywords:
- remote debugging, setup
ms.assetid: 5a94ad64-100d-43ca-9779-16cb5af86f97
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 46913c1bb671c1986c4f302a84d4183fe17f5878
ms.sourcegitcommit: c57ae28181ffe14a30731736661bf59c3eff1211
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2018
ms.locfileid: "38778291"
---
# <a name="remote-debugging"></a>Vzdálené ladění
Můžete ladit aplikace Visual Studio, který byl nasazen na jiný počítač. K tomu použijete vzdálený ladicí program sady Visual Studio.

Podrobné pokyny pro vzdálené ladění naleznete v následujících tématech.

|Scénář|Odkaz|
|-|-|-|
|Azure App Service|[Snapshot Debugger](../debugger/debug-live-azure-applications.md) nebo [vzdálené ladění ASP.NET ve službě Azure](../debugger/remote-debugging-azure.md)|
|Virtuální počítač Azure|[Vzdálené ladění ASP.NET ve službě Azure](../debugger/remote-debugging-azure.md)|
|Azure Service Fabric|[Ladění aplikace Azure Service Fabric](/azure/service-fabric/service-fabric-debugging-your-application#debug-a-remote-service-fabric-application)|
|ASP.NET|[Vzdálené ladění ASP.NET Core](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md) nebo [vzdálené ladění ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)|
|C# nebo Visual Basic|[Vzdálené ladění projektu v jazyce C# nebo Visual Basic](../debugger/remote-debugging-csharp.md)|
|C++|[Vzdálené ladění projektu v jazyce C++](../debugger/remote-debugging-cpp.md)|
|Aplikace pro Universal Windows (UPW)|[Spouštění aplikací pro UWP ve vzdáleném počítači](../debugger/run-windows-store-apps-on-a-remote-machine.md) nebo [ladění balíčku nainstalované aplikace](../debugger/debug-installed-app-package.md)|

Pokud jenom chcete stáhnout a nainstalovat vzdáleného ladicího programu a není třeba žádné další pokyny pro váš scénář, postupujte podle kroků v tomto článku.

## <a name="download-and-install-the-remote-tools"></a>Stáhněte a nainstalujte nástroje remote tools

[!INCLUDE [remote-debugger-download](../debugger/includes/remote-debugger-download.md)]

## <a name="unblock_msvsmon"></a> Odblokování stáhnout nástroje remote tools v systému Windows Server

Výchozí nastavení zabezpečení v aplikaci Internet Explorer ve Windows serveru může být časově náročné ke stažení komponenty, například nástroje remote tools.

* Je povoleno rozšířené nastavení zabezpečení v Internet Exploreru, což brání websites otevírání a zpřístupňování webových prostředků, pokud nejsou explicitně povolená na doménu obsahující zdroj (to znamená, důvěryhodná). I když můžete toto nastavení zakážete, nedoporučujeme, že je vzhledem k tomu, že to představuje bezpečnostní riziko.

* V systému Windows Server 2016, výchozí nastavení **Možnosti Internetu** > **zabezpečení** > **Internet**  >   **Vlastní úroveň** > **stáhne** také zakáže stahování souborů. Pokud chcete stáhnout remote tools přímo v systému Windows Server, je nutné povolit stahování souborů.

Pokud chcete stáhnout nástroje pro Windows Server, doporučujeme jednu z následujících akcí:

* Stáhnout nástroje remote tools na jiném počítači, jako je například jeden spuštěné Visual Studio a zkopírujte *.exe* soubor do systému Windows Server.

* Spustit vzdálený ladicí program [ze sdílené složky](#fileshare_msvsmon) na svém počítači Visual Studio.

* Stáhnout nástroje pro vzdálenou přímo v systému Windows Server a přijímal výzvy k přidání důvěryhodných serverů. Moderních webů často zahrnují mnoho zdrojů třetí strany, takže to může způsobit velké množství výzev. Kromě toho přesměrovaného odkazy muset přidat ručně. Můžete nastavit některé z důvěryhodných lokalit přidat před zahájením stahování. Přejděte na **Možnosti Internetu > zabezpečení > Důvěryhodné servery > servery** a přidejte následující weby.

  * VisualStudio.microsoft.com
  * download.visualstudio.microsoft.com
  * o: prázdné

  Pro starší verze ladicího programu na my.visualstudio.com přidejte tyto další lokality, abyste měli jistotu, že je tento přihlášení úspěšné:

  * microsoft.com
  * go.microsoft.com
  * download.microsoft.com
  * My.VisualStudio.com
  * login.microsoftonline.com
  * Login.live.com
  * secure.aadcdn.microsoftonline-p.com
  * MSFT.STS.microsoft.com
  * auth.gfx.MS
  * app.vssps.visualstudio.com
  * vlscppe.microsoft.com
  * Query.prod.CMS.RT.microsoft.com

    Pokud budete chtít přidat tyto domény při stahování nástroje remote tools a pak zvolte **přidat** po zobrazení výzvy.

    ![Dialogové okno o blokovaném obsahu pole](../debugger/media/remotedbg-blocked-content.png)

    Když si stáhnete software, získat některé další požadavky pro udělení oprávnění k načítání různých skriptů na webu a prostředky. Na my.visualstudio.com doporučujeme vám, že přidáte další domény, abyste měli jistotu, že je tento přihlášení úspěšné.

## <a name="requirements_msvsmon"></a> Požadavky

[!INCLUDE [remote-debugger-requirements](../debugger/includes/remote-debugger-requirements.md)]

## <a name="fileshare_msvsmon"></a> (Volitelné) Spuštění vzdáleného ladicího programu ze sdílené složky

Můžete najít vzdáleného ladicího programu (*msvsmon.exe*) na počítači s Visual Studio Community, Professional nebo Enterprise už nainstalovaná. Pro některé scénáře je nejjednodušší způsob, jak nastavit vzdálené ladění spusťte vzdálený ladící program (msvsmon.exe) ze sdílené složky. Omezení využití najdete na stránce nápovědy vzdáleného ladicího programu (**Nápověda > využití** v vzdálený ladicí program).

1. Najít *msvsmon.exe* v adresáři odpovídající verzi sady Visual Studio. Pro Visual Studio Enterprise 2017:

      *Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\Remote Debugger\x86\msvsmon.exe*

      *Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\Remote Debugger\x64\msvsmon.exe*

2. Sdílené složky **vzdálený ladicí program** složky v počítači, Visual Studio.

3. Na vzdáleném počítači, spusťte *msvsmon.exe* ze sdílené složky. Postupujte podle [instalační pokyny](#bkmk_setup).

> [!TIP]
> Instalace pomocí příkazového řádku a příkazový řádek, naleznete na stránce nápovědy pro *msvsmon.exe* zadáním ``msvsmon.exe /?`` na příkazovém řádku na počítači s nainstalovanou sadu Visual Studio (nebo můžete přejít na **Nápověda > využití**v vzdálený ladicí program).

## <a name="bkmk_setup"></a> Nastavení vzdáleného ladicího programu

[!INCLUDE [remote-debugger-configuration](../debugger/includes/remote-debugger-configuration.md)]

### <a name="configure_msvsmon"></a> Konfigurace vzdáleného ladicího programu
Některé aspekty konfigurace vzdáleného ladicího programu můžete změnit po prvním spuštění po spuštění.

-   Pokud je potřeba přidat oprávnění pro ostatní uživatele, který chcete připojit ke vzdálenému ladicímu programu, zvolte **nástroje > oprávnění**. K udělení nebo odebrání oprávnění je potřeba mít oprávnění správce.

     > [!IMPORTANT]
     > Můžete spustit vzdálený ladicí program uživatelského účtu, který se liší od uživatelského účtu, který používáte na počítači aplikace Visual Studio, ale musíte přidat jiný uživatelský účet oprávnění vzdáleného ladicího programu.

     Alternativně můžete spustit vzdálený ladicí program z příkazového řádku pomocí **/ allow \<uživatelské jméno >** parametr: **msvsmon / allow \< username@computer>**.

-   Pokud je potřeba změnit režim ověřování nebo číslo portu nebo zadat hodnotu časového limitu pro nástroje remote tools: Zvolte **nástroje > Možnosti**.

     Seznam čísel portů používaných ve výchozím nastavení, najdete v části [přiřazení portů vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md).

     > [!WARNING]
     >  Můžete také spustit nástroje Remote Tools v režimu bez ověřování, ale tento režim se rozhodně nedoporučuje. Při spuštění v tomto režimu není žádné zabezpečení sítě. Zvolte režim bez ověřování jenom v případě, že jste si jisti, že síť není ohroženy škodlivými nebo nevyžádanými daty.

##  <a name="bkmk_configureService"></a> (Volitelné) Konfigurovat vzdálený ladicí program jako službu
Pro ladění v technologii ASP.NET a jiné prostředí serveru, musíte buď spustit vzdálený ladicí program jako správce nebo, je vždy spuštěn, chcete-li spustit vzdálený ladicí program jako službu.

 Pokud chcete nakonfigurovat vzdálený ladicí program jako službu, postupujte podle těchto kroků.

1.  Najít **Průvodce konfigurací vzdáleného ladicího programu** (rdbgwiz.exe). (To je samostatná aplikace od vzdáleného ladicího programu.) Je dostupná jenom při instalaci nástrojů remote tools. Nenainstaluje se sadou Visual Studio.

2.  Spustíte Průvodce konfigurací. Po první stránka se zobrazí, klikněte na tlačítko **Další**.

3.  Zkontrolujte, **spustit Visual Studio 2015 vzdálený ladicí program jako službu** zaškrtávací políčko.

4.  Přidáte název uživatelského účtu a hesla.

     Budete muset přidat **přihlásit jako službu** uživatele přímo k tomuto účtu (Najít **místní zásady zabezpečení** (secpol.msc) v **Start** stránky nebo okna (nebo typ  **secpol** z příkazového řádku). Po zobrazení dialogového okna, dvakrát klikněte na panel **přiřazení uživatelských práv**, vyhledejte **přihlásit jako službu** v pravém podokně. Poklepejte na něj. Přidat uživatelský účet **vlastnosti** okno a klikněte na tlačítko **OK**). Klikněte na tlačítko **Další**.

5.  Vyberte typ sítě, mají komunikovat nástroje remote tools. Musí být vybrán alespoň jeden typ sítě. Pokud jsou počítače připojené do domény, měli byste zvolit první položku. Pokud jsou tyto počítače připojeny přes domácí nebo pracovní skupině, měli byste zvolit položky druhý nebo třetí. Klikněte na tlačítko **Další**.

6.  Pokud tuto službu můžete spustit, zobrazí se **byly úspěšně dokončeny Visual Studio Debugger Průvodce konfigurací vzdáleného**. Pokud službu nelze spustit, zobrazí se **se nepodařilo dokončit Visual Studio Debugger Průvodce konfigurací vzdáleného**. Stránce se zobrazuje také několik tipů pro získání služba spustí.

7.  Klikněte na tlačítko **Dokončit**.

 V tomto okamžiku vzdálený ladicí program je spuštěn jako služba. Můžete to ověřit tak, že přejdete do **ovládací panely > služby** a hledáte **Visual Studio 2015 vzdálený ladicí program**.

 Můžete zastavit a spustit službu vzdálený ladicí program z **ovládací panely > služby**.

## <a name="set-up-debugging-with-remote-symbols"></a>Nastavení se vzdálený symboly ladění

[!INCLUDE [remote-debugger-symbols](../debugger/includes/remote-debugger-symbols.md)]

## <a name="see-also"></a>Viz také:

- [Prohlídka funkcí ladicího programu](../debugger/debugger-feature-tour.md)
- [Konfigurace brány Windows Firewall pro vzdálené ladění](../debugger/configure-the-windows-firewall-for-remote-debugging.md)
- [Přiřazení portů vzdáleného ladicího programu](../debugger/remote-debugger-port-assignments.md)
- [Vzdálené ladění ASP.NET Core na počítači vzdálené služby IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-computer.md)
- [Vzdálené ladění chyby a řešení potíží](../debugger/remote-debugging-errors-and-troubleshooting.md)