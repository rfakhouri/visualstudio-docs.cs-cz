---
title: "Představení sady Visual Studio pro Mac | Microsoft Docs"
description: 
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: 3A130EC1-DD8C-4125-9034-B08D7AF7EA65
ms.openlocfilehash: bc836806e1acf33b35604419ac1d6aad41a2d795
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="introducing-visual-studio-for-mac"></a>Představení Visual Studio pro Mac

Visual Studio pro Mac je moderní, sofistikované IDE s mnoha funkcemi pro vytváření mobilních, plocha a webových aplikací. Podporuje vývoj z následujících akcí:

* Mobilní s .NET: Android, iOS, tvOS, watchOS
* Aplikací systému Mac
* Aplikace .NET core
* Základní webové aplikace ASP.NET
* Napříč platformami Unity hry

Zahrnuje a bohatě vybavený editor, ladění, nativní platforma integrace s iOS, Mac a Android a integrované správy zdrojového kódu pro název jen některé z jeho řadu funkcí.

Toto téma zjišťování různých oddílů sady Visual Studio pro Mac, poskytuje podívejte se na některé z funkcí, které umožňují výkonný nástroj pro vytváření aplikací pro různé platformy.

## <a name="installation"></a>Instalace

Postupujte podle kroků v [instalace](~/installation.md) Průvodce stahování a instalace Visual Studio for Mac.

## <a name="language-support"></a>Jazyková podpora

Visual Studio pro Mac podporuje vývoj v C# a F #, ve výchozím nastavení.

### <a name="c"></a>C#

C# je nejčastěji používané jazyk pro vytváření aplikací pro různé platformy v sadě Visual Studio for Mac. To zahrnuje plnou podporu všech funkcí jazyka C# 7.

### <a name="f"></a>F#

F # je silného typu funkční programovací jazyk určená ke spuštění na rozhraní .NET. Je k dispozici jako programovací jazyk pro Visual Studio pro Mac pro Android, Mac a iOS. Další informace o používání F # a ukázky vytvoření v jazyce, najdete [F #](https://developer.xamarin.com/guides/cross-platform/fsharp/) příručky.

## <a name="platform-support"></a>Podpora platformy

## <a name="net-core"></a>.NET Core

[.NET Core](https://www.microsoft.com/net/core#macos) je platforma pro vytváření aplikací, které běží na Windows, Linuxu a Macu. Visual Studio for Mac podporuje načítání, vytváření, používání a ladění projektů .NET Core.

Pro spouštění projektů .NET Core, musí být stažen a nainstalován .NET Core SDK.

Podpora .NET Core zahrnuje:

* C# a F# IntelliSense
* Šablony projektu .NET Core pro konzolu, knihovnu a webové aplikace
* Úplnou podporu ladění, včetně zarážek, zásobníku volání, okna kukátka a dalších funkcí
* Odkazy na balíčky NuGet a obnovení založené na MSBuildu
* Testování podporu pro spouštění a ladění testy s Visual Studio platforma testu, která je součástí rozhraní .NET Core SDK integrované částí.
* Migrace ze starý formát souboru project.json.

Abyste mohli začít, podívejte se na webové aplikace ASP.NET Core [praktické cvičení](https://github.com/Microsoft/vs4mac-labs/tree/master/Web/Getting-Started).

## <a name="xamarin"></a>Xamarin

Prvotřídní podpora [Xamarinu](https://developer.xamarin.com/) umožňuje vývoj propracovaných nativních možností pro Android, macOS, iOS, tvOS a watchOS. Multiplatformní aplikace Xamarin.Forms usnadňují sdílení kódu uživatelského rozhraní založeného na XAML mezi Androidem, iOSem a macOSem bez omezení přístupu k nativním funkcím.

Abyste mohli začít, podívejte se na mobilní aplikace [praktické cvičení](https://github.com/Microsoft/vs4mac-labs/tree/master/Mobile/Getting-Started).

### <a name="android"></a>Android

Visual Studio má svou vlastní integrované Android SDK manager.

Pro aplikace pro Android, Visual Studio pro Mac obsahuje vlastní designer, který funguje s Android `.axml` soubory vizuálně vytvořit uživatelská rozhraní. Visual Studio pro Mac se otevřou tyto soubory v jeho Android designer, jak je uvedeno níže:

![](media/intro-image31.png)

Další informace o Android návrháře najdete [Návrhář přehled](https://developer.xamarin.com/Android/Guides/User_Interface/Designer_Overview) dokumentu.

### <a name="ios"></a>iOS

IOS Designer jsou plně integrované s Visual Studio pro Mac a umožňuje úpravy s náhledem .xib a scénáře soubory a vytvořte iOS, tvOS a WatchOS uživatelská rozhraní a přechody. Celé uživatelské rozhraní se dají vytvářet pomocí přetahování myší funkce mezi sada nástrojů a návrhovou plochu, při použití intuitivní prostředí pro zpracování událostí. Návrhář také podporuje iOS [vlastní ovládací prvky](https://developer.xamarin.com/guides/ios/user_interface/designer/ios_designable_controls_overview/) s výhodu v době návrhu vykreslování.

![](media/intro-image30.png)

Další informace o použití iOS Designer, najdete v části [Návrhář](https://developer.xamarin.com/guides/ios/user_interface/designer) dokumenty.

### <a name="mac"></a>Mac

Xamarin poskytuje nativní vazby Mac rozhraní API umožňuje vytvořit Krásný aplikací systému Mac.

Další informace o psaní aplikací systému Mac pomocí sady Visual Studio pro Mac, najdete v části [Xamarin.Mac](https://developer.xamarin.com/guides/#mac) dokumentaci.

## <a name="gaming"></a>Herní

Visual Studio pro Mac poskytuje podporu pro vývoj napříč platformami hry s Unity 5.6.1.

Abyste mohli začít, podívejte se Unity [praktické cvičení](https://github.com/Microsoft/vs4mac-labs/tree/master/Unity/Getting-Started).

## <a name="enterprise-features"></a>Funkce Enterprise

> [!Note]
> Tyto produkty dá použít jenom s předplatným Visual Studio Enterprise.

### <a name="profiler"></a>profiler

Xamarin profileru má tří nástrojů pro profilaci. [Úvod do profileru Xamarin](https://developer.xamarin.com/guides/cross-platform/deployment,_testing,_and_metrics/xamarin-profiler/) průvodce jsou zde popsány co měřit těchto nástrojů a jak se analyzovat vaše aplikace a vysvětluje význam údaje zobrazené na jednotlivých obrazovky.

### <a name="inspector"></a>Nástroj Inspector

Xamarin Inspector poskytuje interaktivní C# konzole nástroje pro uživatele. Při kontrole aplikací pro živé, jako nástroj pro vyučující jako dokumentace nástroje nebo experimentování může sloužit jako podpora ladění nebo diagnostiky.

![](media/intro-inspector.png)

Skládá se z samostatná aplikace, která poskytuje bohaté C# konzolu, která můžete vybrat různé programovací platformy (Android, iOS, Mac a Windows) a také integraci do ladění pracovní postup vaší IDE.

Další informace najdete v části [Xamarin Inspector](https://developer.xamarin.com/guides/cross-platform/inspector/) průvodce.

## <a name="next-steps"></a>Další kroky

* **Získat velký obrázek** – Pokud chcete získat přehled o řadu hlavní funkce v sadě Visual Studio pro Mac, najdete v sadě Visual Studio pro Mac [IDE prohlídka](~/ide-tour.md).
* **Instalační program** – Další informace o tom, jak stáhnout a nainstalovat Visual Studio naleznete [instalace](~/installation.md) průvodce.
* **Kurzy Xamarin** – Další informace o tom, jak vytvořit kód s Xamarin, přejděte na Xamarin [středisku pro vývojáře](https://developer.xamarin.com).
* **Videa** – Pokud chcete další informace o dalších funkcích a aspekty sady Visual Studio pro Mac, podívejte se na videa na [Xamarin univerzity](https://university.xamarin.com) webu.
* **Praktická cvičení** – Pokud chcete začít používat různé úlohy, které jsou zahrnuté v sadě Visual Studio pro Mac, podívejte se [praktická cvičení](https://github.com/Microsoft/vs4mac-labs).