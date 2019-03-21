---
title: Výběr umístění instalací
description: Zjistěte, jak snížit nároky na instalaci sady Visual Studio na systémovou jednotku tak, že změníte umístění mezipaměti pro stahování, sdílených komponent, sady SDK a nástroje na jiné jednotky.
ms.date: 11/07/2018
ms.custom: seodec18
ms.topic: conceptual
helpviewer_keywords:
- change installation locations for Visual Studio
- select an installation location for Visual Studio files
- move installation files to different drives
- use the D drive
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 842fed287a6035684534c3d735d146e1b9a0fbfb
ms.sourcegitcommit: 3d37c2460584f6c61769be70ef29c1a67397cf14
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/21/2019
ms.locfileid: "58324971"
---
# <a name="select-the-installation-locations-in-visual-studio"></a>Vybrat umístění instalace v sadě Visual Studio

::: moniker range="vs-2017"

**Novinka ve verzi 15.7**: Můžete snížit nároky na instalaci sady Visual Studio na systémovou jednotku tak, že změníte umístění pro některé z jeho souborů. Konkrétně můžete použít jiné umístění pro mezipaměť pro stahování, sdílených komponent, sady SDK a soubory nástroje.

::: moniker-end

::: moniker range="vs-2019"

Můžete snížit nároky na instalaci sady Visual Studio na systémovou jednotku tak, že změníte umístění pro některé z jeho souborů. Konkrétně můžete použít jiné umístění pro mezipaměť pro stahování, sdílených komponent, sady SDK a soubory nástroje.

::: moniker-end

   > [!NOTE]
   > Existují některé nástroje a sady SDK, které mají různá pravidla, na kterém lze nainstalovat. Tyto nástroje a sady SDK jsou nainstalovány na systémovou jednotku i v případě zvolte jiné umístění.

Jste připravení začít? Tady je způsob.

1. Při instalaci sady Visual Studio, zvolte **umístění instalací** kartu.

   ![Vybrat umístění instalace sady Visual Studio 2017 –](media/vs-installation-locations.png "zvolte umístění instalace.")

1. V **Visual Studio IDE** části, přijměte výchozí nastavení. Visual Studio nainstaluje základním produktu a obsahuje soubory, které jsou specifické pro tuto verzi sady Visual Studio.

   ![Visual Studio IDE část kartě umístění instalací](media/vs-installation-locations-ide.png "přijmete výchozí hodnoty pro oddíl IDE sady Visual Studio na kartě umístění instalace.")

   > [!TIP]
   > Systémová jednotka jednotky SSD (Solid-State Drive), doporučujeme přijmout výchozí umístění na systémovou jednotku. Důvod? Při vývoji v sadě Visual Studio, číst a zapisovat do velké množství souborů, což zvyšuje úroveň vstupně-výstupní aktivitu disku. Doporučujeme zvolit nejrychlejší jednotky pro zpracování zátěže.

1. V **mezipaměť pro stahování** části, rozhodněte, zda chcete zachovat mezipaměť pro stahování a následně se rozhodnete, kam chcete uložit své soubory.

     ![Stáhnout oddíl mezipaměti kartě umístění instalací](media/vs-installation-locations-cache.png "zvolte, jestli se má po instalaci zachovat mezipaměť pro stahování a pak určete taky jednotku, ve které chcete ukládat soubory.")

    1. Zaškrtněte nebo zrušte zaškrtnutí políčka **zachovat mezipaměť pro stahování po instalaci**.

       Pokud nechcete zachovat mezipaměť pro stahování, umístění se používá jenom dočasně. Tato akce nebude mít vliv na a odstraňovat soubory z předchozí instalace.

    1. Určete taky jednotku, kam chcete uložit instalační soubory a manifesty z mezipaměti pro stahování.

        Pokud vyberete úlohy "Vývoj desktopových aplikací pomocí C++", dočasně požadovaná velikost je 1.58 GB na systémovou jednotku, která je uvolněna poté, co nejdříve po dokončení instalace.

       > [!IMPORTANT]
       > Toto umístění se nastaví pomocí při první instalaci a není možné později změnit z uživatelského rozhraní instalačního programu. Místo toho je potřeba [použít parametry příkazového řádku](use-command-line-parameters-to-install-visual-studio.md) přesunout do mezipaměti pro stahování.

1. V **sdílené komponenty, nástroje a sady SDK** části, určete taky jednotku, ve které chcete ukládat soubory, které jsou sdíleny instalace sady Visual Studio vedle sebe. Sady SDK a nástroje jsou také uloženy v tomto adresáři.

   ![Sdílené komponenty, nástroje a sady SDK část kartě umístění instalací](media/vs-installation-locations-shared.png "zadejte umístění, kam chcete uložit sdílené komponenty, nástroje a sady SDK.")

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Instalace sady Visual Studio](install-visual-studio.md)
* [Aktualizace sady Visual Studio](update-visual-studio.md)
* [Úpravy sady Visual Studio](update-visual-studio.md)
* [Odinstalace sady Visual Studio](uninstall-visual-studio.md)
