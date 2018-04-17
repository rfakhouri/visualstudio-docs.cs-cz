---
title: Zobrazení dat a příloh diagnostiky pro zátěžové testy v sadě Visual Studio | Microsoft Docs
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, data and diagnostics attachments
ms.assetid: 73309bdd-437a-4eb0-88c8-702c3e24b9b0
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-ide-test
ms.openlocfilehash: 08e4ce09103cd5f06926147ae38b916ae666648b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-view-data-and-diagnostic-attachments-using-the-load-test-analyzer"></a>Postupy: Zobrazení příloh diagnostiky dat pomocí analyzéru zátěžového testu

Před spuštěním zátěžového testu si lze vybrat nastavení testu, které určuje diagnostické adaptéry a adaptéry dat, které chcete použít. Po dokončení zátěžového testu lze pomocí Analyzéru zátěžového testu zobrazit podrobnosti těchto diagnostických adaptérů a adaptérů dat během analýzy výsledků. Chcete-li zobrazit data a adaptéru diagnostických podrobnosti, vyberte **zobrazení dat a příloh diagnostiky** tlačítka na panelu nástrojů Analyzéru zátěžového testu. Pokud měl například zátěžový test v nastavení nakonfigurován adaptér systémových informací, lze zobrazit systémové informace pro počítač, který byl při běhu zátěžového testu použit.

![Výběr dialogové okno přílohy adaptér diagnostických dat](../test/media/load_adapterdialog.png "Load_AdapterDialog")

Dalším příkladem je zátěžový test, který v nastavení testu zahrnuje adaptér technologie IntelliTrace. Adaptér technologie IntelliTrace umožňuje otevírat souhrnnou stránku technologie IntelliTrace.

![Souhrn IntelliTrace](../test/media/load_intellitrace.png "Load_IntelliTrace")

Další informace najdete v tématu [shromažďovat diagnostické informace využitím testovacích nastavení](../test/collect-diagnostic-information-using-test-settings.md) a [dat shromažďování IntelliTrace](../test/how-to-collect-intellitrace-data-to-help-debug-difficult-issues.md).

## <a name="to-view-data-and-diagnostic-attachments-in-a-load-test-from-the-load-test-analyzer"></a>Zobrazení příloh diagnostiky dat v zátěžovém testu z Analyzéru zátěžového testu

1.  Po dokončení testu zatížení nebo po otevření výsledků testů zatížení, v panelu nástrojů nástroje načíst testování Analyzer společnosti, zvolte **zobrazení dat a příloh diagnostiky**.

     **Zvolte adaptéru diagnostických dat** se zobrazí dialogové okno.

2.  Vyberte přílohu adaptéru diagnostických dat, která chcete analyzovat a pak zvolte **OK**.

## <a name="see-also"></a>Viz také

- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)