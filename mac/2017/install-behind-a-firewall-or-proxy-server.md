---
title: Instalace a používání sady Visual Studio pro Mac za bránou firewall nebo proxy serverem
description: Tento dokument obsahuje seznam hostitelů, které musí být uvedeny v seznamu povolených v bráně firewall povolit sady Visual Studio pro Mac (a její úlohy, včetně Xamarinu) pro práci v podnikovém prostředí.
ms.topic: troubleshooting
ms.assetid: 79C0F1A3-0C13-4E55-A820-1138A4082B77
author: asb3993
ms.author: amburns
ms.date: 10/23/2018
ms.openlocfilehash: 70ac8defdcea9cccd8a3b3f9be71d38fb78c9c50
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62997956"
---
# <a name="install-and-use-visual-studio-for-mac-behind-a-firewall-or-proxy-server"></a>Instalace a používání sady Visual Studio pro Mac za bránou firewall nebo proxy serverem

Pokud vy nebo vaše organizace používá bezpečnostní opatření, jako je například Brána firewall nebo proxy server, pak používají domény adresy URL, které můžete chtít "seznamu povolených IP adres" a porty a protokoly, které můžete chtít otevřít, abyste měli co nejlepších výsledků při instalaci a použití samostatného Visual dio pro Mac a služby Azure.

- [**Install Visual Studio for Mac**](#install-visual-studio-for-mac): Tyto tabulky obsahují adresy URL do seznamu povolených IP adres, abyste měli přístup ke všem funkcím a úlohy sady Visual Studio pro Mac.

- [**Pomocí sady Visual Studio pro Mac**](#use-visual-studio-for-mac): Abyste měli přístup ke všem službám a funkcím, které mají tyto tabulky obsahují adresy URL do seznamu povolených IP adres.

## <a name="install-visual-studio-for-mac"></a>Instalace sady Visual Studio pro Mac

Vzhledem k tomu, že Visual Studio pro Mac – instalační program stáhne z různých domén a stáhněte si servery, tady jsou domén a adres URL, které chcete přidat jako důvěryhodné ve vašich konfiguracích.

### <a name="microsoft-domains"></a>Microsoft domains

| Domény| Účel |
| ----------------------------------- |---------------------------|
| *.live.com| Správa přihlašovacích údajů |
| app.vssps.visualstudio.com| Instalační program metadat|
| vortex.data.microsoft.com | O chybách a hlášení chyb |
| az667904.vo.msecnd.net| O chybách a hlášení chyb |
| xamarin.com | Instalační program metadat|
| xampubdl.blob.core.windows.net| Instalační balíčky|
| download.visualstudio.microsoft.com | Instalační balíčky|
| xamarin.azureedge.net | Instalační balíčky|
| developer.xamarin.com | Instalační balíčky|
| dc.services.visualstudio.com| Oznamování chyb |

### <a name="third-party-domains"></a>Domény třetí strany

| Doména| Účel |
| --------------------------|-------------------------|
| dl.google.com | Android SDK |
| download.oracle.com | Java SDK|
| api.apple-cloudkit.com| Zabezpečení služeb Apple |

## <a name="use-visual-studio-for-mac"></a>Pomocí sady Visual Studio pro Mac

Pokud chcete mít jistotu, že máte přístup pro všechny funkce, které potřebujete v sadě Visual Studio pro Mac během za proxy nebo brány firewall, doporučujeme na seznam povolených následující domény a porty.

### <a name="general"></a>Obecné

| Doména | Port(y) pro|Účel|
| ----------------------|------------------|------------------|
| go.microsoft.com | 80/443|Adresa URL služby Microsoft řešení |
| vsstartpage.blob.core.windows.net| 80/443| Data úvodní stránky|
| software.xamarin.com |  80/443|Aktualizační službu|
| addins.monodevelop.com | 80/443| Služby rozšíření |
| visualstudio-devdiv-c2s.msedge.net | 80/443| Experimentální funkce a oznámení |
| targetednotifications.azurewebsites.net|  80/443| Slouží k filtrování globální seznam oznámení do seznamu, který se vztahuje pouze na konkrétní typy počítačů nebo použití scénáře|

### <a name="identity"></a>Identita

| Doména | Port(y) pro|Účel|
| ----------------------|------------------|------------------|
| login.microsoftonline.com | 80/443| Zprostředkovatel identity|
| secure.aadcdn.microsoftonline-p.com | 80/443|Zprostředkovatel identity|
| dc.services.visualstudio.com| 80/443|Oznamování chyb|
| management.azure.com|80/443| Azure Services API |

### <a name="nuget"></a>NuGet

| Doména | Port(y) pro|Účel|
| ----------------------|------------------|------------------|
| api.nuget.org | 80/443|NuGet API|
| secure.aadcdn.microsoftonline-p.com |80/443| Zprostředkovatel identity|

### <a name="android-projects"></a>Projekty Android

| Doména| Účel|
| ------------------------------------|------------------------------------|
| time.android.com| Čas serveru pro emulátor Androidu |
| connectivitycheck.gstatic.com | Připojení k emulátoru Androidu|
| cloudconfig.googleapis.com| Rozhraní API a emulátor pro Android|

## <a name="see-also"></a>Viz také:

- [Instalace a používání sady Visual Studio 2017 a služeb Azure za bránou firewall nebo proxy serverem](/visualstudio/install/install-and-use-visual-studio-behind-a-firewall-or-proxy-server)
- [Řešení potíží s obdobným problémům ve Windows](/visualstudio/install/troubleshooting-network-related-errors-in-visual-studio)
