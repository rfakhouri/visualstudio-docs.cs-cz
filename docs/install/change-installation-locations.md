---
title: Změna umístění instalace v Visual Studio 2017
description: Zjistěte, jak dosáhnout snížení nároků instalace na systémové jednotce změnou umístění mezipaměti pro stahování, sdílení součástí, sady SDK a nástroje k jiné jednotky.
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
ms.openlocfilehash: eef4f8b66da517e471a25bb36e777f6cc343b0a3
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
---
# <a name="change-the-installation-locations-in-visual-studio-2017"></a>Změňte umístění instalace v Visual Studio 2017

**Novinka v 15.7**: nároky na instalaci můžete snížit na systémové jednotce přesunutím mezipaměť pro stahování, sdílení součástí, sady SDK a nástroje k jiné jednotky.

Tady je způsob.

1. Při instalaci sady Visual Studio, vyberte **možnosti instalace** kartě.

  ![Změňte umístění instalace sady Visual Studio 2017 -](media/installation-options-by-location.png "změnit umístění instalace.")

  > [!IMPORTANT]
  > Pokud pozastavit instalace a později ho obnovit, Visual Studio převezme kde bylo přerušeno. Jinými slovy jeho průběh instalace se vztahuje na co je zbývající ke stažení a instalaci a není spuštěna z předchozí počet.

2. V **Visual Studio IDE** část, přijměte výchozí nastavení. To nainstaluje základním produktu a obsahuje soubory, které jsou specifické pro tato verze sady Visual Studio.

 > [!IMPORTANT]
 > Pokud je systémové jednotky SSD jednotka SSD (Solid-State Drive), zde je proč doporučujeme přijmout výchozí umístění na systémové jednotce: při vývoji v sadě Visual Studio, můžete číst z a zapisovat do velké množství souborů, což zvyšuje úroveň vstupně-výstupní aktivitu disku.  Doporučujeme vybrat jednotce nejrychlejší pro zpracování zátěže.

2. V **stáhnout mezipaměti** část, rozhodnout, zda chcete zachovat mezipaměť pro stahování a pak zaškrtněte nebo zrušte zaškrtnutí políčka **zachovat stažení mezipaměti** odpovídajícím způsobem. <br><br>Pokud se rozhodnete zachovat mezipaměť pro stahování, umístění se používá pouze dočasně. Tato akce také, nebude mít vliv na a odstraňovat soubory z předchozí instalace. (Chcete-li vyčistit všechny instalační balíčky, musíte upravit předchozí instalace samostatně.)

3. V **stáhnout mezipaměti** části, zadejte jednotku, kam chcete uložit manifestů a instalační soubory. <br><br>Pokud vyberete zatížení "Vývoj aplikací s jazykem C++", dočasně požadovaná velikost je 1.58 GB na systémové jednotce, která je pak uvolněno při dokončení instalace.

 > [!NOTE]
 > Soubory jsou nejprve stáhne do dočasné složky na systémové jednotce a později odstranit po Visual Studio ověřuje a přesune do složky mezipaměti stahování. Pokud vyberete možnost zachovat mezipaměť pro stahování na jinou jednotku, Visual Studio stále musí místa na disku, který je ekvivalentní pro velikost mezipaměti stahování na systémové jednotce.
 > [!IMPORTANT]
 > Umístění je nastaven s instalací prvního a není možné později změnit z instalačního programu uživatelského rozhraní. Místo toho musíte [používání parametrů příkazového řádku](use-command-line-parameters-to-install-visual-studio.md) přesunout mezipaměť pro stahování

4. V **sdílené součásti, nástroje a sady SDK** části, zadejte jednotku, ve které chcete ukládat soubory, které jsou sdíleny instalace sady Visual Studio vedle sebe. Sady SDK a nástroje, které umožní instalační program sady Visual Studio změnit jeho umístění instalace, které jsou také uloženy v tomto adresáři.

 > [!NOTE]
 > Je několik nástrojů a SDK, které mají různá pravidla na, kde mohou být jsou nainstalovány. Těchto nástrojů a SDK bude stále nainstalována na systémové jednotce i v případě vyberte jiné umístění.)

## <a name="get-support"></a>Získat podporu

V některých případech může problémů. Pokud se nezdaří instalace Visual Studia, najdete v článku [problémy instalace a upgrade řešení potíží s Visual Studio 2017](troubleshooting-installation-issues.md) stránku nápovědy. Můžete nám také požádejte o pomoc instalace pomocí [live chat](https://www.visualstudio.com/vs/support/#talktous) (pouze v angličtině); Další informace najdete v tématu [Visual Studio "Kontaktujte nás" stránka](https://www.visualstudio.com/vs/support/#talktous).

Tady je několik další možnosti podpory:

* Můžete hlášení problémů produktu pro nás prostřednictvím [nahlásit problém](../ide/how-to-report-a-problem-with-visual-studio-2017.md) nástroj, který se zobrazí v instalačním programu Visual Studio i v integrovaném vývojovém prostředí sady Visual Studio.
* Návrh produktu s námi můžete sdílet na [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Můžete sledovat problémy produktu a najít v odpovědi [Visual Studio Community vývojáře](https://developercommunity.visualstudio.com/).
* Můžete také použít s námi a jinými vývojáři Visual Studio prostřednictvím [Visual Studio konverzace v komunitě Gitter](https://gitter.im/Microsoft/VisualStudio). (Tato možnost vyžaduje [Githubu](https://github.com/) účtu.)

## <a name="see-also"></a>Viz také

* [Nainstalovat Visual Studio 2017](install-visual-studio.md)
* [Update Visual Studio 2017](update-visual-studio.md)
* [Upravit Visual Studio 2027](update-visual-studio.md)
* [Odinstalace Visual Studio 2017](uninstall-visual-studio.md)
