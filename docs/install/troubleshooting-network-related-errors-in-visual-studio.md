---
title: Řešení potíží s chybami související se sítí, když instalujete nebo použijte sadu Visual Studio
description: Najít řešení chyby související s sítě nebo proxy, které se můžete setkat při instalaci nebo použití sady Visual Studio za bránou firewall nebo proxy server.
ms.custom: ''
ms.date: 02/12/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e62b6ecddaa58ba8fd7172886bbf567402a03006
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36282649"
---
# <a name="troubleshooting-network-related-errors-when-you-install-or-use-visual-studio"></a>Řešení potíží s chybami související se sítí, když instalujete nebo použijte sadu Visual Studio

My jsme řešení nejčastější chyby související s sítě nebo proxy, které se můžete setkat při instalaci nebo použití sady Visual Studio za bránou firewall nebo proxy server.

## <a name="error-proxy-authorization-required"></a>Chyba: "Proxy autorizace požadované"

Této chybě obvykle dochází, když jsou uživatelé připojeni k Internetu prostřednictvím proxy serveru a proxy server blokuje volání, které provádí některým síťovým prostředkům v sadě Visual Studio.

### <a name="to-fix-this-proxy-error"></a>Chcete-li vyřešit tuto chybu proxy

- Restartujte sadu Visual Studio. By se zobrazit dialogové okno ověřování proxy serveru. Zadejte přihlašovací údaje po zobrazení výzvy v dialogovém okně.

- Pokud restartování sady Visual Studio není problém vyřešen, může to být proxy server nezobrazí výzvu pro přihlašovací údaje pro protokol http:&#47;&#47;go.microsoft.com adresy, ale nebude tak &#42;. visualStudio.com adresy. Pro tyto servery zvažte vytvoření seznamu povolených následující adresy URL odblokování všech scénářích přihlášení v sadě Visual Studio:

    - &#42;.windows.net

    - &#42;.microsoftonline.com

    - &#42;.visualstudio.com

    - &#42;.microsoft.com

    - &#42;.live.com

- V opačném případě můžete odebrat http:&#47;&#47;go.microsoft.com adresní ze seznamu povolených serverů, aby se objeví dialogové okno ověřování proxy serveru pro službu protokolu http:&#47;&#47;go.microsoft.com adresy a koncové body serveru, pokud je v sadě Visual Studio restartovat.

    NEBO

- Pokud chcete k použití výchozích pověření s proxy, můžete provádět následující akce:

    1. Najít **devenv.exe.config** (konfigurační soubor devenv.exe) v: **%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE** nebo **% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE**.

    1. V konfiguračním souboru najít `<system.net>` blokovat a poté přidejte tento kód:

        ```xml
        <defaultProxy enabled="true" useDefaultCredentials="true">
            <proxy bypassonlocal="True" proxyaddress=" HYPERLINK "http://<yourproxy:port#" http://<yourproxy:port#>"/>
        </defaultProxy>
        ```

        Je třeba vložit správné proxy adres pro vaši síť v `proxyaddress="<http://<yourproxy:port#>`.

    NEBO

- Můžete také podle pokynů v [postup připojení prostřednictvím ověřený server Proxy webové](http://blogs.msdn.com/b/rido/archive/2010/05/06/how-to-connect-to-tfs-through-authenticated-web-proxy.aspx) příspěvku na blogu, který ukazuje, jak přidat kód, který vám umožní použít proxy server.

## <a name="error-the-underlying-connection-was-closed"></a>Chyba: "základní připojení bylo ukončeno."

Pokud používáte Visual Studio v privátní síti, která má brána firewall, Visual Studio nemusí být možné se připojit k některým síťovým prostředkům. Tyto prostředky mohou zahrnovat Visual Studio Team Services (VSTS) pro přihlašování a licencování NuGet a službami Azure. Pokud Visual Studio se nepodaří připojit k jeden z těchto prostředků, zobrazí se následující chybová zpráva:

  **Základní připojení bylo ukončeno: došlo k neočekávané chybě při odesílání**

Visual Studio používá k připojení k síťovým prostředkům protokol zabezpečení TLS (Transport Layer) 1.2. Zabezpečovací zařízení v některých soukromých sítích blokují některá serverová připojení, když Visual Studio používá TLS 1.2.

### <a name="to-fix-this-connection-error"></a>Odstranění této chyby připojení

Povolte připojení pro následující adresy URL:

- https:&#47;&#47;management.core.windows.net

- https:&#47;&#47;app.vssps.visualstudio.com

- https:&#47;&#47;login.microsoftonline.com

- https:&#47;&#47;login.live.com

- https:&#47;&#47;go.microsoft.com

- https:&#47;&#47;graph.windows.net

- https:&#47;&#47;app.vsspsext.visualstudio.com

- &#42;. azurewebsites.net (pro Azure připojení)

- &#42;.visualstudio.com

- CDN.vsassets.IO (sítě pro doručování obsahu hostitele nebo CDN, obsah)

- &#42;. gallerycdn.vsassets.io (rozšíření hostitele služby VSTS)

- static2.sharepointonline.com (hostuje prostředky, které Visual Studio používá v sadě Office uživatelského rozhraní Fabric kit, jako je například písem)

- &#42;. nuget.org (pro připojení NuGet)

 > [!NOTE]
 > Soukromě vlastněných že URL serverů NuGet nemusejí být uvedené v tomto seznamu. Můžete zkontrolovat pro servery NuGet, které používáte ve % APPData%\Nuget\NuGet.Config.

## <a name="get-support"></a>Získat podporu

Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránky. Pokud žádná z instalace při řešení potíží pomoci, kontaktujte nás pomocí živé konverzace pro pomoc s instalací (pouze v angličtině). Podrobnosti najdete v tématu [stránky podpory sady Visual Studio](https://visualstudio.microsoft.com/vs/support/#talktous).

Tady je několik další možnosti podpory:

* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu a najít v odpovědi [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/).
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio). (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také:

* [Instalace a používání sady Visual Studio za bránou firewall nebo proxy serverem](install-and-use-visual-studio-behind-a-firewall-or-proxy-server.md)
* [Příručka správce sady Visual Studio](visual-studio-administrator-guide.md)
* [Nainstalovat Visual Studio 2017](install-visual-studio.md)
