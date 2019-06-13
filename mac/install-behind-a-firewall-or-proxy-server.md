---
title: Instalace a používání sady Visual Studio pro Mac za bránou firewall nebo proxy serverem
description: Tento dokument obsahuje seznam hostitelů, které musí být povoleno v bráně firewall umožníte softwaru Visual Studio pro Mac (a její úlohy, včetně Xamarinu) pro práci v podnikovém prostředí.
ms.topic: troubleshooting
ms.assetid: 79C0F1A3-0C13-4E55-A820-1138A4082B77
author: asb3993
ms.author: amburns
ms.date: 10/23/2018
ms.openlocfilehash: 6f3afd51cf4109f07107e60d61565c9126fc5ee7
ms.sourcegitcommit: 91c7f1b525e0c22d938bc4080ba4ceac2483474f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/12/2019
ms.locfileid: "67032787"
---
# <a name="install-and-use-visual-studio-for-mac-behind-a-firewall-or-proxy-server"></a>Instalace a používání sady Visual Studio pro Mac za bránou firewall nebo proxy serverem

Pokud vy nebo vaše organizace používá bezpečnostní opatření, jako je například Brána firewall nebo proxy server, pak jsou domény může být vhodné přidat do "seznamu povolených" a porty a protokoly, které může být vhodné a otevřete tak, abyste měli co nejlepších výsledků při instalaci a použití vztahu Protokolování přístupu uživatele Studio pro Mac a služby Azure.


- [**Install Visual Studio for Mac**](#install-visual-studio-for-mac): Tyto tabulky obsahují domény, které musí umožňovat připojení, abyste měli přístup ke všem funkcím a úlohy sady Visual Studio pro Mac.

- [**Pomocí sady Visual Studio pro Mac**](#use-visual-studio-for-mac): Tyto tabulky obsahují domény, které musí umožňovat připojení, abyste měli přístup k související funkce.

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
| static.xamarin.com | Instalační balíčky|
| dl.xamarin.com | Instalační balíčky|
| dc.services.visualstudio.com| Oznamování chyb |

### <a name="third-party-domains"></a>Domény třetí strany

| Doména| Účel |
| --------------------------|-------------------------|
| dl.google.com | Android SDK |
| download.oracle.com | Java SDK|
| api.apple-cloudkit.com| Zabezpečení služeb Apple |

## <a name="use-visual-studio-for-mac"></a>Pomocí sady Visual Studio pro Mac

Pokud chcete mít jistotu, že máte přístup pro všechny funkce, které potřebujete v sadě Visual Studio pro Mac během za proxy nebo brány firewall, doporučujeme přidat následující porty a domény do seznamu Povolené přístupu.

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

- [Instalace a používání sady Visual Studio a služeb Azure za bránou firewall nebo proxy serverem](/visualstudio/install/install-and-use-visual-studio-behind-a-firewall-or-proxy-server)
- [Řešení potíží s obdobným problémům ve Windows](/visualstudio/install/troubleshooting-network-related-errors-in-visual-studio)
