---
title: Projekty a řešení
description: Tento dokument obsahuje přehled projekty a řešení v sadě Visual Studio pro Mac.
author: conceptdev
ms.author: crdun
ms.date: 05/23/2019
ms.assetid: 8254505D-D96E-48BD-8A5E-CF6A917897EA
ms.openlocfilehash: ec62e9c0b449f5f2aed568735c2a10d1f6634eed
ms.sourcegitcommit: 51dad3e11d7580567673e0d426ab3b0a17584319
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/10/2019
ms.locfileid: "66820956"
---
# <a name="projects-and-solutions-in-visual-studio-for-mac"></a>Projekty a řešení v sadě Visual Studio pro Mac

Tento článek obsahuje přehled *projektu* a *řešení* konceptů v sadě Visual Studio pro Mac.

> [!NOTE] 
> Toto téma se vztahuje k sadě Visual Studio pro Mac. Visual Studio na Windows, naleznete v tématu [projekty a řešení v sadě Visual Studio](/visualstudio/ide/solutions-and-projects-in-visual-studio).

## <a name="projects"></a>Projekty

Při vytváření nové aplikace, webu, atd. v sadě Visual Studio pro Mac, můžete začít s projektem. Projekt obsahuje všechny soubory potřebné (zdrojového kódu, obrázky, datových souborů atd.), které jsou potřebné ke kompilaci webu, knihovna nebo spustitelný soubor.

Projekt je definován souborem (například `.csproj` pro C# projekty) obsahující kód xml, který definuje soubor a hierarchii složek, cesty k souborům a nastavení specifická pro projekt, například nastavení sestavení.

Při načítání projektu ve Visual Studio pro Mac oblasti řešení soubor projektu používá k zobrazení souborů a složek ve vašem projektu. Během kompilace MSBuild načte nastavení ze souboru projektu k vytvoření spustitelného souboru.

## <a name="solutions"></a>Řešení

A *řešení* je kontejner se seskupením dohromady jeden nebo více souvisejících projektů. Řešení jsou popsány pomocí textového souboru (rozšíření `.sln`) s svůj vlastní jedinečný formát; není určen upravit ručně.

## <a name="managing-projects-in-the-solution-pad"></a>Správa projektů v oblasti řešení

Po projekt byl vytvořen nebo načíst, můžete k zobrazení a správě projektu nebo řešení a soubory obsažené v oblasti řešení. Následující obrázek znázorňuje řešení panel s řešení .NET Core, který obsahuje dva projekty:

![Ukázkové řešení s více projekty](media/solution-example.png)

Vlastnosti projekty a řešení můžete spravovat buď poklikáním na název projektu nebo řešení, nebo kliknutím pravým tlačítkem a vyberete **možnosti**.

Další informace o těchto možnostech najdete v [vlastnosti projektu a řešení pro správu](managing-solutions-and-project-properties.md) článku.

## <a name="see-also"></a>Viz také:

- [Řešení a projekty v sadě Visual Studio (Windows)](/visualstudio/ide/solutions-and-projects-in-visual-studio)
