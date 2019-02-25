---
title: Řešení potíží s chybami sítě nebo proxy serveru
description: Řešení chyby související s sítě nebo proxy, které můžete narazit při instalaci nebo používání sady Visual Studio za bránou firewall nebo proxy server.
ms.date: 02/23/2018
ms.topic: troubleshooting
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
- list of domains, locations, URLs, Visual Studio
- proxy errors, Visual Studio
ms.assetid: ''
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: f33351245d35ef025d98b3dcf1c2c325fa1ca802
ms.sourcegitcommit: 1c8e07b98fc0a44b5ab90bcef77d9fac7b3eb452
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/25/2019
ms.locfileid: "56796481"
---
# <a name="troubleshooting-network-related-errors-when-you-install-or-use-visual-studio"></a>Řešení potíží s chyby související se sítí při instalaci nebo používání sady Visual Studio

Máme řešení obvykle chyby související s sítě nebo proxy, které můžete narazit při instalaci nebo používání sady Visual Studio za bránou firewall nebo proxy server.

## <a name="error-proxy-authorization-required"></a>Chyba: "Vyžaduje autorizace proxy"

K této chybě obvykle dochází, když jsou uživatelé připojeni k Internetu prostřednictvím proxy serveru a proxy server blokuje volání, která vytvoří malou Visual Studio k některým síťovým prostředkům.

### <a name="to-fix-this-proxy-error"></a>Chcete-li vyřešit tuto chybu proxy

- Restartujte sadu Visual Studio. By se zobrazit dialogové okno ověřování proxy serveru. Zadejte svoje přihlašovací údaje po zobrazení výzvy v dialogovém okně.

- Pokud restartování sady Visual Studio problém nevyřeší, může být, že váš proxy server nezobrazí výzvu pro přihlašovací údaje pro protokol http:&#47;&#47;go.microsoft.com řeší, ale provádí se &#42;. visualStudio.com adresy. Pro tyto servery zvažte přidání na seznam povolených následující adresy URL pro odblokování všech scénářů přihlašování v aplikaci Visual Studio:

    - &#42;.windows.net

    - &#42;.microsoftonline.com

    - &#42;.visualstudio.com

    - &#42;.microsoft.com

    - &#42;.live.com

- V opačném případě můžete odebrat http:&#47;&#47;go.microsoft.com adresy, ze seznamu povolených, aby se zobrazí dialog ověřování proxy serveru pro obě http:&#47;&#47;go.microsoft.com adresy a koncové body serveru, když je aplikace Visual Studio restartovat.

  -OR-

- Pokud chcete použít výchozí pověření s proxy serverem, můžete provádět následující akce:

  1. Najít **devenv.exe.config** (konfigurační soubor devenv.exe) v: **%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE** nebo **% ProgramFiles (x86) %\Microsoft Vizuální Studio\2017\Enterprise\Common7\IDE**.

  2. V konfiguračním souboru najít `<system.net>` blokovat a následně přidejte následující kód:

      ```xml
      <defaultProxy enabled="true" useDefaultCredentials="true">
          <proxy bypassonlocal="True" proxyaddress="http://<yourproxy:port#>"/>
      </defaultProxy>
      ```

      Je třeba vložit adresu proxy serveru správná pro vaši síť v `proxyaddress="<http://<yourproxy:port#>`.

     > [!NOTE]
     > Další informace najdete v tématu [ &lt;defaultProxy&gt; – Element (nastavení sítě)](/dotnet/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings) a [ &lt;proxy&gt; – Element (nastavení sítě)](/dotnet/framework/configure-apps/file-schema/network/proxy-element-network-settings) stránky.

  -OR-

- Také postupujte podle pokynů [jak se připojit přes ověřený proxy server webové](https://blogs.msdn.microsoft.com/rido/2010/05/06/how-to-connect-to-tfs-through-authenticated-web-proxy/) blogový příspěvek, který ukazuje, jak přidat kód, který vám umožní používat proxy server.

## <a name="error-the-underlying-connection-was-closed"></a>Chyba: "Nadřízené připojení bylo uzavřeno."

Pokud používáte Visual Studio v privátní síti, která má bránu firewall, Visual Studio nemusí být schopný se připojit k některým síťovým prostředkům. Tyto prostředky mohou zahrnovat Azure DevOps služby pro přihlašování a licencování NuGet a službami Azure. Pokud Visual Studio nepodaří připojit k jednomu z těchto prostředků, může se zobrazit následující chybová zpráva:

  **Nadřízené připojení bylo uzavřeno: Při odesílání došlo k neočekávané chybě.**

Visual Studio používá k připojení k síťovým prostředkům protokol zabezpečení TLS (Transport Layer) 1.2. Zabezpečovací zařízení několik soukromých sítích blokují některá serverová připojení, když sada Visual Studio používá TLS 1.2.

### <a name="to-fix-this-connection-error"></a>Chcete-li vyřešit tuto chybu připojení

Povolte připojení pro následující adresy URL:

- https:&#47;&#47;management.core.windows.net

- https:&#47;&#47;app.vssps.visualstudio.com

- https:&#47;&#47;login.microsoftonline.com

- https:&#47;&#47;login.live.com

- https:&#47;&#47;go.microsoft.com

- https:&#47;&#47;graph.windows.net

- https:&#47;&#47;app.vsspsext.visualstudio.com

- &#42;. azurewebsites.net (pro připojení Azure)

- &#42;.visualstudio.com

- CDN.vsassets.IO (síť pro doručování obsahu hostitele nebo CDN, obsah)

- &#42;. gallerycdn.vsassets.io (rozšíření hostitele služby Azure DevOps)

- static2.sharepointonline.com (prostředky hostitele, které Visual Studio používá v uživatelském rozhraní Office Fabric kit, jako je například písma)

- &#42;. nuget.org (pro připojení NuGet)

  > [!NOTE]
  > Soukromě vlastněných že nuget serverové adresy URL nemusí být zahrnuté v tomto seznamu. Můžete vyhledat servery NuGet, které používáte v % APPData%\Nuget\NuGet.Config.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Instalace a používání sady Visual Studio za bránou firewall nebo proxy serverem](install-and-use-visual-studio-behind-a-firewall-or-proxy-server.md)
* [Příručka správce sady Visual Studio](visual-studio-administrator-guide.md)
* [Instalace sady Visual Studio 2017](install-visual-studio.md)
