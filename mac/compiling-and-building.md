---
title: Kompilaci a sestavování
description: Tento článek popisuje, jak pro zkompilování a vybuildování projekty a řešení v sadě Visual Studio pro Mac
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: FB253757-DB00-4889-A6BF-E44722E25BD1
ms.openlocfilehash: 29c6baaa4da4eae4a2302ec3916a156b59a49272
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2018
ms.locfileid: "34453880"
---
# <a name="compiling-and-building-in-visual-studio-for-mac"></a>Kompilaci a sestavování v sadě Visual Studio pro Mac

Visual Studio pro Mac slouží k vytváření aplikací a vytváření sestavení během vývoje projektu. Je důležité pro zkompilování a vybuildování kódu včas a často, aby mohli identifikovat neshody typu a dalších chyb kompilace.

## <a name="building-from-the-ide"></a>Sestavení v prostředí IDE

Pomocí sady Visual Studio pro Mac umožňuje vytvářet a spustit okamžitě, vytvoří při stále a ovládat funkce sestavení. Visual Studio pro Mac MSBuild používá jako podkladový systém sestavení.

Všechny projekty a řešení vytvořená v prostředí IDE bude mít výchozí konfigurace sestavení, která definuje kontext pro sestavení. Tyto konfigurace se dá upravit nebo vytvořit vlastní. Vytvoření nebo úprava tyto konfigurace se automaticky aktualizuje soubor projektu, který je následně používán MSBuild k sestavení projektu.  

Další informace o tom, jak vytvářet projekty a řešení v integrovaném vývojovém prostředí najdete v tématu [sestavování a čištění projektů a řešení](building-and-cleaning-projects-and-solutions.md) průvodce.

Visual Studio pro Mac lze také provést následující akce:

* Změňte výstupní cesta. To je upravit v možnostech vašeho projektu:

    ![Změna výstupní cesta](media/compiling-and-building-image4.png)

* Změna podrobností výstupu sestavení:

    ![Změna sestavení podrobností](media/compiling-and-building-image5.png)

* Přidáte vlastní příkazy před, během nebo po vytvoření nebo čištění:

    ![Přidat vlastní příkazy](media/compiling-and-building-image6.png)

## <a name="building-from-command-line"></a>Sestavování z příkazového řádku

Můžete vytvářet aplikace pomocí příkazového řádku nástroje MSBuild Build Engine.

Najdete v článku [MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild) obsahu pro další informace o použití nástroje MSBuild.

## <a name="building-from-visual-studio-team-services"></a>Sestavování z Visual Studio Team Services

* [Sestavení vaší aplikace Xamarin](https://www.visualstudio.com/docs/build/apps/mobile/xamarin)
* [Průběžnou integraci s funkcí Xamarin](https://developer.xamarin.com/guides/cross-platform/ci/)