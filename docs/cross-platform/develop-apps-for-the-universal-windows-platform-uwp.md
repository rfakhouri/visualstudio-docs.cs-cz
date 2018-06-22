---
title: Vývoj aplikací pro univerzální platformu Windows (UWP) | Microsoft Docs
ms.custom: ''
ms.date: 10/24/2017
ms.technology:
- tgt-pltfrm-cross-plat
ms.topic: conceptual
ms.assetid: eac59cb6-f12e-4a77-9953-6d62b164a643
author: stevehoag
ms.author: shoag
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 3d8de5ea7f4e42ba8a0e37bc982b38633b8bf53f
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36281596"
---
# <a name="develop-apps-for-the-universal-windows-platform-uwp"></a>Vývoj aplikací pro Univerzální platformu Windows (UWP)
Univerzální platformu Windows a naše jeden jádro systému Windows můžete spustit na jakékoli zařízení s Windows 10, z telefonů pro stolní počítače stejné aplikaci. Vytvořte tyto univerzální aplikace pro Windows s Visual Studio a nástroje pro vývoj pro univerzální aplikace pro Windows.

 ![Univerzální platformu Windows](../cross-platform/media/uwp_coreextensions.png "UWP_CoreExtensions")

 Spuštění aplikace na Windows 10 phone, Windows 10 desktop nebo Xbox. Jedná se o stejný balíček aplikace! Se zavedením jednotnou jádra Windows 10 můžete spustit jeden balíček aplikace pro všechny platformy. Několik platforem mít rozšíření sady SDK, které můžete přidat do vaší aplikace využívat výhod chování specifické pro platformu. Rozšíření sady SDK pro mobile například zpracovává stisknutou na Windows phone tlačítko Zpět. Pokud jste odkaz rozšíření sady SDK ve vašem projektu a pak stačí přidat runtime kontroly k testování této sady SDK je k dispozici na této platformě. To je, jak může mít stejný balíček aplikace pro každou platformu!

 **Co je jádro systému Windows?**

 Pro první má byl Windows rozdělili do mají společné základní pro všechny platformy Windows 10. Neexistuje jeden společný zdroj, jeden běžné jádro systému Windows, jeden zásobník vstupně-výstupní soubor a jeden model aplikace. Pro uživatelské rozhraní je jedním framework XAML uživatelského rozhraní a jeden HTML uživatelského rozhraní framework. Můžete soustředit na vytváření skvělá aplikace, protože jsme provedli jsme ho snadno tak, aby měl aplikace spustit na různých zařízeních Windows 10.

 **Co je přesně univerzální platformu Windows?**

Univerzální platformu Windows je jednoduše kolekce kontrakty a verze. To umožní cíl, kde můžete spustit aplikace. Už cíle operační systém; Nyní můžete cílit na jeden nebo více řadách zařízení. Další podrobnosti načtením [Úvod do univerzální platformy Windows](/windows/uwp/get-started/universal-application-platform-guide).

## <a name="requirements"></a>Požadavky
 Univerzální aplikace pro Windows nástrojů pro vývoj obsahují emulátorů, které můžete vidět, jak vaše aplikace vypadá na různých zařízeních. Pokud chcete použít tyto emulátorů, budete muset instalovat tento software na fyzickém počítači. Fyzický počítač musí běžet Windows 8.1 (x64) edice Professional nebo vyšší, a mít procesor, který podporuje klient Hyper-V a překlad adres druhé úrovně (SLAT). Emulátorů nelze použít při instalaci sady Visual Studio na virtuálním počítači.

 Tady je seznam softwaru, které potřebujete:

-   [Windows 10](http://windows.microsoft.com/windows/downloads). Visual Studio 2017 podporuje vývoj UWP jenom na Windows 10. Další podrobnosti najdete v sadě Visual Studio [cílení na platformy](/visualstudio/productinfo/vs2017-compatibility-vs) a [požadavky na systém](/visualstudio/productinfo/vs2017-system-requirements-vs).

-   [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017). Budete také potřebovat volitelné úlohy vývoj pro univerzální platformu Windows.

     ![Zatížení UWP](media/uwp_workload.png)

Po instalaci tohoto softwaru, musíte povolit zařízení s Windows 10 pro vývoj. V tématu [povolit zařízení pro vývoj](/windows/uwp/get-started/enable-your-device-for-development). Již nepotřebujete licenci vývojáře pro každé zařízení Windows 10.

## <a name="universal-windows-apps"></a>Univerzální aplikace pro Windows
Vyberte si jazyk upřednostňované vývoj z jazyka C#, Visual Basic, C++ nebo JavaScript k vytvoření aplikace pro univerzální platformu Windows pro zařízení s Windows 10. Čtení [vytvoření první aplikace](/windows/uwp/get-started/your-first-app) nebo sledování [přehled nástrojů pro Windows 10](http://channel9.msdn.com/Series/ConnectOn-Demand/229) videa.

Pokud máte existující aplikace Windows Store 8.1, Windows Phone 8.1 aplikace nebo aplikace Universal Windows, které byly vytvořeny s Visual Studiem 2015, budete potřebovat k portu těchto aplikací používat nejnovější univerzální platformu Windows. V tématu [přesunout z prostředí Windows Runtime 8.x do UWP](/windows/uwp/porting/w8x-to-uwp-root).

Po vytvoření aplikace pro Universal Windows, musíte sestavit balíček aplikaci instalovat do zařízení Windows 10 nebo odeslat na web Windows Store. V tématu [balení aplikací](/windows/uwp/packaging/index).

## <a name="see-also"></a>Viz také:
[Vývoj multiplatformních mobilních řešení v sadě Visual Studio](../cross-platform/cross-platform-mobile-development-in-visual-studio.md)
