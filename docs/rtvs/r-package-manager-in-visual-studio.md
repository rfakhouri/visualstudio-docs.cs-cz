---
title: Správce balíčků pro R
description: Jak používat Správce balíčků R v sadě Visual Studio k instalaci a manager R balíčky.
ms.custom: ''
ms.date: 01/24/2018
ms.technology:
- devlang-r
dev_langs:
- R
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- data-science
ms.openlocfilehash: ab0ddbe4a4e2a5013e0c9b72b6c94e5aaf555564
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="package-manager"></a>Správce balíčků

R nástrojů pro Visual Studio (RTVS) Správce balíčků je uživatelského rozhraní pro správu balíčků R. Otevřete ho vyberte **R nástroje > Windows > balíčky** nebo stiskněte kombinaci kláves Ctrl + 7.

Správce balíčků má tři karty. Každý karta zobrazuje seznam relevantní balíčků na levé straně a konkrétní podrobnosti pro vybraný balíček na pravé straně, včetně verze balíčku, popisu, licence, nainstalujte umístění a odkazy na další důležité informace. Do vyhledávacího pole v pravém horním rohu umožňuje filtrovat seznam.

> [!Tip]
> Do pole hledání termín zůstává v platnosti se při přepínání mezi kartami.

- **K dispozici** umožňuje procházet balíčky pro instalaci. Pokud balíček je již nainstalován, **nainstalovat** tlačítko na pravé straně se změní na **odinstalovat**.

    ![Karta dostupné balíčky v nástrojích R pro správce balíčků sady Visual Studio](media/package-manager-available.png)

- **Nainstalovat** zobrazuje všechny nainstalované a načíst balíčky. Zelená tečka vedle balíček označuje, že je načten do relace R. Na červené X ikonu v levé seznamu nebo **odinstalovat** tlačítko na pravé straně lze použít k odinstalaci balíčku. Pokud je k dispozici novější verze nainstalovaných balíčku, modrá šipka vpravo balíčku nahoru provede aktualizace.

    ![Karta balíčky nainstalované v R nástrojů pro Visual Studio Správce balíčků](media/package-manager-installed.png)

- **Načíst** zobrazí pouze balíčky, které jsou načteny do relace R všechny z nich se zobrazí zelená tečkou. Také můžete odinstalovat a aktualizovat balíčky sem.

    ![Načíst balíčky na kartě R nástrojů pro Visual Studio Správce balíčků](media/package-manager-loaded.png)

## <a name="package-locations"></a>Umístění balíčku

Balíčky jsou nainstalovány v následujících umístěních:

- Základní balíčky, které jsou součástí RTVS jsou nainstalovány v `C:\Program Files\Microsoft\R Client\R_SERVER\library`
- Další balíčky instalují `%userprofile%\Documents\R\win-library\3.3`
