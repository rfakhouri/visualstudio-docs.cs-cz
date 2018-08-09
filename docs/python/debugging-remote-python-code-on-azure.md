---
title: Azure vzdálené ladění pomocí Pythonu
description: Postup konfigurace služby Azure App Service pomocí sady Visual Studio pro vzdálené ladění aplikace v Pythonu.
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
ms.openlocfilehash: 1e3e70675901128ed6b8d118e54dc10ddee152a5
ms.sourcegitcommit: 96a6d1f16d06ca28d309d05b6e9fbd52f628cdbc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2018
ms.locfileid: "40008616"
---
# <a name="remotely-debug-python-code-on-azure"></a>Vzdálené ladění kódu v Pythonu v Azure

[Podpora Pythonu v sadě Visual Studio](installing-python-support-in-visual-studio.md) zahrnuje možnost vzdáleně ladit kód Pythonu, na kterém běží ve službě Azure App Service. Na rozdíl od jednoduché vzdálené ladění, cílový počítač v tomto scénáři není přímo přístupný přes protokol TCP, aby Visual Studio poskytuje proxy server, který zpřístupňuje protokol ladicího programu přes protokol HTTP. Projekty vytvořené pomocí šablony webové automaticky tento proxy server nakonfigurovat v generované *web.debug.config* souboru. Vzdálené ladění je také povolena, když publikujete **ladění** konfigurace projektu jak je popsáno na [publikovat do služby Azure App Service](publishing-python-web-applications-to-azure-from-visual-studio.md).

Vzhledem k tomu vzdálené ladění Azure používá webové sokety, sockets musí být povolené pro službu App Service prostřednictvím [webu Azure portal](https://portal.azure.com) tak, že přejdete do **nastavení** > **nastavení aplikace**  vypíná a zapíná **obecné nastavení** > **webové sokety** k **na**, pak vyberete **Uložit**na použití změny. (Všimněte si, **ladění** nebude platit nastavení pro ladění Pythonu.)

![Povolení webové sokety na webu Azure portal](media/azure-remote-debugging-enable-web-sockets.png)

## <a name="attach-with-server-explorer"></a>Připojit pomocí Průzkumníka serveru

Jakmile se váš projekt je správně nasazená a povolené webové sokety, můžete připojit do služby App Service z **Průzkumníka serveru** v sadě Visual Studio (**zobrazení** > **Průzkumníka serveru**). Vyhledejte webu **Azure** > **služby App Service** a příslušné prostředky skupiny, klikněte pravým tlačítkem a vyberte **připojit ladicí program (Python)**. ( **Připojit ladicí program** příkaz je pro aplikace .NET běžící v rámci služby IIS a je užitečná pouze v případě, že společné hostování .NET kódu společně s vaší aplikace v Pythonu.)

Visual Studio se můžete dostat přímo do sady pokyny pro připojení přímo, jak je popsáno níže v [připojit bez Průzkumníka serveru](#attach-without-server-explorer). Pokud se nezobrazí **připojit ladicí program (Python)** příkazu nebo sady Visual Studio nepodaří připojit k webu, naleznete v tématu [vzdálené ladění Poradce při potížích pro Python a Azure](debugging-remote-python-code-on-azure-troubleshooting.md).

Pokud je připojení úspěšné, se přepne do zobrazení ladicího programu sady Visual Studio. Panelu nástrojů označuje jako laděného procesu `wss://` identifikátor URI:

![Ladění web služby Azure App Service](media/azure-remote-debugging-attached.png)

Po připojení se možnosti ladění je ve většině případů stejná jako regulární vzdálené ladění v souladu s několika omezeními. Zejména na webovém serveru IIS, který zpracovává příchozí požadavky a deleguje do kódu v Pythonu pomocí FastCGI má časový limit pro zpracování požadavků, výchozí nastavení je 90 sekund. Pokud zpracování požadavku trvá déle než tento časový limit (například z důvodu procesu pozastavení na zarážce), služby IIS ukončí proces, poslední ladicí relaci. 

## <a name="attach-without-server-explorer"></a>Připojit bez Průzkumníka serveru

Připojit ladicí program přímo do služby App Service, postupujte podle pokynů na stránce informace o proxy protokolu WebSocket, který sada Visual Studio nasadí na váš web na  *\<site_url > / ptvsd* například  *ptvsdemo.azurewebsites.NET/ptvsd*. Na této stránce najdete také ověří, že je správně nakonfigurovaný proxy server:

![Vzdálený ladicí proxy informace stránka na webu Azure](media/azure-remote-debugging-proxy-info-page.png)

Podle pokynů, vytvořit adresu URL, pomocí tajného klíče z *web.debug.config*, který je znovu vygenerovány pokaždé, když váš projekt se publikuje. Tento soubor je ve výchozím nastavení skrytá **Průzkumníka řešení** a není součástí projektu, tedy zobrazit všechny soubory nebo pro jeho otevření v samostatných editoru. Po otevření souboru, podívejte se na hodnotu nastavení aplikace s názvem `WSGI_PTVSD_SECRET`:

![Určuje se koncový bod ladicího programu ve službě Azure App Service](media/azure-remote-debugging-secret.png)

Adresa URL je teď třeba ve formě `wss://<secret>@<site_name>.azurewebsites.net/ptvsd` nahradit &lt;tajný kód&gt; a &lt;název_webu&gt; v řetězci s určitými hodnotami.

Chcete-li připojit ladicí program, vyberte **ladění** > **připojit k procesu**vyberte **vzdálené ladění Pythonu** v **přenosu**rozevíracího seznamu, zadejte adresu URL do **textového pole kvalifikátor**a stiskněte klávesu **Enter**. Pokud Visual Studio můžete úspěšně připojit ke službě App Service, zobrazí jeden proces Pythonu v seznamu. Vyberte ho a pak **připojit** pro spuštění ladění:

![Pomocí připojit k procesu dialogové okno Připojit k webu Azure](media/azure-remote-debugging-manual-attach.png)
