---
title: Visual Studio a Xamarin | Microsoft Docs
ms.custom: ''
ms.date: 03/30/2018
ms.reviewer: ''
ms.suite: ''
ms.technology: vs-ide-mobile
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1da4064f-af69-472c-8f31-98484be5f790
caps.latest.revision: 10
author: charlespetzold
ms.author: chape
manager: crdun
ms.workload:
- xamarin
ms.openlocfilehash: be1739a83e05ca55fa288fa707b37fddb095cc57
ms.sourcegitcommit: a0a49cceb0fdc1465ddf76d131c6575018b628b8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/05/2018
---
# <a name="visual-studio-and-xamarin"></a>Visual Studio a Xamarin

Xamarin je platforma pro vývoj mobilních aplikací pro vytváření nativní aplikace pro iOS, Android a Windows aplikace z běžných C# / .NET code base. Aplikací napsaných pomocí Xamarinu můžete dosáhnout 75 % na téměř 100 % opětovné použití kódu mezi platformami. Tyto aplikace mají plný přístup k rozhraní API základní platformu a můžete začlenit nativní uživatelská rozhraní. By kompilovat specifické pro platformu balíčky s malým dopadem na výkon modulu runtime. (Poznámka: Xamarin také podporuje F #, ale tato dokumentace se soustředí pouze na C#. Visual Basic není v současné době podporovaný.)  
  
Vývojáři, kteří znají C# .NET a Visual Studio bude získejte stejný výkon a produktivitu při práci s funkcí Xamarin pro mobilní aplikace. Tyto výhody patří vzdáleného ladění na zařízení Android, iOS a Windows, aniž by museli další nativní programovacích jazyků jako jazyka Objective-C nebo Java. Je málo neočekávaném pak tolika vysoce výkonné aplikace s Krásný uživatelského rozhraní – například NASCAR, Aviva a MixRadio – které se sestavily pomocí Xamarin.  
  
Tato dokumentace vám pomůže vyhodnotit potenciál **Visual Studio s Xamarinem** s cílem vytvořit tyto.  
  
-   Začněte s [nastavení a instalaci](../cross-platform/setup-and-install.md), proces, který bude trvat delší dobu (obvykle 2 – 4 hodin v závislosti na rychlosti připojení k Internetu, co jste již nainstalovali a možnosti výběru).  
  
-   V době spuštění instalační programy, můžete [Další informace o pro vývoj mobilních řešení s Xamarinem](learn-about-mobile-development-with-xamarin.md) kterého bude vás informovat o povaze Xamarin, porovnat Xamarin.Forms na nativní uživatelského rozhraní a další.  
  
-   Po dokončení instalace [ověřte prostředí Xamarin](../cross-platform/verify-your-xamarin-environment.md).  
  
-   Dokončit prostřednictvím tohoto kurzu [další základy vytváření aplikací s Xamarin.Forms v sadě Visual Studio](/learn-app-building-basics-with-xamarin-forms-in-visual-studio.md).  
  
Můžete pracovat se všemi funkcemi Xamarin pomocí [libovolná edice Visual Studio 2017](https://www.visualstudio.com/vs) (Community, Professional a Enterprise). Je vyžadována bez samostatné licence.  
  
> [!NOTE]
>  Tyto pokyny popisují konfiguraci počítače nejjednodušší a nejjednodušší pro vývojáře, kteří mají na pozadí systému Windows Server a Visual Studio. Pomocí této konfigurace celkové vývojového prostředí je jednodušší, protože potřebujete pracovat s Mac používat simulátoru iOS a připojené zařízení. Pokud místo toho pocházet z pozadí Mac, doporučujeme, abyste buď spuštění sady Visual Studio v Parallels nebo VMWare, nebo pomocí sady Visual Studio for Mac. Odkazovat na [nastavení, instalaci a ověření pro uživatele Mac](../cross-platform/setup-install-and-verifications-for-mac-users.md) pokyny.  
  
> [!NOTE]
>  Pokud hledáte řešení vývoj pro různé platformy, HTML a CSS, podívejte se na Visual Studio Tools pro Apache Cordova jak je popsáno v [vývoj pro různé platformy v sadě Visual Studio](../cross-platform/cross-platform-mobile-development-in-visual-studio.md#HTML).