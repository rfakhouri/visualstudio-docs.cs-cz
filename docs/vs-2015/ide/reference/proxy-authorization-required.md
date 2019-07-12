---
title: Vyžaduje se autorizace proxy | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: troubleshooting
ms.assetid: c2d24ae1-9902-460e-b72a-0299eed9ee82
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f2de40c520bca0ea04f50ec782fec2dda531172e
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2019
ms.locfileid: "67822072"
---
# <a name="proxy-authorization-required"></a>Vyžaduje se autorizace proxy serveru
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

**Vyžaduje se autorizace Proxy** chybě obvykle dochází, když jsou uživatelé připojeni k sadě Visual Studio online prostředků prostřednictvím proxy serveru a proxy server blokuje volání.

Chcete-li této chybě, zkuste použít jeden nebo více z následujících kroků:

- Restartujte sadu Visual Studio. By se zobrazit dialogové okno ověřování proxy serveru. V dialogovém okně zadejte svoje přihlašovací údaje.

- Pokud předchozí krok problém nevyřeší, může to být vzhledem k tomu, že váš proxy server zobrazovat výzvu k zadání pověření pro http://go.microsoft.com řeší, ale provádí se *. visualStudio.com adresy. Pro tyto servery budete muset přidat následující adresy URL do seznamu povolených pro odblokování všech scénářů přihlašování v aplikaci Visual Studio:

  - *.windows.net

  - *.microsoftonline.com

  - *.visualstudio.com

  - *.microsoft.com

  - *.live.com

- Můžete odebrat http://go.microsoft.com ze seznamu povolených adres tak, aby se zobrazí dialogové okno ověřování proxy serveru pro obě http://go.microsoft.com adresy a koncové body serveru při restartování sady Visual Studio.

- Pokud chcete použít výchozí pověření s proxy serverem, postupujte takto:

   1. Hledání devenv.exe.config (konfigurační soubor devenv.exe): **%ProgramFiles%\Microsoft Visual Studio 14.0\Common7\IDE** (nebo **% ProgramFiles (x86) %\Microsoft Visual Studio 14.0\Common7\IDE**) .

   2. V konfiguračním souboru najít `<system.net>` blokovat a přidejte tento kód:

      ```xml
      <defaultProxy enabled="true" useDefaultCredentials="true">
          <proxy bypassonlocal="True" proxyaddress=" HYPERLINK "http://<yourproxy:port#" http://<yourproxy:port#>"/>
      </defaultProxy>
      ```

      Vložit správný proxy adres pro síť v `proxyaddress="<http://<yourproxy:port#>`.

- Postupujte podle pokynů v [tento příspěvek na blogu](http://blogs.msdn.com/b/rido/archive/2010/05/06/how-to-connect-to-tfs-through-authenticated-web-proxy.aspx) přidáte kód, který umožňuje používat proxy server.
