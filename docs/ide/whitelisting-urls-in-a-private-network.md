---
title: "Vytvoření seznamu povolených adres URL v privátní síti | Microsoft Docs"
ms.custom: 
ms.date: 09/19/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 4a4093c7ebba74493a64833bfbf83ee6d28ef1ef
ms.sourcegitcommit: 06cdc1651aa7f45e03d260080da5a623d6258661
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/15/2018
---
# <a name="whitelisting-urls-in-a-private-network"></a>Vytvoření seznamu povolených adres URL v privátní síti

Pokud používáte Visual Studio v privátní síti, která používá o zabezpečení zařízení, jako je například Brána firewall, Visual Studio nemusí být možné se připojit k některým síťovým prostředkům. Tyto prostředky zahrnují Visual Studio Team Services (VSTS) pro přihlašování a licencování NuGet a službami Azure. Pokud Visual Studio se nepodaří připojit k jeden z těchto prostředků, zobrazí se následující chybová zpráva:

  **Základní připojení bylo ukončeno: došlo k neočekávané chybě při odesílání**

Visual Studio používá k připojení k síťovým prostředkům protokol zabezpečení TLS (Transport Layer) 1.2. Zabezpečovací zařízení v některých soukromých sítích blokují některá serverová připojení, když Visual Studio používá TLS 1.2. Chcete-li opravit chyby, povolte připojení pro následující adresy URL:

- https://management.core.windows.net

- https://app.vssps.visualstudio.com

- https://login.microsoftonline.com

- https://login.live.com

- https://go.microsoft.com

- https://graph.windows.net

- https://app.vsspsext.visualstudio.com

- *. azurewebsites.net (pro Azure připojení)

- *. nuget.org (pro připojení NuGet)

- *.visualstudio.com

- CDN.vsassets.IO (sítě pro doručování obsahu hostitele nebo CDN, obsah)

- *. gallerycdn.vsassets.io (rozšíření hostitele služby VSTS)

- static2.sharepointonline.com (hostuje prostředky, které Visual Studio použije v prostředcích infrastruktury office kit uživatelského rozhraní, jako je například písem)

> [!NOTE]
> Soukromě vlastněných že URL serverů NuGet nemusejí být uvedené v seznamu výš. Servery NuGet, které používáte, můžete zkontrolovat otevřením %APPData%\Nuget\NuGet.Config.

## <a name="see-also"></a>Viz také

[Chyba autorizace vyžaduje proxy server](../ide/reference/proxy-authorization-required.md)  
[Instalaci sady Visual Studio za serverem brány firewall nebo proxy server](../install/install-visual-studio-behind-a-firewall-or-proxy-server.md)
