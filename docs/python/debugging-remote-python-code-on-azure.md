---
title: Vzdálené ladění pomocí Python Azure
description: Postup konfigurace Azure App Service pomocí sady Visual Studio pro vzdálené ladění aplikace Python.
ms.date: 06/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 92fd9cf7c81b0b383a185a76eaaf5a3bfc8b93a5
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2018
ms.locfileid: "37057977"
---
# <a name="remotely-debugging-python-code-on-azure"></a>Vzdálené ladění kódu jazyka Python v Azure

[Python podporují v sadě Visual Studio](installing-python-support-in-visual-studio.md) zahrnuje možnost vzdáleně ladění kódu Python, která běží na Azure App Service. Na rozdíl od jednoduchého vzdáleného ladění, cílový počítač v tomto scénáři není přímo přístupné přes protokol TCP, proto Visual Studio poskytuje proxy server, který zveřejňuje protokol ladicí program přes protokol HTTP. Projekty vytvořené pomocí šablony webového automaticky tento proxy server nakonfigurovat v vygenerovaného `web.debug.config` souboru. Vzdálené ladění je také povoleno, když publikujete konfiguraci ladění projektu, jak je popsáno na [publikování do služby Azure App Service] (publishing-python-web-applications-k-azure-from-visual-studio.md.

Protože Azure vzdálené ladění používá webové sokety, sockets musí být povolen pro App Service pomocí [portál Azure](https://portal.azure.com) přechodem na **Nastavení > Nastavení aplikace** vypíná a zapíná  **Obecná nastavení > webové sokety** k **na**, pak výběrem **Uložit** na použití změny. (Všimněte si, že **ladění** nastavení se nevztahuje na ladění Python.)

![Povolení webové sokety na portálu Azure](media/azure-remote-debugging-enable-web-sockets.png)

Jakmile je správně nasazená projekt a webové sokety povolená, můžete připojit ke službě aplikace z **Průzkumníka serveru** v sadě Visual Studio (**zobrazení > Průzkumníka serveru**). Najít váš web v rámci **Azure > služby App Service** a příslušné prostředky skupiny, klikněte pravým tlačítkem a vyberte **připojit ladicí program (Python)**. ( **Připojit ladicí program** příkaz, který je pro aplikace .NET běžící v rámci služby IIS, a je užitečný jenom v případě, že jste společné hostování rozhraní .NET code vedle aplikace Python.)

Visual Studio může trvat můžete přímo na sadu pokyny pro připojení přímo, jak je popsáno níže v [připojení bez Průzkumníka serveru](#attaching-without-server-explorer). Pokud se nezobrazí **připojit ladicí program (Python)** příkaz nebo Visual Studio nepodaří připojit k webu, najdete v části [řešení potíží s Azure vzdálené ladění](debugging-remote-python-code-on-azure-troubleshooting.md).

Pokud připojení úspěšné, Visual Studio se přepne do zobrazení ladicího programu. Panelu nástrojů označuje proces laděné například `wss://` identifikátor URI:

![Ladění webovou stránku služby Azure App Service](media/azure-remote-debugging-attached.png)

Po připojení ladění prostředí je ve většině případů je stejný jako u regulární vzdálené ladění vztahují několik omezení. Na konkrétní webový server služby IIS, který zpracovává příchozí požadavky a provede delegaci je pro kód Python prostřednictvím FastCGI má vypršení časového limitu pro zpracování požadavků, výchozí nastavení je 90 sekund. Pokud zpracování požadavku trvá déle, než tento časový limit (například z důvodu procesu byla pozastavena na zarážce), služba IIS ukončí proces, ukončení relace ladění. 

## <a name="attaching-without-server-explorer"></a>Připojení bez Průzkumníka serveru

Připojí ladicí program přímo do služby App Service, postupujte podle pokynů na stránce informace o proxy protokolu WebSocket, který Visual Studio nasadí na váš web na základě `<site_url>/ptvsd` například `ptvsdemo.azurewebsites.net/ptvsd`. Návštěvou Tato stránka také ověří správně nakonfigurován proxy server:

![Vzdálené ladění proxy informace stránky Azure](media/azure-remote-debugging-proxy-info-page.png)

Podle pokynů, vytvořit adresu URL pomocí tajný klíč z `web.debug.config`, který je regenerována pokaždé, když je publikována projektu. Tento soubor je skrytý ve výchozím nastavení v Průzkumníku řešení a není zahrnut ve vašem projektu, takže zobrazit všechny soubory nebo ho otevřete v samostatných editoru. Po otevření souboru, podívejte se na hodnotu appSetting s názvem `WSGI_PTVSD_SECRET`:

![Určení ladicí program koncového bodu v Azure App Service](media/azure-remote-debugging-secret.png)

Adresa URL je teď třeba ve formě `wss://<secret>@<site_name>.azurewebsites.net/ptvsd` kde nahradíte &lt;tajný klíč&gt;a &lt;název_webu&gt; v řetězci s konkrétními hodnotami.

Připojit ladicí program, vyberte **ladění > připojit k procesu**, vyberte **Python vzdálené ladění** v **přenosu** rozevíracího seznamu, zadejte adresu URL do  **Kvalifikátor textbox**, a stiskněte klávesu Enter. Pokud Visual Studio můžete úspěšně připojit do služby App Service, zobrazuje jeden proces Python v seznamu. Vyberte ho a potom **Attach** spustit ladění:

![Použití připojit k procesu dialogové okno Připojit k webovému serveru Azure](media/azure-remote-debugging-manual-attach.png)
