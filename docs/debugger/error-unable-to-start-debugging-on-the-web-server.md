---
title: 'Chyba: Nepodařilo se zahájit ladění na webovém serveru | Dokumentace Microsoftu'
ms.date: 05/23/2018
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.http
- vwd.nonadmin.error.
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- IIS, debugging DLLs
- debugger, Web application errors
- unable to start debugging error
- security [debugger], Web applications
- debugging [Visual Studio], errors
- HTTP servers, debugging error
- security settings, checking for default Web sites
- errors [debugger], unable to start debugging
- debugging ASP.NET Web applications, unable to start debugging error
- remote debugging, errors
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 53ffc893b63447ab75a439ea1e093ddaf4b75645
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62850099"
---
# <a name="error-unable-to-start-debugging-on-the-web-server"></a>Chyba: Nepodařilo se zahájit ladění na webovém serveru

Při pokusu o ladění aplikace ASP.NET běžící na webovém serveru, se může zobrazit tato chybová zpráva: `Unable to start debugging on the Web server`.

Této chybě dochází často, protože k chybě nebo konfigurace došlo ke změně, která vyžaduje aktualizaci fondů aplikací a resetování služby IIS. Služba IIS můžete resetovat otevřením příkazového řádku se zvýšenými oprávněními a zadáním `iisreset`.

## <a name="specificerrors"></a>Co je Podrobná chybová zpráva?

`Unable to start debugging on the Web server` Zprávy je obecný. Obvykle podrobnější zprávu je součástí řetězec chyby a, které mohou pomoci identifikovat příčinu problému nebo vyhledejte přesnější opravu. Tady je několik běžných chybových zpráv, které jsou připojeny k hlavním chybová zpráva:

- [IIS nemá v seznamu web, který odpovídá spuštění adresy url](#IISlist)
- [Webový server není správně nakonfigurován.](#web_server_config)
- [Nelze se připojit k webový server](#unabletoconnect)
- [Webový server neodpověděl včas](#webservertimeout)
- [Microsoft visual studio vzdálené ladění monitor(msvsmon.exe) zřejmě není spuštěn ve vzdáleném počítači](#msvsmon)
- [Vzdálený server vrátil chybu](#server_error)
- [Nelze spustit ASP.NET ladění](#aspnet)
- [Ladicí program nemůže připojit ke vzdálenému počítači](#cannot_connect)
- [Zobrazit nápovědu pro běžné chyby konfigurace. Spuštění webové stránky mimo ladicí program získáte další informace.](#see_help)

## <a name="IISlist"></a> IIS nemá v seznamu web, který odpovídá spuštění adresy url

- Restartujte Visual Studio jako správce a zkuste ladění. (Některé scénáře ladění ASP.NET vyžaduje zvýšená oprávnění).

    Visual Studio vždy spustit jako správce kliknutím pravým tlačítkem myši na ikonu zástupce sady Visual Studio, můžete nakonfigurovat výběr **vlastnosti > Upřesnit**a poté volbou vždy spustit jako správce.

## <a name="web_server_config"></a> Webový server není správně nakonfigurován.

- Zobrazit [Chyba: Webový server není nakonfigurován správně](../debugger/error-the-web-server-is-not-configured-correctly.md).

## <a name="unabletoconnect"></a> Nelze se připojit k webový server

- Můžete se službou Visual Studio a webový server na stejném počítači a ladění pomocí **F5** (místo **připojit k procesu**)? Otevřete vlastnosti projektu a ujistěte se, že projekt je nakonfigurován pro připojení ke správnému webového serveru a adresa URL pro spuštění. (Otevřete **vlastnosti > Web > servery** nebo **vlastnosti > ladění** v závislosti na typu vašeho projektu. Pro projekt webových formulářů, otevřete **stránky vlastností > Možnosti spuštění > Server**.)

- V opačném případě restartujte fond aplikací a pak restartujte službu IIS. Další informace najdete v tématu [Zkontrolujte konfiguraci služby IIS](#vxtbshttpservererrorsthingstocheck).

## <a name="webservertimeout"></a> Webový server neodpověděl včas

- Resetujte IIS a zkuste to znovu ladění. Více instancí ladicí program může připojit k procesu služby IIS. vynulování ukončí je. Další informace najdete v tématu [Zkontrolujte konfiguraci služby IIS](#vxtbshttpservererrorsthingstocheck).

## <a name="msvsmon"></a> Microsoft visual studio vzdálené ladění monitor(msvsmon.exe) zřejmě není spuštěn ve vzdáleném počítači

- Když provádíte ladění na vzdáleném počítači, ujistěte se, že máte [nainstalovali a používají vzdálený ladicí program](../debugger/remote-debugging.md). Pokud zpráva uvádí bránu firewall, ujistěte se, že [opravte porty v bráně firewall](../debugger/remote-debugger-port-assignments.md) jsou otevřené, zejména v případě, že používáte firewall od jiného výrobce.
- Pokud používáte soubor HOSTITELŮ, ujistěte se, že je správně nakonfigurovaný. Například, pokud ladění pomocí **F5** (místo **připojit k procesu**), hostitele soubor musí obsahovat stejnou adresu URL projektu jako vlastnosti projektu, **vlastnosti > Web > servery**  nebo **vlastnosti > ladění**, v závislosti na typu vašeho projektu.

## <a name="server_error"></a> Vzdálený server vrátil chybu

Zkontrolujte vaše [souboru protokolu služby IIS](https://support.microsoft.com/help/943891/the-http-status-code-in-iis-7-0--iis-7-5--and-iis-8-0) dílčí kódy chyb a další informace a tuto službu IIS 7 [blogový příspěvek](https://blogs.iis.net/tomkmvp/troubleshoot-a-403).

Kromě toho se tady jsou některé běžné kódy chyb a několik návrhů.
- Zakázáno (403). Existuje mnoho možných příčin této chyby, tak váš soubor protokolu a nastavení zabezpečení služby IIS pro web. Ujistěte se, že soubor web.config serveru zahrnuje `debug=true` v elementu kompilace. Ujistěte se, že vaše webové aplikace složka má správná oprávnění a konfiguraci fondu aplikací správnost (může mít změnit heslo). Zobrazit [Zkontrolujte konfiguraci služby IIS](#vxtbshttpservererrorsthingstocheck). Pokud tato nastavení jsou správné a že ladíte místně, taky ověřit, že se připojujete k správný typ serveru a adresu URL (v **vlastnosti > Web > servery** nebo **vlastnosti > ladění**, v závislosti na typu vašeho projektu).
- (503) server není dostupný. Fond aplikací se možná zastavil z důvodu chyby nebo konfigurace změny. Restartování fondu aplikací.
- (404) nebyl nalezen. Ujistěte se, že fond aplikací je nakonfigurovaný pro správnou verzi technologie ASP.NET.

## <a name="aspnet"></a> Nelze spustit ASP.NET ladění

- Restartování fondu aplikací a resetujte IIS. Další informace najdete v tématu [Zkontrolujte konfiguraci služby IIS](#vxtbshttpservererrorsthingstocheck).
- Pokud provádíte přepíše adresu URL, otestovat základní soubor web.config se žádná adresa URL přepisů. Zobrazit **Poznámka** o adrese URL revize v modulu [Zkontrolujte konfiguraci služby IIS](#vxtbshttpservererrorsthingstocheck).

## <a name="cannot_connect"></a> Ladicí program nemůže připojit ke vzdálenému počítači

Jestliže ladíte místně, této chybě může dojít, protože Visual Studio je 32bitová aplikace, aby používalo 64bitovou verzi vzdáleného ladicího programu pro ladění 64bitových aplikací. Otevřete vlastnosti projektu a ujistěte se, že projekt je nakonfigurován pro připojení ke správné webový server a adresy URL. (Otevřete **vlastnosti > Web > servery** nebo **vlastnosti > ladění** v závislosti na typu vašeho projektu.)

Navíc pokud použijete soubor HOSTITELŮ, ujistěte se, že je správně nakonfigurován. Například soubor HOSTITELŮ musí obsahovat stejnou adresu URL projektu jako vlastnosti projektu, **vlastnosti > Web > servery** nebo **vlastnosti > ladění**, v závislosti na typu vašeho projektu.

## <a name="see_help"></a> Zobrazit nápovědu pro běžné chyby konfigurace. Spuštění webové stránky mimo ladicí program získáte další informace.

- Používáte ve stejném počítači Visual Studio a webový server? Otevřete vlastnosti projektu a ujistěte se, že projekt je nakonfigurován pro připojení ke správnému webového serveru a adresa URL pro spuštění. (Otevřete **vlastnosti > Web > servery** nebo **vlastnosti > ladění** v závislosti na typu vašeho projektu.)

- Pokud to nepomůže, nebo ladíte vzdáleně, postupujte podle kroků v [Zkontrolujte konfiguraci služby IIS](#vxtbshttpservererrorsthingstocheck).

## <a name="vxtbshttpservererrorsthingstocheck"></a> Zkontrolujte konfiguraci služby IIS

Až provedete kroky popsané tady řešení tohoto problému a před dalším pokusem o ladění může být také potřeba resetovat služby IIS. Můžete to udělat otevřením příkazového řádku se zvýšenými oprávněními a zadáním `iisreset`.

* Zastavit a restartovat fondů aplikací IIS, a opakujte.

    Fond aplikací se možná zastavil v důsledku chyby. Nebo jiné se provedené změny konfigurace můžou vyžadovat ukončení a restartování fondu aplikací.

    > [!NOTE]
    > Pokud udržuje zastavení fondu aplikací, budete muset z ovládacího panelu odinstalovat modul přepisování adres URL. Můžete znovu nainstalovat pomocí instalačního programu webové platformy (WebPI). Tomuto problému může dojít po upgradu významné systému.

* Zkontrolujte konfiguraci fondu aplikací, opravte ji v případě potřeby a zkuste zopakovat.

    Fond aplikací může být nakonfigurovaný pro verze technologie ASP.NET, která se neshoduje s projektu sady Visual Studio. Aktualizovat verzi technologie ASP.NET ve fondu aplikací a restartujte ji. Podrobné informace najdete v tématu [IIS 8.0 pomocí technologie ASP.NET 3.5 a technologii ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45).

    Také pokud jste změnili heslo přihlašovacích údajů, budete muset aktualizovat ve fondu aplikací nebo webovou stránku.  Ve fondu aplikací, aktualizujte přihlašovací údaje v **Upřesnit nastavení > Model procesu > Identity**. Pro webový server, aktualizujte přihlašovací údaje v **základní nastavení > připojit jako...** . Restartování fondu aplikací.

* Zkontrolujte, že vaše webové aplikace složka má správná oprávnění.

    Ujistěte se, že poskytnete IIS_IUSRS IUSR, nebo konkrétního uživatele přidružené k [fond aplikací](/iis/manage/configuring-security/application-pool-identities) číst a spouštět práva ke složce webové aplikace. Tento problém vyřešit a restartuje fond aplikací.

* Ujistěte se, že je nainstalována správná verze technologie ASP.NET ve službě IIS.

    Neshoda verzí technologie ASP.NET ve službě IIS a v projektu sady Visual Studio může způsobit potíže. Budete muset nastavit verzi rozhraní framework v souboru web.config. Instalace technologie ASP.NET na IIS, použijte [instalačního programu webové platformy (WebPI)](https://www.microsoft.com/web/downloads/platform.aspx). Viz také [IIS 8.0 pomocí technologie ASP.NET 3.5 a technologii ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45) nebo pro ASP.NET Core, [hostitelská služba ve Windows se službou IIS](https://docs.asp.net/en/latest/publishing/iis.html).

* Řešení chyb při ověřování, pokud používáte jenom IP adresy

     Ve výchozím nastavení IP adresy jsou považovány za součást Internetu a ověřování protokolem NTLM není Hotovo přes Internet. Pokud je váš web konfigurován ve službě IIS tak, aby vyžadovala ověřování, ověřování se nezdaří. Chcete-li tento problém, můžete zadat název vzdáleného počítače místo IP adresy.

## <a name="other-causes"></a>Další příčiny

Pokud se konfigurace služby IIS nebude příčinou problému, proveďte následující kroky:

- Restartujte sadu Visual Studio s oprávněními správce a zkuste to znovu.

    Některé scénáře ladění ASP.NET například pomocí nasazení webu vyžaduje zvýšená oprávnění pro Visual Studio.

- Pokud běží více instancí sady Visual Studio, otevřete projekt v jedné instanci sady Visual Studio (s oprávněními správce) a zkuste to znovu.

- Pokud používáte soubor HOSTITELŮ pomocí místní adresy, použijte adresu zpětné smyčky místo jeho IP adresy.

    Pokud nepoužíváte místní adresy, ujistěte se, že soubor HOSTITELŮ obsahuje stejnou adresu URL projektu jako vlastnosti projektu, **vlastnosti > Web > servery** nebo **vlastnosti > ladění**, v závislosti na vaší Typ projektu.

## <a name="more-troubleshooting-steps"></a>Další postup řešení potíží

* Vyvolejte localhost stránku v prohlížeči na serveru.

     Pokud služba IIS není správně nainstalovaná, by měl dojde k chybám při zadávání `http://localhost` v prohlížeči.

     Další informace o nasazení do služby IIS najdete v tématu [IIS 8.0 pomocí technologie ASP.NET 3.5 a technologii ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45) a pro ASP.NET Core, [hostitelská služba ve Windows se službou IIS](https://docs.asp.net/en/latest/publishing/iis.html).

* Vytvořit základní aplikaci v ASP.NET na serveru (nebo použijte soubor základní web.config).

    Pokud to nejde s vaší aplikaci umožní pracovat s ladicím programem, zkuste vytvořit základní aplikaci ASP.NET místně na serveru a zkuste ladit základní aplikaci. (Můžete chtít použít výchozí šablony ASP.NET MVC.) Pokud ladíte základní aplikaci, který vám mohou pomoci identifikovat, čím se liší mezi dvěma konfiguracemi. Vyhledejte rozdíly v nastavení v souboru web.config, jako například pravidla pro přepis adres URL.

## <a name="see-also"></a>Viz také
- [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)