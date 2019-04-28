---
title: Visual Studio for Mac Tour
description: Visual Studio for Mac obsahuje integrované vývojové prostředí pro vytváření aplikací .NET v systému macOS, včetně webů ASP.NET Core a projekty Xamarin pro iOS, Android, Mac a Xamarin.Forms.
author: conceptdev
ms.author: crdun
ms.date: 04/02/2019
ms.assetid: 7DC64A52-AA41-4F3A-A8A1-8A20BCD81CC7
ms.custom: video
ms.openlocfilehash: a621faece8ed0cef3dd48d46fc41857af6e62c9e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62983810"
---
# <a name="visual-studio-2019-for-mac-tour"></a>Visual Studio 2019 for Mac tour

Visual Studio for Mac je .NET _integrovaného vývojového prostředí_ na počítači Mac, který je možné upravit, ladit a vytvářet kód a pak publikujete aplikaci. Kromě očekávané funkce, jako je standardní editor a ladicí program Visual Studio for Mac obsahuje kompilátory, nástroje dokončování kódu, grafičtí návrháři pro a správy zdrojového kódu do úložiště ese proces vývoje softwaru.

Visual Studio for Mac podporuje mnoho stejné typy souborů jako jeho protějšek Windows, například `.csproj`, `.fsproj`, nebo `.sln` soubory a podporuje funkce, jako je například EditorConfig, což znamená, že můžete použít rozhraní IDE, který vám bude nejlépe vyhovovat.
Vytvoření, otevření nebo vyvíjet aplikace bude známým všem uživatelům, kteří dříve používali Visual Studio na Windows. Kromě toho Visual Studio for Mac využívá mnoho výkonných nástrojů, které usnadňují jeho protějšek Windows výkonné IDE. Platforma kompilátor Roslyn se používá pro refaktoring a technologii IntelliSense. Jeho modul systému a sestavení projektu pomocí nástroje MSBuild a jeho Editor zdrojového kódu podporuje sady TextMate. Používá stejný ladicím modulem pro aplikace Xamarin a .NET Core a stejného návrháře pro Xamarin.iOS a Xamarin.Android.

## <a name="what-can-i-do-in-visual-studio-for-mac"></a>Co můžu dělat v sadě Visual Studio for Mac

Visual Studio for Mac podporuje následující typy vývoje pro:

- Webové aplikace ASP.NET Core s C#, F#a podpora pro stránky Razor, JavaScript a TypeScript
- Konzolové aplikace .NET core s C# neboF#
- Hry Unity pro různé platformy a aplikace sC#
- Aplikace pro Android, iOS, tvOS a watchOS v Xamarinu s C# nebo F# a XAML
- Desktopové aplikace cocoa v C# neboF#

Tento článek se věnuje různých oddílů sady Visual Studio pro Mac, poskytuje pohled na některé z funkcí, které usnadňují výkonný nástroj pro vytváření těchto aplikací.

## <a name="ide-tour"></a>Prohlídka integrovaného vývojového prostředí

Visual Studio for Mac je uspořádaný do několika oddílů pro správu souborů aplikace a nastavení, vytvoření kódu aplikace a ladění.

## <a name="start-window"></a>Časový interval pro spuštění

Při spuštění. 2019 Visual Studio pro Mac nové uživatelům se zobrazí okno přihlášení. Přihlaste se pomocí svého účtu Microsoft k aktivaci placenou licenci (pokud nějakou máte) nebo odkaz na předplatná Azure. Stisknutím klávesy **přeskočit** a později přihlásit přes **sady Visual Studio > přihlaste** položky nabídky:

![Přihlaste se ke svému účtu Microsoft](media/ide-tour-2019-start-signin.png)

Přihlášených uživatelů se zobrazí nové _časový interval pro spuštění_, která zobrazuje seznam posledních projektů a tlačítka Otevřít existující projekt nebo vytvořte novou:

![Výběr z nedávných projektů, nebo vytvořit něco nového](media/ide-tour-2019-start-projects.png)

## <a name="solutions-and-projects"></a>Řešení a projekty

Následující obrázek ukazuje Visual Studio for Mac pomocí aplikace načíst:

![Načtení sady Visual Studio pro Mac s aplikací](media/ide-tour-image17.png)

Následující části obsahují základní informace o hlavních oblastech v sadě Visual Studio pro Mac.

## <a name="solution-pad"></a>Oblasti řešení

Oblasti řešení Uspořádá projekty v řešení:

![Projekty, které jsou uspořádány v oblasti řešení](media/ide-tour-image18.png)

Je to, kde soubory pro zdrojový kód, prostředky, uživatelské rozhraní a závislosti jsou uspořádány do projektů specifické pro platformu.

Další informace o použití projekty a řešení v sadě Visual Studio pro Mac, najdete v článku [projekty a řešení](/visualstudio/mac/projects-and-solutions) článku.

## <a name="assembly-references"></a>Odkazy na sestavení

Odkazy na sestavení pro každý projekt jsou k dispozici ve složce odkazy:

![Složka s odkazy v oblasti řešení](media/ide-tour-image19.png)

Další odkazy jsou přidána pomocí **upravit odkazy** dialogové okno, které se zobrazí na něj poklikejte na složku odkazy nebo tak, že vyberete **upravit odkazy** na jeho místní nabídky akce:

![Odkazy na dialogové okno Upravit](media/ide-tour-image20.png)

Další informace o používání odkazů v sadě Visual Studio pro Mac, najdete v článku [Správa odkazů v projektu](/visualstudio/mac/managing-references-in-a-project) článku.

## <a name="dependencies--packages"></a>Závislosti / balíčky

Všechny externí závislosti používaných v aplikaci jsou uloženy ve složce závislosti nebo balíčky, v závislosti na tom, jestli jste v.Net Core nebo Xamarin.iOS/Xamarin.Android projektu. Ty se obvykle poskytují ve formě NuGet.

Správce balíčků NuGet je nejoblíbenější Správce balíčků pro vývoj na platformě .NET. Díky podpoře NuGet sady Visual Studio můžete snadno vyhledat a přidat balíčky do vašeho projektu do aplikace.

Chcete-li přidat závislost pro vaši aplikaci, klikněte pravým tlačítkem na závislosti / balíčky a pak zvolte položku **přidat balíčky**:

![Přidání balíčku NuGet](media/ide-tour-image21.png)

Informace o použití balíčku NuGet v aplikaci najdete v [projektu včetně NuGet ve vašem projektu](/visualstudio/mac/nuget-walkthrough) článku.

## <a name="refactoring"></a>Refaktoring

Visual Studio for Mac obsahuje dva užitečné způsoby, jak kód Refaktorovat: Kontext akce a zdrojová analýza. Další informace o nich v [refaktoringu](/visualstudio/mac/refactoring) článku.

## <a name="debugging"></a>Ladění

Visual Studio for Mac obsahuje nativní ladicí program umožňuje ladění podporu pro aplikace Xamarin.Android, Xamarin.iOS a Xamarin.Mac. Visual Studio pro Mac používá Mono Obnovitelně ladicí program, který je implementován do modulu Mono runtime, umožňuje rozhraní IDE k ladění spravovaného kódu na všech platformách. Další informace o ladění, najdete [ladění](/visualstudio/mac/debugging) článku.

Ladicí program obsahuje bohatou vizualizéry pro speciální typy, jako jsou řetězce, barvy, adresy URL, jakož i velikostí, souřadnice a Bézierovy křivky.

Další informace o datové vizualizace ladicího programu, najdete [vizualizace dat](/visualstudio/mac/data-visualizations) článku.

## <a name="version-control"></a>Správa verzí

Visual Studio pro Mac se integruje s systémy správy zdrojového kódu Git a Subversion. Projekty v rámci správy zdrojového kódu, jsou označeny větev uvedená vedle názvu řešení:

![Název větve k označení projekt pod správou zdrojových kódů](media/ide-tour-image22.png)

Soubory s nepotvrzené změny mít anotaci na jejich ikonami v podokně řešení, jak je znázorněno na následujícím obrázku:

![Nepotvrzené soubory v oblasti řešení](media/ide-tour-image23.png)

Další informace o používání správy verzí v sadě Visual Studio, najdete v článku [verzí](/visualstudio/mac/version-control) článku.

## <a name="next-steps"></a>Další kroky

- [Instalace sady Visual Studio pro Mac](installation.md)
- [Zkontrolujte dostupné úlohy](/visualstudio/mac/workloads/)

## <a name="related-video"></a>Související videa

> [!Video https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Visual-Studio-for-Mac-Overview/player]

## <a name="see-also"></a>Viz také:

- [Visual Studio IDE (on Windows)](/visualstudio/ide/visual-studio-ide)
