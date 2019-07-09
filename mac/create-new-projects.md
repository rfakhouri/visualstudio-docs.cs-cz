---
title: Vytváří se nové projekty a řešení
description: Tento článek popisuje, jak vytvořit projekty a řešení v sadě Visual Studio pro Mac
author: heiligerdankgesang
ms.author: dominicn
ms.date: 05/23/2019
ms.assetid: 5880BB10-0A12-47E2-8A82-7A2D59C4D579
ms.openlocfilehash: dbfc0d951524bb9ffbbd4a2366679cfc6ae41925
ms.sourcegitcommit: 7fbfb2a1d43ce72545096c635df2b04496b0be71
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/09/2019
ms.locfileid: "67693054"
---
# <a name="creating-a-new-project"></a>Vytvoření nového projektu

## <a name="opening-the-project-creation-dialog"></a>Otevřete dialogové okno Vytvoření projektu

Existuje několik způsobů, jak vytvořit nový projekt v sadě Visual Studio pro Mac. Při prvním otevření sady Visual Studio pro Mac, zobrazí se na úvodní obrazovce. Odsud můžete **nový** což vás přesměruje na obrazovku pro vytvoření projektu.

> [!TIP]
> Kromě toho z úvodní obrazovky, můžete také otevřít a vyhledejte poslední projekty a řešení. Posledních projektů můžete otevřít také tak, že přejdete na řádku nabídek a zvolíte **soubor > poslední řešení**

![Úvodní obrazovka s vytvořením nového projektu](media/first-run-project.png)

Pokud Visual Studio for Mac je už otevřená řešení načtení, můžete vytvořit nové řešení tak, že přejdete na řádku nabídek a zvolíte **soubor > Nový řešení**. Vytvoření nového řešení tímto způsobem se zavřít řešení, které je již načtena.

## <a name="creating-a-new-project-from-a-template"></a>Vytvoření nového projektu ze šablony

**Nový projekt** dialogové okno, ve výchozím nastavení, zobrazí vaše naposledy použité šablony, seřazené podle *naposledy použitých*.

Pokud nechcete použít poslední šablonu, můžete z kategorií nalevo od dialogového okna. Každá kategorie obsahuje několik šablon projektů si můžete vybírat. Kliknutím na typu projektu umožňuje zobrazit popis na pravé straně obrazovky.

![Nová obrazovka projektu](media/project-creation-screen.png)

## <a name="configuring-your-new-project"></a>Konfigurace nového projektu

Když vyberete šablonu projektu na následující obrazovce vás provede všech kroků konfigurace požadovaných nastavení projektu. To se může lišit podle typu projektu.

Všechny projekty vyžadují nový projekt, spolu s umístění pro uložení souborů. Pokud je projekt součástí nové řešení, místo jeho přidání k existujícím řešení, název řešení bude také vyžadovat.

V této fázi můžete volitelně můžete také nakonfigurovat možností správy zdrojového kódu Git. Na následujícím obrázku je příklad posledním krokem konfigurace pro projekt .NET Core:

![Konfigurace nového projektu](media/configure-new-project.png)

## <a name="adding-additional-projects-to-a-solution"></a>Přidání další projekty do řešení

Můžete přidat další projekty do řešení pravým tlačítkem na řešení v oblasti řešení a zvolením buď **Přidat > Přidat nový projekt** nebo **Přidat > Přidat existující projekt**.

Přidáním nového projektu se dostanete pomocí vytvoření projektu, jak je znázorněno v [konfigurace váš nový projekt](#configuring-your-new-project).

Zvolíte-li přidat existující projekt vám umožní vyhledat existující projekt na vašem počítači a přidat do řešení.

## <a name="see-also"></a>Viz také:

- [Vytvářet řešení a projekty (Visual Studio na Windows)](/visualstudio/ide/creating-solutions-and-projects)