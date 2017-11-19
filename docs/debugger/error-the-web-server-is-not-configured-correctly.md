---
title: "Chyba: Webový server není nakonfigurován správně | Microsoft Docs"
ms.custom: 
ms.date: 09/20/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.remote.projnotconfigured
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: debugger, Web application errors
ms.assetid: 875ba87f-c372-4126-8fe3-e33931cf26c0
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e0538693a815cf9749b3cd9df007486de1af3637
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="error-the-web-server-is-not-configured-correctly"></a>Chyba: Webový server není správně nakonfigurován.

Po převzetí kroky popsané v tomto poli se problém vyřešit a před dalším pokusem o ladění můžete také obnovit službu IIS. Můžete to udělat pomocí otevřete příkazový řádek správce a zadáte `iisreset`.

Proveďte tyto kroky k vyřešení tohoto problému:

1. Pokud webová aplikace hostované na serveru je nakonfigurovaný jako znovu publikovat jako sestavení ladicí verze sestavení pro vydání a ověřte, že soubor web.config obsahuje `debug=true` v elementu kompilace. Resetování služby IIS a zkuste to znovu.

    Například pokud používáte profil publikování pro sestavení pro vydání, změňte jej na ladění a znovu publikovat. Jinak, nastaví atribut ladění na `false` při publikování.

2. (IIS) Ověřte správnost fyzickou cestu. Ve službě IIS, zjistíte, toto nastavení v **základní nastavení > fyzická cesta** (nebo **Upřesnit nastavení** ve starších verzích služby IIS).

    Fyzická cesta může být nesprávný, jestliže webová aplikace byla zkopírována do jiný počítač, ručně přejmenován nebo přesunut. Resetování služby IIS a zkuste to znovu.

3. V sadě Visual Studio ověřte, zda je vybrán správný server ve vlastnostech. (Otevřete **vlastnosti > Web > servery** nebo **vlastnosti > ladění** v závislosti na typu vašeho projektu. Pro projekt webové formuláře, otevřete **stránky vlastností > Možnosti spuštění > serveru**).

    Pokud používáte externí (vlastní) server například služby IIS, adresa URL musí být správné. Jinak vyberte možnost služby IIS Express a zkuste to znovu.

4. (IIS) Ujistěte se, že je na serveru nainstalována správná verze technologie ASP.NET.

    Tento problém může způsobit neodpovídající verze technologie ASP.NET ve službě IIS a v projektu sady Visual Studio. Musíte nastavit framework verze v souboru web.config. Instalace technologie ASP.NET ve službě IIS, použijte [instalačního programu webové platformy (WebPI)](https://www.microsoft.com/web/downloads/platform.aspx). Další informace naleznete v [IIS 8.0 pomocí technologie ASP.NET 3.5 a technologii ASP.NET 4.5](https://docs.microsoft.com/en-us/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45) nebo pro ASP.NET Core [hostitele v systému Windows pomocí služby IIS](https://docs.asp.net/en/latest/publishing/iis.html).
  
4. Pokud `maxConnection` limit ve službě IIS je příliš nízké a máte příliš mnoha připojení, budete muset [zvýšení limitu připojení](https://docs.microsoft.com/en-us/iis/configuration/system.applicationhost/sites/sitedefaults/limits).
  
## <a name="see-also"></a>Viz také  
 [Vzdálené ladění technologie ASP.NET v počítači vzdálené služby IIS](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)   
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)