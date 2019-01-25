---
title: Vyžaduje se autorizace proxy | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
ms.assetid: c2d24ae1-9902-460e-b72a-0299eed9ee82
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b55dba438280fc4579fe15bd2a423d323c38abf6
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54767277"
---
# <a name="proxy-authorization-required"></a>Vyžaduje se autorizace proxy
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
K této chybě obvykle dochází, když jsou uživatelé připojeni ke službě Visual Studio Online prostřednictvím proxy serveru a proxy server blokuje volání. Visual Studio Online slouží k ukládání uživatel přihlášený rozhraní IDE.  
  
## <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Restartujte sadu Visual Studio. By se zobrazit dialogové okno ověřování proxy serveru. V dialogovém okně zadejte svoje přihlašovací údaje.  
  
-   Pokud předchozí krok problém nevyřeší, může to být vzhledem k tomu, že váš proxy server zobrazovat výzvu k zadání pověření pro http://go.microsoft.com řeší, ale provádí se *. visualStudio.com adresy. Pro tyto servery potřebujete na seznam povolených v následujícím seznamu pro odblokování všech scénářů přihlašování v aplikaci Visual Studio:  
  
    -   *.windows.net  
  
    -   *.microsoftonline.com  
  
    -   *.visualstudio.com  
  
    -   *.microsoft.com  
  
    -   *.live.com  
  
-   V opačném případě můžete odebrat http://go.microsoft.com adresy, ze seznamu povolených, aby se zobrazí dialogové okno ověřování proxy serveru pro obě http://go.microsoft.com adresy a koncové body serveru při restartování sady Visual Studio.  
  
-   NEBO  
  
-   Pokud chcete použít výchozí pověření s proxy serverem, máte následující:  
  
    1.  Hledání devenv.exe.config (konfigurační soubor devenv.exe): **%ProgramFiles%\Microsoft Visual Studio 14.0\Common7\IDE** (nebo **% ProgramFiles (x86) %\Microsoft Visual Studio 14.0\Common7\IDE**) .  
  
    2.  V konfiguračním souboru najít `<system.net>` blokovat a přidejte tento kód:  
  
        ```xml  
        <defaultProxy enabled="true" useDefaultCredentials="true">  
            <proxy bypassonlocal="True" proxyaddress=" HYPERLINK "http://<yourproxy:port#" http://<yourproxy:port#>"/>  
        </defaultProxy>  
  
        ```  
  
         Je třeba vložit adresu proxy serveru správná pro vaši síť v `proxyaddress="<http://<yourproxy:port#>`.  
  
-   NEBO  
  
-   Můžete také postupujte podle pokynů v [tento příspěvek](http://blogs.msdn.com/b/rido/archive/2010/05/06/how-to-connect-to-tfs-through-authenticated-web-proxy.aspx) přidáte kód, který vám umožní používat proxy server.
