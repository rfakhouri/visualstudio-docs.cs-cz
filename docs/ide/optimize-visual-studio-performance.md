---
title: Zlepšení výkonu při pomalém sady Visual Studio
titleSuffix: ''
ms.date: 04/11/2018
ms.topic: conceptual
helpviewer_keywords:
- performance [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
f1_keywords:
- vs.performancecenter
ms.workload:
- multiple
ms.openlocfilehash: d163edf5e08df3b60bdf664da8048781927729ac
ms.sourcegitcommit: cea6187005f8a0cdf44e866a1534a4cf5356208c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/27/2019
ms.locfileid: "56953583"
---
# <a name="optimize-visual-studio-performance"></a>Optimalizace výkonu sady Visual Studio

Tento článek obsahuje několik návrhů vyzkoušet, pokud zjistíte, že Visual Studio běží pomalu. Můžete taky využít podívat [a tipy k výkonu sady Visual Studio](../ide/visual-studio-performance-tips-and-tricks.md) další návrhy na vylepšení výkonu.

## <a name="upgrade-to-visual-studio-2017-version-156-or-later"></a>Upgrade na Visual Studio 2017 verze 15.6 nebo novější

Pokud aktuálně používáte Visual Studio 2015, stáhněte si [Visual Studio 2017](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) zdarma, podívejte se na jeho vylepšení výkonu. Řešení se načítají dvakrát až třikrát rychleji v sadě Visual Studio 2017 se vylepšení výkonu v jiných oblastech příliš. Visual Studio 2017 je vedle sebe kompatibilní s Visual Studiem 2015, takže nic nepřijdete a vyzkoušejte si.

Pokud aktuálně používáte Visual Studio 2017, ujistěte se, že používáte verzi 15.6 nebo novější. Dat udávají, že řešení se načtení do dvakrát nebo třikrát rychlejší ve verzi 15.6. Stáhněte si ho [tady](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

## <a name="extensions-and-tool-windows"></a>Rozšíření a okna nástrojů

Můžete mít nainstalovaná rozšíření, které snižují sady Visual Studio. Nápověda pro správu rozšíření kvůli zvýšení výkonu, naleznete v tématu [změnit nastavení rozšíření kvůli zvýšení výkonu](../ide/optimize-visual-studio-startup-time.md#extensions).

Podobně může mít okna nástrojů, které snižují sady Visual Studio. Nápovědu pro správu nástroje windows najdete v tématu [změnit nastavení okna nástroje pro zvýšení výkonu](../ide/optimize-visual-studio-startup-time.md#tool-windows).

## <a name="hardware"></a>Hardware

Pokud uvažujete o hardwaru, jednotky SSD (Solid-State Drive) má další dopad na výkon než další paměť RAM nebo na rychlejší procesor.

Pokud chcete přidat SSD, pro zajištění optimálního výkonu instalaci Windows na této jednotce, na rozdíl od pevných discích (HDD). Umístění disku řešení sady Visual Studio nefunguje co nejvíce záleží.

Kromě toho nespouštějte řešení z USB Flash disk. Zkopírujte ho do pevný disk nebo SSD.

## <a name="help-us-improve"></a>Pomozte nám zlepšovat kvalitu

Vaše zpětná vazba pomůže nám se zdokonalovat. Použití **nahlásit problém** funkci pro trasování "záznam" a odeslat společnosti Microsoft. Vyberte ikonu zpětné vazby vedle **rychlé spuštění**, nebo vyberte **pomáhají** > **odeslat zpětnou vazbu** > **nahlásit problém** z řádku nabídek. Další informace najdete v tématu [postup ohlášení problému se sadou Visual Studio](../ide/how-to-report-a-problem-with-visual-studio.md).

## <a name="see-also"></a>Viz také:

- [Tipy ke zvýšení výkonu a triky](../ide/visual-studio-performance-tips-and-tricks.md)
- [Blog Visual Studio – zátěžové řešení rychleji s využitím sady Visual Studio 2017 verze 15.6](https://devblogs.microsoft.com/visualstudio/load-solutions-faster-with-visual-studio-2017-version-15-6/)