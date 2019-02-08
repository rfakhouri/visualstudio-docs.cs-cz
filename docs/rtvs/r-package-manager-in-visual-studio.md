---
title: Správce balíčků pro R
description: Jak používat Správce balíčků R ve Visual Studiu k instalaci a správce R balíčky.
ms.date: 01/24/2018
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: jillfra
ms.workload:
- data-science
ms.openlocfilehash: d35bfd45e862912ff78ae600eed01ce8dc002493
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55931582"
---
# <a name="package-manager"></a>Správce balíčků

Nástroje R pro Visual Studio (RTVS) Správce balíčků je uživatelské rozhraní pro správu balíčků R. Pokud chcete soubor otevřít, vyberte **nástroje R** > **Windows** > **balíčky** nebo stiskněte **Ctrl** + **7**.

Správce balíčku obsahuje tři karty. Každá karta zobrazuje seznam relevantních balíčků na levé straně a konkrétní podrobnosti pro vybraný balíček na pravé straně, včetně verze balíčku, popisu, licence, nainstalujte umístění a odkazy na další relevantní informace. Pole Hledat v pravém horním rohu umožňuje filtrovat seznam.

> [!Tip]
> Výraz v poli vyhledat zůstává v platnosti při přepínání mezi kartami.

- **K dispozici** umožňuje procházet balíčky pro instalaci. Pokud je již nainstalován balíček, **nainstalovat** tlačítko na pravé straně se změní na **odinstalovat**.

    ![Karta dostupné balíčky v nástroje jazyka R pro správce balíčků sady Visual Studio](media/package-manager-available.png)

- **Nainstalované** uvádí všechny nainstalované a načtení balíčků. Zelenou tečku vedle balíčku znamená, že je načtena do relace jazyka R. Na červené X ikony v levém seznamu nebo **odinstalovat** tlačítko na pravé straně lze použít k odinstalaci balíčku. Pokud je k dispozici novější verzi nainstalovaného balíčku, provádí modrý nahoru šipka vpravo od balíček aktualizace.

    ![Nainstalované balíčky kartu v nástroje jazyka R pro správce balíčků sady Visual Studio](media/package-manager-installed.png)

- **Načíst** zobrazí pouze balíčky, které se načtou do relace jazyka R, které se zobrazí s zelenou tečku. Můžete rovněž odinstalovat a aktualizace balíčků tady.

    ![Načíst kartu balíčky v nástroje jazyka R pro správce balíčků sady Visual Studio](media/package-manager-loaded.png)

## <a name="package-locations"></a>Umístění balíčku

Balíčky jsou nainstalovány v následujících umístěních:

- Základní balíčky, které jsou součástí RTVS jsou nainstalovány v *C:\Program Files\Microsoft\R Client\R_SERVER\library*
- Další balíčky se nainstalují do *%userprofile%\Documents\R\win-library\3.3*
