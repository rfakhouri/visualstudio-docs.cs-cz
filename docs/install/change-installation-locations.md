---
title: Změna umístění instalací sady Visual Studio 2017
description: Zjistěte, jak snížit nároky na instalaci na systémovou jednotku tak, že změníte umístění mezipaměti pro stahování, sdílených komponent, sady SDK a nástroje na jiné jednotky.
ms.date: 05/07/2018
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- change installation locations for Visual Studio
- move installation files to different drives
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 87698421c4992d0349e04740c120d491aa54fcc3
ms.sourcegitcommit: 6b092e7d466377f06913d49d183dbbdca16730f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/28/2018
ms.locfileid: "43138963"
---
# <a name="change-the-installation-locations-in-visual-studio-2017"></a>Změna umístění instalací sady Visual Studio 2017

**Nové ve verzi 15.7**: můžete snížit nároky na instalaci na systémovou jednotku přesunutím mezipaměti pro stahování, sdílených komponent, sady SDK a nástroje na jiné jednotky.

Tady je způsob.

1. Při instalaci sady Visual Studio, zvolte **možnosti instalace** kartu.

  ![Změna umístění instalace sady Visual Studio 2017 –](media/installation-options-by-location.png "Změna umístění instalace")

  > [!IMPORTANT]
  > Pokud pozastavení instalace a později ji obnovit, Visual Studio převezme tam, kde skončila. Jinými slovy jeho průběh instalace se vztahuje na co je ponecháno na stažení a instalaci a nespustí se od předchozího počtu.

2. V **Visual Studio IDE** části, přijměte výchozí nastavení. To nainstaluje základním produktu a obsahuje soubory, které jsou specifické pro tuto verzi sady Visual Studio.

 > [!IMPORTANT]
 > Pokud je systémového disku SSD (SOLID-State drive), zde jeho proč doporučujeme přijmout výchozí umístění na systémovou jednotku: při vývoji v sadě Visual Studio, čtení a zápis do velké množství souborů, což zvyšuje úroveň vstupně-výstupní aktivitu disku.  Doporučujeme zvolit nejrychlejší jednotky pro zpracování zátěže.

2. V **mezipaměť pro stahování** části, rozhodněte, zda chcete zachovat mezipaměť pro stahování a poté zaškrtněte nebo zrušte zaškrtnutí políčka **zachovat mezipaměť pro stahování** odpovídajícím způsobem. <br><br>Pokud nechcete zachovat mezipaměť pro stahování, umístění se používá jenom dočasně. Tato akce, nebude mít vliv na a odstraňovat soubory z předchozí instalace. (Chcete-li vyčistit všechny instalační balíčky, je třeba upravit předchozí instalace zvlášť.)

3. V **mezipaměť pro stahování** části, určete taky jednotku, kam chcete uložit instalační soubory a manifesty. <br><br>Pokud vyberete úlohy "Vývoj desktopových aplikací pomocí C++", dočasně požadovaná velikost je 1.58 GB na systémovou jednotku, která je uvolněna poté, co nejdříve po dokončení instalace.

 > [!NOTE]
 > Soubory jsou nejprve stáhne do dočasné složky na systémovou jednotku a byl později smazán po sady Visual Studio ověří a přesune je do složky mezipaměti pro stahování. Pokud se rozhodnete zachovat mezipaměť pro stahování na jinou jednotku, Visual Studio stále potřebuje místo na disku, které se rovná velikosti mezipaměti pro stahování na systémovou jednotku.
 > [!IMPORTANT]
 > Umístění se nastaví pomocí při první instalaci a není možné později změnit z uživatelského rozhraní instalačního programu. Místo toho je potřeba [použít parametry příkazového řádku](use-command-line-parameters-to-install-visual-studio.md) přesunout do mezipaměti pro stahování

4. V **sdílené komponenty, nástroje a sady SDK** části, určete taky jednotku, ve které chcete ukládat soubory, které jsou sdíleny instalace sady Visual Studio vedle sebe. Sady SDK a nástroje, které umožní instalačního programu sady Visual Studio změňte umístění instalace také uložené v tomto adresáři.

 > [!NOTE]
 > Je několik nástrojů a sad SDK, které mají různá pravidla na, kde může být jsou nainstalované. Tyto nástroje a sady SDK stále se nainstaluje na systémovou jednotku i v případě zvolte jiné umístění.)

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Instalace sady Visual Studio 2017](install-visual-studio.md)
* [Update Visual Studio 2017](update-visual-studio.md)
* [Upravit Visual Studio 2027](update-visual-studio.md)
* [Odinstalace sady Visual Studio 2017](uninstall-visual-studio.md)
