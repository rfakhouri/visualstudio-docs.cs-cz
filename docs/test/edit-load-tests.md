---
title: "Úpravy zátěžových testů v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- Load Test Editor
- load tests, Load Test Editor
ms.assetid: ba16ed02-137e-40bf-a4cb-45d87d922d37
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: f8a6d4bbec460103f1e8db596fa5d8b523c1bd92
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="edit-load-tests"></a>Upravit zátěžových testů

Zátěžové testy spustit testy výkonnosti webu nebo testy jednotek k simulaci mnoha uživateli přístup k serveru ve stejnou dobu. Zátěžový test umožňuje přístup k datům zátěže a výkonu aplikace. Zátěžový test lze nakonfigurovat pro emulaci rozličných podmínek zátěže, jako je uživatelská zátěž nebo typ sítě.

> [!NOTE]
> Zátěžové testování je k dispozici pouze v edici Enterprise systému Visual Studio 2017.

Zátěžový test je definována *scénáře*, *čítače sady*, a *spustit nastavení*. Na následujícím obrázku vysvětluje rozdíly mezi [scénáře](../test/edit-load-test-scenarios.md), [čítače sady](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md), a [spustit nastavení](../test/load-test-run-settings-properties.md):

![Architektura testu zatížení](../test/media/load_test_editor.png)

## <a name="edit-load-test-scenario-settings"></a>Upravit nastavení načítání testovací scénář

Scénář se používá k modelu, jak skupiny uživatelů komunikuje s serverová aplikace. Scénáře se skládají ze vzoru zatížení, modelu kombinace testů, kombinace testů, kombinace prohlížečů a kombinace sítí. Zátěžový test může mít více než jeden scénář a jeden scénář může obsahovat testy výkonnosti webu a testy částí. Seskupením podobných nastavení umožňuje scénář seskupit podobné testy a spustit je současně.

Další informace najdete v tématu [úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md) a [vlastnosti scénáře zátěžového testu](../test/load-test-scenario-properties.md).

## <a name="configure-and-manage-performance-counter-sets"></a>Konfigurace a Správa sad čítačů výkonu

Zátěžové testy zadat sady s názvem čítače, uspořádané podle technologie, které jsou užitečné při analýze dat čítačů výkonu. Sady čítačů zahrnují zátěžový Test, IIS, ASP.NET a SQL. Když vytvoříte zátěžový test s načíst testování Průvodce novým, počáteční sadu předdefinovaných a důležité čítače je nakonfigurován pro počítače, které zadáte pro zahrnutí do zátěžový test. Můžete spravovat vaše čítače v editoru zátěžových testů.

Další informace najdete v tématu [určení sad čítačů a mezních pravidel pro počítače v zátěžovém testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md).

## <a name="configure-and-manage-load-test-run-settings"></a>Konfigurovat a spravovat nastavení testu zatížení

Spuštění nastavení jsou vlastnosti, které ovlivňují způsob spuštění zátěžového testu. Spuštění nastavení jsou uspořádány do kategorií v okně Vlastnosti.

Další informace najdete v tématu [konfigurace parametrů běhu testu zatížení](../test/configure-load-test-run-settings.md) a [vlastnosti nastavení spustit Test zatížení](../test/load-test-run-settings-properties.md).

## <a name="see-also"></a>Viz také

- [Analýza výsledků zátěžových testů](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Analýza mezních pravidel](../test/analyze-threshold-rule-violations-in-load-tests.md)