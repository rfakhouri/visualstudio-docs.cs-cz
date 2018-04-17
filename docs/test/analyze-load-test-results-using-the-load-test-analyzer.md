---
title: Analýza výsledků zátěžových testů v sadě Visual Studio | Microsoft Docs
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
ms.technology: vs-ide-test
ms.openlocfilehash: 7add3789d3c48fb405818f50efd47bb83cb9f899
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="analyze-load-test-results-using-the-load-test-analyzer"></a>Analýza výsledků zátěžového testu pomocí Analyzéru zátěžového testu

Najít kritická místa a identifikovat chyby měření vylepšení v aplikaci při použití Analyzéru zátěžového testu. Analýza výsledků zátěžových testů v těchto způsobů:

-   Sledování zátěžový test, zda je spuštěná.

-   Analýza zátěžový test, po jeho dokončení.

-   Zobrazení výsledků z předchozího zátěžový test.

Můžete také vytvořit sestavy, které porovnávají dvou nebo více sestav pro analýzu trendů sdílet s zúčastněným stranám. V tématu [Reporting zátěžové testy s výsledky pro porovnávání testů a analýzu trendů](../test/compare-load-test-results.md).

Můžete provést tyto úlohy jestli spuštění zátěžového testu z Visual Studio Enterprise nebo z příkazového řádku a jestli se v jednom počítači nebo ve vzdáleném počítači spusťte zátěžový test.

## <a name="differences-between-analyzing-a-running-and-a-completed-load-test"></a>Rozdíly mezi analýza spuštěný a dokončeného zátěžového testu

 Při spuštění zátěžového testu zatížení testování analyzátor zobrazí na samostatné kartě spolu s název zátěžový test a čas, který byl spuštěn test (například **LoadTest1 [12:40 PM]**). Po spuštění zátěžového testu menší sadu data čítače výkonu se udržuje v paměti. Tuto sadu dat můžete sledovat, při spuštění zátěžového testu. Po dokončení zátěžový test, můžete analyzovat kompletní data z databáze. Existují rozdíly v jaká data se zobrazí, když běží zátěžový test a co data, která se zobrazí po zatížení test byla dokončena. Například 90 procent a 95 procent času data odpovědi není vypočítat, dokud se nedokončí zátěžový test. Některé rozdíly ve funkci nástroje, které jsou k dispozici k analýze dat taky dojít.

 Když spustíte zátěžový test, jsou k dispozici dvě zobrazení: zobrazení grafů a tabulek zobrazení. Zobrazení grafů můžete graf čítače výkonu, které byly shromážděny. Zobrazení tabulky poskytuje informace o jednotlivých testů, stránky, transakce a požadavky, které byly shromážděny. Můžete také získat tabulku, která obsahuje chyby.

 Ve výchozím nastavení je po dokončení spuštění zátěžového testu zobrazí souhrnné zobrazení. Můžete přepínat mezi zobrazení souhrn, grafy, tabulky a podrobnosti s použitím panelu nástrojů. Analyzéru zátěžového testu může být ukotveno nebo nastavte na float pomocí technik manipulaci obvykle okno sady Visual Studio. Když analyzujete dokončeného zátěžového testu běží, může mít několik zatížení testování analyzátorů otevřete ve stejnou dobu k porovnání testovací spouští různé zatížení.

## <a name="tasks"></a>Úlohy

|Úlohy|Související témata|
|-----------|-----------------------|
|**Přístup k výsledků zátěžového testu:** při spuštění zátěžového testu z editoru načíst otestovat, automaticky otevře výsledků zátěžových testů a v analyzátor spouštění testů se zobrazí spuštěné zátěžový test.|-   [Postupy: přístup k výsledků zátěžového testu pro analýzu](../test/how-to-access-load-test-results-for-analysis.md)|
|**Přidání poznámky k analýze do zátěžového testu:** komentáře můžete přidat do zátěžový test při provedení analýzy. Komentáře jsou uloženy trvale, společně s výsledků testů zatížení. Popis, který zadáte také zobrazí v **popis** sloupec, který je přidružen zátěžového testu v dialogovém okně Otevřít a správa výsledků testů v editoru načíst testování.<br /><br /> Další informace najdete v tématu [postupy: přístup výsledků zátěžového testu pro analýzu](../test/how-to-access-load-test-results-for-analysis.md).<br /><br /> Při vytvoření sestavy aplikace Excel pro zatížení výsledky testů se navíc nezobrazí komentáře.<br /><br /> Další informace najdete v tématu [Reporting výsledků zátěžových testů pro porovnávání testů a analýzu trendů](../test/compare-load-test-results.md).|-   [Postupy: přidávání komentářů během analýzy dokončeného zátěžového testu](../test/how-to-add-comments-on-a-completed-load-test.md)|
|**Analýza výsledků zátěžového testu:** po získat přístup k zátěžový test, který spouští dat, výsledná data můžete analyzovat. Můžete zobrazit souhrn testu zatížení rychle pochopit výsledky. Souhrn testu zatížení zobrazuje výsledky klíče ve formátu compact a snadno pro čtení.<br /><br /> Můžete si ho vytisknout souhrn testu zatížení. Díky tomu je vhodnější použít při komunikaci výsledky zúčastněným stranám.<br /><br /> Podrobnosti o si výsledky testu zatížení můžete analyzovat pomocí grafů a tabulek ve výsledcích. Jedná se o chyby, stránky, požadavků, trasování SQL, testů, prahové hodnoty a transakce.|-   [Načíst přehled souhrnu výsledků testu](../test/load-test-results-summary-overview.md)<br />-   [Postupy: zobrazení doby odezvy webové stránky](../test/how-to-view-web-page-response-time-in-a-load-test.md)<br />-   [Analýza mezních pravidel](../test/analyze-threshold-rule-violations-in-load-tests.md)<br />-   [Analýza výsledků zátěžových testů v zobrazení grafů](../test/analyze-load-test-results-in-the-graphs-view.md)<br />-   [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md)|
|**Analýza aktivity virtuálních uživatelů ve vaší výsledcích zátěžového testu izolovat problémy s výkonem:** grafu aktivity virtuálního uživatele můžete použít k vizualizaci, co dělají virtuálních uživatelů během zátěžového testu. To vám může pomoct izolovat špičky v Procesorem nebo vyřazuje v požadavků za sekundu a zjistit, které testy nebo stránky počítač během těchto špičky a hodnota neklesne.|-   [Analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)|