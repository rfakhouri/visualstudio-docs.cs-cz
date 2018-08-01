---
title: Zobrazit Data a diagnostické přílohy pro zátěžové testy v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, data and diagnostics attachments
ms.assetid: 73309bdd-437a-4eb0-88c8-702c3e24b9b0
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 228f8306b803fcbd0e83e23e5b8e919dc2116c37
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/31/2018
ms.locfileid: "39382461"
---
# <a name="how-to-view-data-and-diagnostic-attachments-using-the-load-test-analyzer"></a>Postupy: zobrazení data a diagnostické přílohy pomocí Analyzéru zátěžového testu

Před spuštěním zátěžového testu si lze vybrat nastavení testu, které určuje diagnostické adaptéry a adaptéry dat, které chcete použít. Po dokončení zátěžového testu, můžete použít **Analyzéru zátěžového testu** zobrazíte podrobnosti o těchto adaptérech diagnostiky a dat během analýzy výsledků. Chcete-li zobrazit data a podrobnosti o adaptéru diagnostiky, zvolte **zobrazit Data a diagnostické přílohy** tlačítko **Analyzéru zátěžového testu** nástrojů. Pokud měl například zátěžový test v nastavení nakonfigurován adaptér systémových informací, lze zobrazit systémové informace pro počítač, který byl při běhu zátěžového testu použit.

![Výběr dialogového okna přílohu adaptéru diagnostiky dat](../test/media/load_adapterdialog.png)

Dalším příkladem je zátěžový test, který v nastavení testu zahrnuje adaptér technologie IntelliTrace. Adaptér technologie IntelliTrace umožňuje otevírat **IntelliTrace – Souhrn** stránky.

![IntelliTrace – souhrn](../test/media/load_intellitrace.png)

Další informace najdete v tématu [shromažďování diagnostických informací pomocí nastavení testu](../test/collect-diagnostic-information-using-test-settings.md) a [data IntelliTrace shromažďování](../test/how-to-collect-intellitrace-data-to-help-debug-difficult-issues.md).

## <a name="to-view-data-and-diagnostic-attachments-in-a-load-test-from-the-load-test-analyzer"></a>Zobrazení příloh diagnostiky dat v zátěžovém testu z Analyzéru zátěžového testu

1.  Po dokončení zátěžového testu nebo po otevření výsledku zátěžového testu v **Analyzéru zátěžového testu** nástrojů, zvolte **zobrazit Data a diagnostické přílohy**.

     **Zvolte adaptér diagnostiky dat** se zobrazí dialogové okno.

2.  Vyberte přílohu adaptéru diagnostiky dat, který chcete analyzovat a klikněte na tlačítko **OK**.

## <a name="see-also"></a>Viz také:

- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
