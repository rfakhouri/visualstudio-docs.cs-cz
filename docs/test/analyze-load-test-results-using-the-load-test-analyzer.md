---
title: Analýza výsledků zátěžových testů v sadě Visual Studio
ms.date: 10/20/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, test results
- load tests, analyzing test results
- load tests, managing test results
ms.assetid: 8a4ba300-425d-447c-91d9-c53f4345feee
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 7890f5c1db26616ec1041b202a3863d1fbfae20e
ms.sourcegitcommit: f685fa5e2df9dc307bf1230dd9dc3288aaa408b5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2018
ms.locfileid: "36234160"
---
# <a name="analyze-load-test-results-using-the-load-test-analyzer"></a>Analýza výsledků zátěžového testu pomocí Analyzéru spouštění testů

Hledání problémových míst, identifikovat chyby a měření vylepšení v aplikaci při použití **Analyzéru zátěžového testu**. Analýza výsledků zátěžových testů v těchto způsobů:

-   Sledování zátěžový test, zda je spuštěná.

-   Analýza zátěžový test, po jeho dokončení.

-   Zobrazení výsledků z předchozího zátěžový test.

Můžete také vytvořit sestavy, které porovnávají dvou nebo více sestav pro analýzu trendů sdílet s zúčastněným stranám. V tématu [Reporting zátěžové testy s výsledky pro porovnávání testů a analýzu trendů](../test/compare-load-test-results.md).

Můžete provést tyto úlohy jestli spuštění zátěžového testu z Visual Studio Enterprise nebo z příkazového řádku a jestli se v jednom počítači nebo ve vzdáleném počítači spusťte zátěžový test.

## <a name="differences-between-analyzing-a-running-and-a-completed-load-test"></a>Rozdíly mezi analýza spuštěný a dokončeného zátěžového testu

 Při spuštění zátěžového testu **načíst testování analyzátor** zobrazí na samostatné kartě spolu s název zátěžový test a čas, který byl spuštěn test (například **LoadTest1 [12:40 PM]**). Po spuštění zátěžového testu menší sadu data čítače výkonu se udržuje v paměti. Tuto sadu dat můžete sledovat, při spuštění zátěžového testu. Po dokončení zátěžový test, můžete analyzovat kompletní data z databáze. Existují rozdíly v jaká data se zobrazí, když běží zátěžový test a co data, která se zobrazí po zatížení test byla dokončena. Například 90 procent a 95 procent času data odpovědi není vypočítat, dokud se nedokončí zátěžový test. Některé rozdíly ve funkci nástroje, které jsou k dispozici k analýze dat taky dojít.

 Když spustíte zátěžový test, jsou k dispozici dvě zobrazení: **grafy** zobrazení a **tabulky** zobrazení. **Grafy** zobrazení umožňuje grafu čítače výkonu, které byly shromážděny. **Tabulky** zobrazení získáte informace o jednotlivých testů, stránky, transakce a požadavky, které byly shromážděny. Můžete také získat tabulku, která obsahuje chyby.

 Ve výchozím nastavení po dokončení zátěžový test, spusťte **Souhrn** je zobrazeno zobrazení. Můžete přepínat mezi **Souhrn**, **grafy**, **tabulky**, a **podrobnosti** zobrazení pomocí panelu nástrojů. **Analyzéru zátěžového testu** můžete ukotven, nebo nastavte float pomocí technik manipulaci obvykle okno sady Visual Studio. Když analyzujete dokončeného zátěžového testu běží, může mít více **načíst testování analyzátorů** otevřete ve stejnou dobu k porovnání spouští různé zátěžový test.

## <a name="tasks"></a>Úlohy

|Úlohy|Související témata|
|-----------|-----------------------|
|**Přístup k výsledků zátěžového testu:** při spuštění zátěžového testu z editoru načíst otestovat, automaticky otevře výsledků zátěžových testů a spuštěné zátěžového testu se zobrazí v **načíst testování analyzátor**.|-   [Postupy: přístup k analýze výsledků zátěžového testu](../test/how-to-access-load-test-results-for-analysis.md)|
|**Přidání poznámky k analýze do zátěžového testu:** komentáře můžete přidat do zátěžový test při provedení analýzy. Komentáře jsou uloženy trvale, společně s výsledků testů zatížení. Popis, který zadáte také zobrazí v **popis** sloupec, který je přidružen zátěžového testu v **otevřete a spravovat výsledky testu** dialogové okno v editoru načíst otestovat.<br /><br /> Další informace najdete v tématu [postupy: přístup výsledků zátěžového testu pro analýzu](../test/how-to-access-load-test-results-for-analysis.md).<br /><br /> Při vytvoření sestavy aplikace Excel pro zatížení výsledky testů se navíc nezobrazí komentáře.<br /><br /> Další informace najdete v tématu [Reporting zátěžové testy s výsledky pro porovnávání testů a analýzu trendů](../test/compare-load-test-results.md).|-   [Postupy: přidávání komentářů během analýzy dokončeného zátěžového testu](../test/how-to-add-comments-on-a-completed-load-test.md)|
|**Analýza výsledků zátěžového testu:** po získat přístup k zátěžový test, který spouští dat, výsledná data můžete analyzovat. Můžete zobrazit souhrn testu zatížení rychle pochopit výsledky. Souhrn testu zatížení zobrazuje výsledky klíče ve formátu compact a snadno pro čtení.<br /><br /> Můžete si ho vytisknout souhrn testu zatížení. Díky tomu je vhodnější použít při komunikaci výsledky zúčastněným stranám.<br /><br /> Podrobnosti o si výsledky testu zatížení můžete analyzovat pomocí grafů a tabulek ve výsledcích. Mezi ně patří **chyby**, **stránky**, **požadavky**, **trasování SQL**, **testy**,  **Prahové hodnoty**, a **transakce**.|-   [Přehled souhrnu výsledků testu zatížení](../test/load-test-results-summary-overview.md)<br />-   [Postupy: zobrazení webové stránky odpovědi](../test/how-to-view-web-page-response-time-in-a-load-test.md)<br />-   [Analýza mezních pravidel](../test/analyze-threshold-rule-violations-in-load-tests.md)<br />-   [Analýza výsledků zátěžových testů v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md)<br />-   [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)|
|**Analýza aktivity virtuálních uživatelů ve vaší výsledcích zátěžového testu izolovat problémy s výkonem:** grafu aktivity virtuálního uživatele můžete použít k vizualizaci, co dělají virtuálních uživatelů během zátěžového testu. To vám může pomoct izolovat špičky v Procesorem nebo vyřazuje v požadavků za sekundu a zjistit, které testy nebo stránky počítač během těchto špičky a hodnota neklesne.|-   [Analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)|