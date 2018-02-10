---
title: Visual Studio a Xamarin | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-mobile
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1da4064f-af69-472c-8f31-98484be5f790
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- xamarin
ms.openlocfilehash: e550d7f6220d4d555d8427bcb1c2a3e814a4f5c3
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="visual-studio-and-xamarin"></a>Visual Studio a Xamarin
Xamarin je platforma pro vývoj mobilních aplikací pro vytváření nativní aplikace pro iOS, Android a Windows aplikace z běžných C# / .NET code základ, dosažení 75 % na téměř 100 % opětovné použití kódu mezi platformami. Aplikace, které jsou napsané pomocí Xamarinu a C# mají plný přístup k základní platformu rozhraní API a možnost vytvářet nativní uživatelská rozhraní a zkompilovat specifické pro platformu balíčků, je malý vliv na výkon modulu runtime. (Poznámka: Xamarin také podporuje F #, ale tato dokumentace se soustředí pouze na C#. Visual Basic není v současné době podporovaný.)  
  
 Přesto lépe vývojáři, kteří znají C# .NET a Visual Studio bude požívá stejné napájení a produktivitu při práci s funkcí Xamarin pro mobilní aplikace, včetně vzdáleného ladění na zařízení Android, iOS a Windows – bez nutnosti další nativní kódování jazyky jako jazyka Objective-C nebo Java. Je málo neočekávaném pak tolika vysoký výkon aplikací s Krásný uživatelského rozhraní – například NASCAR, Aviva a MixRadio – které se sestavily pomocí Xamarin.  
  
 Tato dokumentace vám pomůže vyhodnotit všech možnostech **Visual Studio s Xamarinem** s cílem vytvořit tyto.  
  
-   Začněte s [nastavení a instalaci](../cross-platform/setup-and-install.md), proces, který bude trvat delší dobu (obvykle 2 – 4 hodin v závislosti na rychlosti připojení k Internetu, co jste již nainstalovali a možnosti výběru).  
  
-   V době spuštění instalační programy, můžete [Další informace o pro vývoj mobilních řešení s Xamarinem](../cross-platform/learn-about-mobile-development-with-xamarin.md) kterého bude vás informovat o povaze Xamarin, porovnat Xamarin.Forms na nativní uživatelského rozhraní a další.  
  
-   Po dokončení instalace [ověřte prostředí Xamarin](../cross-platform/verify-your-xamarin-environment.md).  
  
-   Dokončit prostřednictvím tohoto kurzu [další základy vytváření aplikací s Xamarin.Forms v sadě Visual Studio](../cross-platform/learn-app-building-basics-with-xamarin-forms-in-visual-studio.md).  
  
 Můžete pracovat se všemi funkcemi Xamarin prostřednictvím [libovolná edice sady Visual Studio 2015](https://www.visualstudio.com/vs-2015-product-editions) (Community, Professional a Enterprise). Všimněte si také, že od 31. března 2016 Xamarin je součástí všech edic Visual Studio 2015 a už vyžaduje samostatné licence. Pro Visual Studio 2013, můžete nainstalovat Xamarin samostatně, jako [nastavení a instalaci](../cross-platform/setup-and-install.md) téma popisuje.  
  
> [!NOTE]
>  Tyto pokyny popisují konfiguraci počítače nejjednodušší a nejjednodušší pro ty, které mají na pozadí systému Windows Server a Visual Studio. Pomocí této konfigurace celkové vývojového prostředí je jednodušší, protože potřebujete pracovat s Mac používat simulátoru iOS a připojené zařízení. Pokud místo toho pocházet z pozadí Mac, doporučujeme, abyste buď spuštění sady Visual Studio v Parallels nebo VMWare, nebo pomocí Xamarin Studio Community. Odkazovat na [nastavení, instalaci a ověření pro uživatele Mac](../cross-platform/setup-install-and-verifications-for-mac-users.md) pokyny.  
  
> [!NOTE]
>  Pokud hledáte řešení vývoj pro různé platformy, HTML a CSS, podívejte se na Visual Studio Tools pro Apache Cordova jak je popsáno v [vývoj pro různé platformy v sadě Visual Studio](../cross-platform/cross-platform-mobile-development-in-visual-studio.md#HTML).