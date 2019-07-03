---
title: Novinky v sadě Visual Studio 2019
titleSuffix: ''
description: Další informace o nových funkcích sady Visual Studio 2019.
ms.date: 06/29/2019
helpviewer_keywords:
- Visual Studio, what's new
- what's new [Visual Studio]
ms.assetid: 00bec66b-bcee-46f5-91d9-f73a2b469744
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
ms.topic: conceptual
ms.workload:
- multiple
ms.openlocfilehash: 6b5387fa61686d85e02c200a0a50cffa9e5aa155
ms.sourcegitcommit: c7b9ab1bc19d74b635c19b1937e92c590dafd736
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/03/2019
ms.locfileid: "67552866"
---
# <a name="whats-new-in-visual-studio-2019"></a>Novinky v sadě Visual Studio 2019

**Aktualizováno pro [16.1 vydání](/visualstudio/releases/2019/release-notes/)**

>[!div class="button"]
>[Stáhněte si Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)

Visual Studio 2019 získáte ve své třídě nejlepší nástroje a služby pro všechny vývojáře, aplikace a jakoukoli platformu. Ať už používáte Visual Studio poprvé nebo jste dosud používali ho let, není v této nové verzi, jako je mnoho dalších!

Tady je podrobný rekapitulace toho, co je nového:

* **[Vývoj](#develop)** : Udržte si zaměření a produktivity pomocí Vylepšený výkon, rychlé kód čištění a lepší výsledky hledání.
* **[Spolupráce](#collaborate)** : Využijte přirozené spolupráci prostřednictvím Git první pracovní postup v reálném čase, úpravy a ladění, a revize kódu přímo v sadě Visual Studio.
* **[Ladění](#debug)** : Zvýrazněte a přejděte na konkrétní hodnoty, optimalizovat využití paměti a provést automatické snímky spuštění vaší aplikace.

Úplný seznam všech, který je v této verzi nové, najdete v článku [poznámky k verzi](/visualstudio/releases/2019/release-notes/).

## <a name="develop"></a>Vývoj

Zobrazte na následující video a další informace o tom, jak můžete ušetřit čas s novými funkcemi. <br><br>*Délka videa: 3.00 minut*

> [!VIDEO https://www.youtube.com/embed/n5sJ4EewKGk]

### <a name="improved-search"></a>Vylepšené vyhledávání

Dříve označované jako Snadné spuštění, naše nové rozhraní pro hledání je rychlejší a efektivnější. Nyní výsledky hledání zobrazeny dynamicky během psaní. A výsledky hledání můžete často obsahují klávesové zkratky pro příkazy, takže můžete snadno pamatovat pro budoucí použití.

   ![Animaci, která nové rozhraní pro hledání v aplikaci Visual Studio 2019](media/vs-2019/new-search-feature.gif)

Nové vyhledávání přibližných shod logiky najdete všechno, co potřebujete, bez ohledu na to, překlepy. Takže ať už hledáte příkazů a nastavení nebo další užitečné věci, nová funkce vyhledávání je snazší najít, co hledáte.

### <a name="refactorings"></a>Refaktoring

Existuje velké množství refaktoringů, nových a velmi užitečné v C# , které usnadňují uspořádání vašeho kódu. Se zobrazují jako návrhy v žárovky a zahrnují akce, jako je například přesun členy rozhraní nebo základní třídy, obory názvů k nastavení odpovídají strukturu složek, převeďte smyčky foreach do dotazů Linq a dalších.

   ![Animace prostředí refaktoringy Visual Studio 2019](media/vs-2019/refactorings.gif)

Jednoduše vyvolat refaktoringy stisknutím kombinace kláves **Ctrl +.** a vyberte akci, kterou chcete převést.

### <a name="intellicode"></a>IntelliCode

[Visual Studio IntelliCode](/visualstudio/intellicode/) vylepšuje své úsilí vývoje softwaru pomocí umělé inteligence (AI). IntelliCode železniční napříč 2 000 open-source projektů na Githubu&mdash;každý s více než 100 hvězdiček&mdash;ke generování doporučení.

 ![Animace IntelliCode v Visual Studio 2019](media/vs-2019/IntelliCode.gif)

Tady je několik způsobů, jak Visual Studio IntelliCode může pomoct zvýšit produktivitu práce:

* Doručování dokončování s ohledem na kontext kódu
* Příručka pro vývojáře dodržovat vzory a styly jejich tým
* Najít problémy s kódu obtížné catch
* Revize kódu fokus kreslením upozornit na oblasti, které jsou opravdu důležité.

Zpočátku podporujeme pouze C# když jsme první předběžně IntelliCode jako rozšíření pro Visual Studio. Nyní **novinkou 16.1**, přidali jsme podporu pro C# a XAML "in-the-box". (Podpora C++ a TypeScript/JavaScript jsou stále ve verzi preview, ale.)

A pokud používáte C#, přidali jsme také možnost pro trénování modelu vlastní na váš vlastní kód.

Další informace o IntelliCode, najdete v článku [oznamujeme obecnou dostupnost IntelliCode a vás zajímá Náhled](https://devblogs.microsoft.com/visualstudio/announcing-the-general-availability-of-intellicode-plus-a-sneak-peek/) a [více kódu, posuňte se menší s Visual Studio IntelliCode](https://devblogs.microsoft.com/visualstudio/code-more-scroll-less-with-visual-studio-intellicode/) blogové příspěvky.

### <a name="code-cleanup"></a>Kód čištění

Spárovat s nový indikátor stavu dokumentu je nový příkaz vyčištění kódu. Tento nový příkaz slouží k identifikaci a potom opravit upozornění a návrhy kliknutím na tlačítko.

Čištění formátovat kód, který se použije všechny opravy kódu jak navrhovaly [aktuální nastavení](code-styles-and-code-cleanup.md) a [soubory .editorconfig](create-portable-custom-editor-options.md).

   ![Snímek obrazovky nového ovládacího prvku vyčištění kódu v aplikaci Visual Studio 2019](media/vs-2019/code-cleanup-profile.png)

Kolekce fixers můžete také uložit jako profil. Například pokud máte malou sadu cílových fixers, které můžete použít při kódu můžete často, a pak máte jiné komplexní sadu fixers použít před přezkoumání kódu, můžete nakonfigurovat profily k vyřešení těchto různých úloh.

   ![Snímek obrazovky konfigurace kód čištění ovládacího prvku na Visual Studio 2019](media/vs-2019/code-cleanup-profile-configure.png)

### <a name="per-monitor-aware-pma-rendering"></a>Clustery vykreslování (PMA) na monitorování

Pokud používáte monitorování, které jsou nakonfigurovány s jiným zobrazením měřítko nebo vzdáleně připojit k počítači s použitím zobrazení škálování faktorů, které se liší od hlavní zařízení, můžete všimnout, že Visual Studio rozmazaný nebo vykreslí nesprávné měřítko.

Ve verzi Visual Studio 2019 nyní Visual Studio (PMA) aplikace pracující s za monitorování. Nyní Visual Studio správně vykresluje bez ohledu na škálování faktorů zobrazení, které používáte.

   ![Clustery vykreslování (PMA) v aplikaci Visual Studio 2019 za monitorování](media/vs-2019/pma-dpi-scaling.png)

Další informace najdete v tématu [lepší prostředí pro více monitorů s Visual Studio 2019](https://devblogs.microsoft.com/visualstudio/a-better-multi-monitor-experience-with-visual-studio-2019/) blogový příspěvek.

## <a name="collaborate"></a>Spolupráce

Zobrazte na následující video a další informace o tom, jak můžete seskupit vyřešit nějaký problém. <br><br>*Délka videa: 4.22 minut*

> [!VIDEO https://www.youtube.com/embed/dKLJsiK1QU8]

### <a name="cloud-first-workflow"></a>Cloudového pracovního postupu

Určitě si všimnete, když spustíte Visual Studio 2019 je její nové okno start.

   ![Snímek obrazovky okna Nový start v aplikaci Visual Studio 2019](media/vs-2019/start-window-dark.png)

V okně spuštění vám nabídne několik možností, jak můžete rychle získat kód. Jsme jste umístili možnost klonovat rezervaci nebo vrácení kódu z úložiště, poprvé.

   ![Animace prostředí Git první Visual Studio 2019](media/vs-2019/git-first.gif)

V okně start zahrnuje také možnosti Otevřít projekt nebo řešení, otevřete místní složku nebo vytvořte nový projekt.

Další informace najdete v tématu [získat kód: Jak jsme navrhli nové okno Visual Studio start](https://devblogs.microsoft.com/visualstudio/get-to-code-how-we-designed-the-new-visual-studio-start-window/) blogový příspěvek.

### <a name="live-share"></a>Live Share

[Visual Studio Live Share](https://visualstudio.microsoft.com/services/live-share/) je služba pro vývojáře, která umožňuje sdílet základ kódu a jeho kontextu s programujete a získat rychlé obousměrné spolupráci přímo z Visual Studia. S Live Share programujete můžete přečíst, přejděte, upravit a ladit projekt, který jste sdíleli s nimi a učinit snadno a bezpečně.

A s Visual Studio 2019, tato služba nainstaluje ve výchozím nastavení.

![Animace, který zobrazuje spolupráci funkce Live Share v aplikaci Visual Studio 2019](media/vs-2019/live-share.gif)

Další informace najdete v tématu [Visual Studio Live Share pro revize kódu v reálném čase a interaktivní vzdělávání](https://devblogs.microsoft.com/visualstudio/visual-studio-live-share-for-real-time-code-reviews-and-interactive-education/) příspěvek na blogu a [teď součástí Visual Studio 2019 Live Share](https://devblogs.microsoft.com/visualstudio/live-share-now-included-with-visual-studio-2019/) blogový příspěvek.

### <a name="integrated-code-reviews"></a>Revize kódu integrované

Zavádíme nové rozšíření, které si můžete stáhnout pomocí Visual Studio 2019. Toto nové rozšíření můžete zkontrolovat, spuštění a dokonce i ladění žádosti o přijetí změn od týmu bez opuštění sady Visual Studio. Podporujeme kódu v úložištích GitHub a Azure DevOps.

   ![Snímek obrazovky okna Nový start v aplikaci Visual Studio 2019](media/vs-2019/pr-experience.png)

Další informace najdete v tématu [revize kódu pomocí rozšíření pro Visual Studio žádosti o přijetí změn](https://devblogs.microsoft.com/visualstudio/code-reviews-using-the-visual-studio-pull-requests-extension/) blogový příspěvek.

## <a name="debug"></a>Ladění

Zobrazte na následující video a další informace o tom, jak můžete nula pomocí přesné cílení během ladění. <br><br>*Délka videa: 3.54 minut*

> [!VIDEO https://www.youtube.com/embed/hr72Fs8n_9c]

### <a name="performance-gains"></a>Zvýšení výkonu

Jsme provést jednou výhradně C++ datové zarážky a přizpůsobit je pro aplikace .NET Core.

   ![Animace, který zobrazuje ladění ve Visual Studio 2019 datové zarážky](media/vs-2019/debug-data-breakpoints.gif)

Tak, jestli jste už kódování v C++ nebo .NET Core, datové zarážky může být dobrou alternativou jenom uvedení pravidelné zarážky. Datové zarážky jsou taky ideální pro scénáře, jako je hledání pozměňuje globálního objektu nebo jsou přidány nebo odebrány ze seznamu.

A pokud jste vývojář C++, který vyvíjí velké aplikace, Visual Studio 2019 provedl symboly mimo proces, který umožňuje ladit tyto aplikace bez majícího problémy související s pamětí.

### <a name="search-while-debugging"></a>Hledat při ladění

Pravděpodobně jste došlo před, hledání v okně kukátko pro řetězec ze sady hodnot. V aplikaci Visual Studio 2019 jsme přidali vyhledávání v oknech sledovat, místní hodnoty a automatické hodnoty a umožňují najít objekty a hodnoty, které hledáte.

   ![Animace, která zobrazuje okno hledání ladění ve Visual Studio 2019](media/vs-2019/debug-window-search.gif)

Můžete také formátovat, jak se zobrazí hodnota v oknech sledovat, místní hodnoty a automatické hodnoty.  Dvakrát klikněte na jednu z položek v některém z windows a přidejte čárku (",") pro přístup k seznamu rozevírací seznam specifikátorů formátu je to možné, z nichž každý obsahuje popis jeho zamýšlený efekt.

   ![Nové kukátko okno Formát hodnoty funkci a ve Visual Studio 2019](media/search-watch-window.png)

Další informace najdete v tématu [zdokonaleno ve Visual Studio 2019: Hledání objektů a vlastností v okně kukátka, automatické hodnoty a místní hodnoty Windows](https://devblogs.microsoft.com/visualstudio/enhanced-in-visual-studio-2019-search-for-objects-and-properties-in-the-watch-autos-and-locals-windows/) blogový příspěvek.

### <a name="snapshot-debugger"></a>Snapshot Debugger

Získáte snímek provádění své aplikace v cloudu a podívat se, co se přesně děje. (Tato funkce je dostupná v sadě Visual Studio Enterprise, pouze.)

   ![Animace, který zobrazuje ladicího programu snímků v sadě Visual Studio. 2019 Enterprise](media/vs-2019/snapshot-debugger.gif)

Přidali jsme podporu pro cílení na aplikace ASP.NET (instalace jádra a desktop), běžící ve Virtuálním počítači Azure. A přidali jsme podporu pro aplikace, které běží ve službě Azure Kubernetes Service. Snapshot Debugger můžete výrazně zkrátit čas potřebný k vyřešení problémů, ke kterým dochází v produkčním prostředí.

Další informace najdete v tématu [ladit živé aplikace ASP.NET Azure pomocí ladicího programu snímků](../debugger/debug-live-azure-applications.md) stránky a [Představujeme doba trvání cesty ladění pro Visual Studio Enterprise 2019](https://devblogs.microsoft.com/visualstudio/introducing-time-travel-debugging-for-visual-studio-enterprise-2019/) blogový příspěvek.

## <a name="whats-next"></a>Co se chystá

Díky novým funkcím, které můžete provádět vývoj ještě lepší prostředí často aktualizujeme Visual Studio 2019. Další informace o našich nejnovějších inovacích, podívejte se [blogu Visual Studio](https://devblogs.microsoft.com/visualstudio/). A pro záznam co jsme vydali ve verzi preview na datum, podívejte se na [poznámky k verzi Preview](/visualstudio/releases/2019/release-notes-preview/).

Chcete vědět více o tom, co jiného se připravuje pro Visual Studio 2019? Zobrazit [Visual Studio Roadmap](/visualstudio/productinfo/vs-roadmap/).

## <a name="give-us-feedback"></a>Sdělte nám svůj názor

Proč odeslat zpětnou vazbu týmu sady Visual Studio? Protože jsme vážně trvat zpětné vazby od zákazníků. To vede velkou část co děláme.

* Pokud chcete provést návrh o tom, jak můžeme vylepšit sady Visual Studio, můžete to provést pomocí [navrhnout funkci](suggest-a-feature.md) nástroj.

* Pokud dochází k zablokování, při selhání nebo jiné problémy s výkonem, můžete jednoduše sdílet kroky pro reprodukci a podpůrné soubory s námi pomocí [nahlásit problém](how-to-report-a-problem-with-visual-studio.md) nástroj.

## <a name="see-also"></a>Viz také:

* [Announcing Visual Studio 2019](https://devblogs.microsoft.com/visualstudio/visual-studio-2019-code-faster-work-smarter-create-the-future/)
* [Zpráva k vydání verze Visual Studio 2019](/visualstudio/releases/2019/release-notes/)
* [Co je nového ve Visual Studio SDK. 2019](../extensibility/whats-new-visual-studio-2019-sdk.md)
* [2019 Visual Studio for Mac je nyní k dispozici](https://devblogs.microsoft.com/visualstudio/visual-studio-2019-for-mac-is-now-available/)
* [Konference Microsoft Build 2019](https://www.microsoft.com/build)
* [Microsoft Connect(); 2018 conference](https://www.microsoft.com/connectevent)
