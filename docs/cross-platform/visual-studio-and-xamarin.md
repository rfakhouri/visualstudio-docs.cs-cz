---
title: Visual Studio a Xamarin | Dokumentace Microsoftu
ms.custom: ''
ms.date: 03/30/2018
ms.technology: vs-ide-mobile
ms.topic: conceptual
ms.assetid: 1da4064f-af69-472c-8f31-98484be5f790
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: ef599a67dcb81586bd31fd08836c0a95b812bde1
ms.sourcegitcommit: 71b307ce86c4079cc7ad686d8d5f96a6a123aadd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/25/2018
ms.locfileid: "39251224"
---
# <a name="visual-studio-and-xamarin"></a>Visual Studio a Xamarin

Xamarin je platforma pro vývoj mobilních aplikací pro vytváření nativních aplikací pro iOS, Android a Windows aplikace z common jazyka C# / .NET code base. Aplikace vytvořené pomocí Xamarinu můžete dosáhnout 75 % na téměř 100 % opakované využívání kódu mezi platformami. Tyto aplikace mají plný přístup k rozhraní API základní platformy a rozšiřovat nativní uživatelská rozhraní. Jsou kompilovány do balíčků specifických pro platformu s malým dopadem na výkon modulu runtime. (Poznámka: Xamarin také podporuje F #, ale tato dokumentace se soustředí pouze k jazyku C#. Visual Basic není v tuto chvíli nepodporuje.)

Vývojáři, kteří znají C#, .NET a Visual Studio bude využívat stejný výkon a produktivitu při práci s využitím kódu Xamarin pro mobilní aplikace. Mezi tyto výhody patří vzdáleného ladění na zařízení s Androidem, iOS a Windows, bez nutnosti učit nativní kódování jazycích Objective-C nebo Java. Je trochu překvapením a potom daný počet vysoce výkonné aplikace s krásná uživatelská rozhraní, jako je například NASCAR, Aviva a MixRadio – byly vytvořené pomocí Xamarinu.

Tato dokumentace vám pomůže vyhodnotit potenciál **Visual Studio s Xamarinem** k vytváření těchto možností.

-   Začněte s [nastavení a instalaci](../cross-platform/setup-and-install.md), proces, který bude trvat delší dobu (obvykle 2 – 4 hodin v závislosti na rychlosti připojení k Internetu, co jste již nainstalovali a možností, které zvolíte).

-   Zatímco instalační programy jsou spuštěny, je možné [přečtěte si víc o vývoj mobilních řešení s využitím kódu Xamarin](learn-about-mobile-development-with-xamarin.md) které zjistíte informace o povaze Xamarin, porovnat Xamarin.Forms k nativním uživatelským rozhraním a další.

-   Až se instalace dokončí, [ověření prostředí Xamarinu](../cross-platform/verify-your-xamarin-environment.md).

-   Dokončit tak, že přejdete v průběhu kurzu [základy vytváření aplikací s Xamarin.Forms v sadě Visual Studio](learn-app-building-basics-with-xamarin-forms-in-visual-studio.md).

Můžete pracovat se všemi funkcemi Xamarin pomocí [libovolná edice sady Visual Studio 2017](https://visualstudio.microsoft.com/vs) (Community, Professional a Enterprise). Vyžaduje se bez samostatné licence služby.

> [!NOTE]
>  Tyto pokyny popisují konfiguraci nejjednodušší a nejjednodušší počítače pro vývojáře, kteří mají Windows a Visual Studio na pozadí. S touto konfigurací celkové prostředí vývoje je jednodušší, protože je potřeba jenom komunikovat s počítači Mac použít simulátor iOS a zařízení připojených formou tetheringu. Pokud místo toho pocházet z Mac na pozadí, doporučujeme, abyste spuštění sady Visual Studio uvnitř Parallels nebo VMWare, nebo pomocí sady Visual Studio pro Mac. Odkazovat na [instalační program, instalace a ověření pro uživatele počítačů Mac](../cross-platform/setup-install-and-verifications-for-mac-users.md) pokyny.

> [!NOTE]
>  Pokud potřebujete pro vývoj pro různé platformy řešení založeného na HTML a CSS, projděte si Visual Studio Tools pro Apache Cordova, jak je popsáno v [vývoj pro různé platformy v sadě Visual Studio](../cross-platform/cross-platform-mobile-development-in-visual-studio.md#HTML).