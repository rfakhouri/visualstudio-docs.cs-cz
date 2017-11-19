---
title: "Kompilaci a sestavování v sadě Visual Studio pro Mac | Microsoft Docs"
description: 
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.assetid: FB253757-DB00-4889-A6BF-E44722E25BD1
ms.openlocfilehash: 9005cf64f4b72f39923d6525e78de745d79c3953
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="compiling-and-building-in-visual-studio-for-mac"></a>Kompilaci a sestavování v sadě Visual Studio pro Mac

Visual Studio pro Mac slouží k vytváření aplikací a vytváření sestavení během vývoje projektu. Je důležité pro zkompilování a vybuildování kódu včas a často, aby mohli identifikovat neshody typu a dalších chyb kompilace.

## <a name="choosing-a-build-method"></a>Výběr metody sestavení:

### <a name="using-the-ide"></a>Používání prostředí IDE

Pomocí sady Visual Studio pro Mac umožňuje vytvořit a spustit sestavení okamžitě, přitom stále poskytuje ovládat funkce sestavení. Visual Studio pro Mac MSBuild používá jako podkladový systém sestavení.

Všechny projekty a řešení vytvořená v prostředí IDE bude mít výchozí konfigurace sestavení, která definuje kontext pro sestavení. Tyto konfigurace se dá upravit nebo vytvořit vlastní. Vytvoření nebo úprava tyto konfigurace se automaticky aktualizuje soubor projektu, který je následně používán MSBuild k sestavení projektu.  

Další informace o tom, jak vytvářet projekty a řešení v integrovaném vývojovém prostředí najdete v tématu [sestavování a čištění projektů a řešení](~/building-and-cleaning-projects-and-solutions.md) průvodce.

Visual Studio pro Mac lze také provést následující akce:

* Změňte výstupní cesta. To je upravit v možnostech vašeho projektu:

    ![Změna výstupní cesta](media/compiling-and-building-image4.png)

* Změna podrobností výstupu sestavení:

    ![Změna sestavení podrobností](media/compiling-and-building-image5.png)

* Přidáte vlastní příkazy před, během nebo po vytvoření nebo čištění:

    ![Přidat vlastní příkazy](media/compiling-and-building-image6.png)

### <a name="building-from-command-line"></a>Sestavování z příkazového řádku

Můžete vytvářet aplikace pomocí příkazového řádku nástroje MSBuild Build Engine.

Najdete v článku [MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild) obsahu pro další informace o použití nástroje MSBuild.

### <a name="using-visual-studio-team-services"></a>Pomocí sady Visual Studio Team Services

* [Sestavení vaší aplikace Xamarin](https://www.visualstudio.com/docs/build/apps/mobile/xamarin)
* [Průběžnou integraci s funkcí Xamarin](https://developer.xamarin.com/guides/cross-platform/ci/)