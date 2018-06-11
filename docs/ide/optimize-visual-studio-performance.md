---
title: Zvýšit výkon, pokud jde o pomalé Visual Studio
ms.date: 04/11/2018
ms.topic: conceptual
helpviewer_keywords:
- performance [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
f1_keywords:
- vs.performancecenter
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.workload:
- multiple
ms.openlocfilehash: b185beaeefeeedaeb63ac6d102d2207926e52748
ms.sourcegitcommit: 34f7d23ce3bd140dcae875b602d5719bb4363ed1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2018
ms.locfileid: "35257732"
---
# <a name="optimize-visual-studio-performance"></a>Optimalizace výkonu v sadě Visual Studio

Tento článek obsahuje některé návrhy pokusit Pokud zjistíte, že Visual Studio je pomalý. Můžete taky využít podívejte se na [Rady a tipy pro zvýšení výkonu sady Visual Studio](../ide/visual-studio-performance-tips-and-tricks.md) další návrhy na zlepšení výkonu.

## <a name="upgrade-to-visual-studio-2017-version-156-or-later"></a>Upgrade na verzi Visual Studio 2017 15,6 operací nebo novější

Pokud aktuálně používáte Visual Studio 2015, stáhněte si [Visual Studio 2017](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) zdarma a podívejte se na její lepší výkon. Řešení načíst dvakrát až třikrát rychlejší v aplikaci Visual Studio 2017 s vylepšení výkonu v jiných oblastech příliš. Visual Studio 2017 je vedle sebe kompatibilní s Visual Studiem 2015, abyste neztratili nic tak, že zkusíte.

Pokud aktuálně používáte Visual Studio 2017, zkontrolujte, zda že používáte verzi 15.6 nebo novější. Data se zobrazují, že se řešení načíst dvě nebo tři časy rychlejší ve verzi 15,6 operací. Stažení [zde](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

## <a name="extensions-and-tool-windows"></a>Rozšíření a okna nástrojů

Můžete mít nainstalovaná rozšíření, které jsou zpomalení nástroje Visual Studio. Pomoc na správu rozšíření ke zlepšení výkonu najdete v tématu [změnit nastavení rozšíření pro zlepšení výkonu](../ide/optimize-visual-studio-startup-time.md#extensions).

Obdobně může mít nástroj windows, které jsou zpomalení nástroje Visual Studio. Pomoc na správu nástroj windows najdete v tématu [změnit nastavení okna nástroj ke zlepšení výkonu](../ide/optimize-visual-studio-startup-time.md#tool-windows).

## <a name="hardware"></a>Hardware

Pokud uvažujete o upgrade hardwaru, na jednotku SSD (SSD) má více vliv na výkon než další paměť RAM nebo na rychlejší procesor.

Pokud přidáte SSD, pro zajištění optimálního výkonu instalaci systému Windows na této jednotce, a na jednotku pevného disku (HDD). Umístění disku řešení sady Visual Studio pravděpodobně vás co nejvíc.

Kromě toho se nespustí řešení z jednotky USB. Zkopírujte jej do HDD nebo SSD.

## <a name="help-us-improve"></a>Pomozte nám vylepšit

Vaše zpětná vazba nám pomůže vylepšovat. Použití **nahlásit problém** funkci pro trasování "záznam" a odeslat společnosti Microsoft. Vyberte ikonu pro zpětnou vazbu vedle **QuickLaunch**, nebo vyberte **pomoci** > **odeslat zpětnou vazbu** > **nahlásit problém** z řádku nabídek. Další informace najdete v tématu [postup nahlásit problém s Visual Studio 2017](../ide/how-to-report-a-problem-with-visual-studio-2017.md).

## <a name="see-also"></a>Viz také:

- [Rady a tipy pro zvýšení výkonu](../ide/visual-studio-performance-tips-and-tricks.md)
- [Visual Studio blog - zatížení řešení rychlejší s Visual Studio 2017 verze 15,6 operací](https://blogs.msdn.microsoft.com/visualstudio/2018/04/04/load-solutions-faster-with-visual-studio-2017-version-15-6/)