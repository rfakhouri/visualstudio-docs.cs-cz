---
title: Novinky v sadě Visual Studio 2019
titleSuffix: ''
description: Další informace o nových funkcích sady Visual Studio 2019.
ms.date: 04/03/2019
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
ms.openlocfilehash: b38f75f1172e96e3dc2576a199949fdbb0c32f68
ms.sourcegitcommit: 40393347a36779230d128f2355a911632a8d458e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/02/2019
ms.locfileid: "58866741"
---
# <a name="whats-new-in-visual-studio-2019"></a>Novinky v sadě Visual Studio 2019

**Aktualizováno pro [16,0 vydání](/visualstudio/releases/2019/release-notes/)**

>[!div class="button"]
>[Stáhněte si Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)

Visual Studio 2019 získáte ve své třídě nejlepší nástroje a služby pro všechny vývojáře, aplikace a jakoukoli platformu. Ať už používáte Visual Studio poprvé nebo jste dosud používali ho let, není v této nové verzi, jako je mnoho dalších!

Tady je podrobný rekapitulace toho, co je nového:

* **[Vývoj](#develop)**: Udržte si zaměření a produktivity pomocí Vylepšený výkon, rychlé kód čištění a lepší výsledky hledání.
* **[Spolupráce](#collaborate)**: Využijte přirozené spolupráci prostřednictvím cloudového pracovního postupu, v reálném čase, úpravy a ladění, a revize kódu přímo v sadě Visual Studio.
* **[Ladění](#debug)**: Zvýrazněte a přejděte na konkrétní hodnoty, optimalizovat využití paměti a provést automatické snímky spuštění vaší aplikace.

Úplný seznam všech, který je v této verzi nové, najdete v článku [poznámky k verzi](/visualstudio/releases/2019/release-notes/). 

## <a name="develop"></a>Vývoj

Ušetřete čas s novými funkcemi.
<br><br>
> [!VIDEO https://www.youtube.com/embed/n5sJ4EewKGk]

### <a name="improved-search"></a>Vylepšené vyhledávání

Dříve označované jako Snadné spuštění, naše nové rozhraní pro hledání je rychlejší a efektivnější. Nyní výsledky hledání zobrazeny dynamicky během psaní. A výsledky hledání můžete často obsahují klávesové zkratky pro příkazy, takže můžete snadno pamatovat pro budoucí použití.

   ![Animaci, která nové rozhraní pro hledání v aplikaci Visual Studio 2019](media/vs-2019/new-search-feature.gif)

Nové vyhledávání přibližných shod logiky najdete všechno, co potřebujete, bez ohledu na to, překlepy. Takže ať už hledáte příkazů a nastavení nebo další užitečné věci, nová funkce vyhledávání je snazší najít, co hledáte.

### <a name="refactorings"></a>Refaktoring

Nové C# refaktoringy usnadňují uspořádání vašeho kódu. Jednoduše vyvolat refaktoringy stisknutím kombinace kláves **Ctrl +.** a vyberte akci, kterou chcete převést. 

   ![Animace prostředí refaktoringy Visual Studio 2019](media/vs-2019/refactorings.gif)

Přidali jsme mnoho nových refaktoringů, včetně ten, který umožňuje zabalit parametrů metody.

### <a name="intellicode"></a>IntelliCode

[Visual Studio IntelliCode](/visualstudio/intellicode/) je rozšíření, která vylepšuje své úsilí vývoje softwaru pomocí umělé inteligence (AI). IntelliCode železniční napříč 2 000 open-source projektů na Githubu&mdash;každý s více než 100 hvězdiček&mdash;ke generování doporučení.

 ![Animace IntelliCode v Visual Studio 2019](media/vs-2019/IntelliCode.gif)

Tady je několik způsobů, jak Visual Studio IntelliCode může pomoct zvýšit produktivitu práce:

* Doručování dokončování s ohledem na kontext kódu
* Příručka pro vývojáře dodržovat vzory a styly jejich tým
* Najít problémy s kódu obtížné catch
* Revize kódu fokus kreslením upozornit na oblasti, které jsou opravdu důležité.

Zpočátku podporujeme pouze C# když jsme první předběžně IntelliCode rozšíření pro Visual Studio. Nyní přidali jsme podporu pro C++ a XAML v sadě Visual Studio, příliš.

A pokud používáte C#, přidali jsme také možnost pro trénování modelu vlastní na váš vlastní kód.

Další informace o IntelliCode, najdete v článku [více kódu, posuňte se menší s Visual Studio IntelliCode](https://devblogs.microsoft.com/visualstudio/code-more-scroll-less-with-visual-studio-intellicode/) blogový příspěvek. 

### <a name="code-cleanup"></a>Kód čištění

Spárovat s nový indikátor stavu dokumentu je nový příkaz vyčištění kódu. Tento nový příkaz slouží k identifikaci a potom opravit upozornění a návrhy kliknutím na tlačítko.

Čištění formátovat kód, který se použije všechny opravy kódu jak navrhovaly [aktuální nastavení](code-styles-and-quick-actions.md), [soubory .editorconfig](create-portable-custom-editor-options.md), nebo [analyzátory Roslyn](../code-quality/roslyn-analyzers-overview.md).

   ![Snímek obrazovky nového ovládacího prvku vyčištění kódu v aplikaci Visual Studio 2019](media/vs-2019/code-cleanup-profile.png)

Kolekce fixers můžete také uložit jako profil. Například pokud máte malou sadu cílových fixers, které můžete použít při kódu můžete často, a pak máte jiné komplexní sadu fixers použít před přezkoumání kódu, můžete nakonfigurovat profily k vyřešení těchto různých úloh.

   ![Snímek obrazovky nového ovládacího prvku vyčištění kódu v aplikaci Visual Studio 2019](media/vs-2019/code-cleanup-profile-configure.png)

## <a name="collaborate"></a>Spolupráce

Týmové vyřešit nějaký problém.
<br><br>
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

Abyste mohli hned začít, stáhněte si [žádosti o přijetí změn pro sadu Visual Studio](https://aka.ms/pr4vs) rozšíření z Visual Studio Marketplace.

## <a name="debug"></a>Ladit

Nula pomocí cílení na přesné.
<br><br>
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

Další informace najdete v tématu [ladit živé aplikace ASP.NET Azure pomocí ladicího programu snímků](../debugger/debug-live-azure-applications.md) stránky.

## <a name="give-us-feedback"></a>Sdělte nám svůj názor

Proč odeslat zpětnou vazbu týmu sady Visual Studio? Protože jsme vážně trvat zpětné vazby od zákazníků. To vede velkou část co děláme.

* Pokud chcete provést návrh o tom, jak můžeme vylepšit sady Visual Studio, můžete to provést pomocí [poslat návrh](talk-to-us.md#i-want-to-make-a-suggestion-about-visual-studio-features) nástroj.

* Pokud dochází k zablokování, při selhání nebo jiné problémy s výkonem, můžete jednoduše sdílet kroky pro reprodukci a podpůrné soubory s námi pomocí [nahlásit problém](talk-to-us.md#i-want-to-report-a-problem-with-visual-studio) nástroj.

## <a name="see-also"></a>Viz také:

* [Announcing Visual Studio 2019](https://devblogs.microsoft.com/visualstudio/visual-studio-2019-code-faster-work-smarter-create-the-future/)
* [Zpráva k vydání verze Visual Studio 2019](/visualstudio/releases/2019/release-notes/)
* [Co je nového ve Visual Studio SDK. 2019](../extensibility/whats-new-visual-studio-2019-sdk.md)
* [2019 Visual Studio for Mac je nyní k dispozici](https://devblogs.microsoft.com/visualstudio/visual-studio-2019-for-mac-is-now-available/)
* [Microsoft Connect(); 2018 conference](https://www.microsoft.com/connectevent)
