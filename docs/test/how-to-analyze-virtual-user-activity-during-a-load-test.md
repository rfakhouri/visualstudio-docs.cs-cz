---
title: Analýza aktivity virtuálních uživatelů pro zátěžové testy v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- virtual user activity chart, viewing
ms.assetid: 8bda19b3-91c1-4daf-b6c7-09108bddadff
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 20367c2632e62d53199ee7bc1a522b81b570070e
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/20/2018
ms.locfileid: "39178502"
---
# <a name="how-to-analyze-what-virtual-users-are-doing-during-a-load-test-using-the-virtual-user-activity-chart"></a>Postupy: Analýza činnosti virtuálních uživatelů během zátěžového testu pomocí graf aktivity virtuálního uživatele

Zobrazte aktivity virtuálního uživatele, který je spojen se zátěžovým testem pomocí graf aktivity virtuálního uživatele. Každý řádek v tabulce představuje jednotlivého virtuálního uživatele. Přesně co jednotlivé virtuální uživatele se provádí během testu zobrazí graf aktivity virtuálního uživatele. Můžete vidět vzory aktivity uživatelů, vzory zátěže, korelovat Nezdařená nebo pomalá testy a zobrazují požadavky pomocí další aktivity virtuálního uživatele. Graf aktivity virtuálního uživatele je k dispozici pouze po dokončení zátěžového testu.

Následující postupy ukazují, jak zobrazit graf aktivity virtuálního uživatele, jak prozkoumat aktivita konkrétního uživatele a jak používat filtrování.

## <a name="to-view-the-virtual-user-activity-chart-in-your-load-test-results"></a>Chcete-li zobrazit graf aktivity virtuálního uživatele ve vašich výsledcích zátěžového testu

1.  Chcete-li zobrazit data virtuálního uživatele, je nutné nejprve nakonfigurovat **detaily o všech jednotlivých položkách** nastavení **úložiště podrobností časování** vlastnost, která je spojen se zátěžovým testem. Spusťte zátěžový test. Další informace najdete v tématu [postupy: Konfigurace shromažďování veškerých podrobností a zpřístupnění grafu aktivity virtuálního uživatele](../test/how-to-configure-load-tests-to-collect-full-details.md).

2.  Po zatížení testovacích běhů, zobrazuje souhrnnou stránku výsledků testu. Zvolte **podrobnosti uživatele** tlačítko na panelu nástrojů.

     -nebo-

     Otevřít zobrazení grafů výběrem **grafy** tlačítko na panelu nástrojů. Klikněte pravým tlačítkem na graf a potom vyberte **přejít na podrobnosti uživatele**.

     Pokud použijete tuto možnost, graf aktivity virtuálního uživatele bude automatické přiblížení část testu, který jste klikli pravým tlačítkem myši. Například, pokud ukazatel myši nachází na přibližně 30 druhý označit, zobrazení podrobností se zobrazí přibližně na značce 30 druhý v **přiblížení na dobu** nástroj v dolní části grafu aktivity virtuálního uživatele.

     Dále můžete prozkoumat podrobnosti o konkrétním uživatelům aktivitě v graf aktivity virtuálního uživatele.

## <a name="to-investigate-a-specific-users-activity-in-the-virtual-user-activity-chart"></a>Prozkoumat konkrétní uživatele aktivity v graf aktivity virtuálního uživatele

1.  Vyberte oblast v grafu, ve které chcete prozkoumat podrobnosti o konkrétního uživatele použijte funkce zvětšení na čas období nástroj v dolní části graf aktivity virtuálního uživatele.

2.  Podržte ukazatel myši nad podrobností v grafu. Všimněte si, že tyto informace se zobrazí v popisu tlačítka:

    -   **Id uživatele**

    -   **Scénář**

    -   **Test**

    -   **Adresa URL** (nejsou zobrazeny v testu nebo transakce)

    -   **Výsledek**

    -   **Prohlížeč** (nejsou zobrazeny v testu nebo transakce)

    -   **Sítě**

    -   **Čas spuštění**

    -   **Doba trvání**

    -   **Agent**

    -   **Protokol testu** (odkaz na protokol testu)

        > [!NOTE]
        > Pomáhat při ladění aplikace, pokud kliknete na odkaz protokolu testu bude otevřít výsledek webového testu nebo výsledky testů jednotek přidružené k protokolu.

     Operace filtrování a zvýraznění, které jsou k dispozici v dalším kroku můžete graf aktivity virtuálního uživatele.

## <a name="to-use-filtering-options-in-the-virtual-user-activity-chart"></a>Použití možnosti filtrování v graf aktivity virtuálního uživatele

1.  V legendě podrobnosti pomocí rozevíracího seznamu vyberte buď **testovací**, **stránky**, nebo **transakce**.

     **Panel podrobné legendy**

     ![Panel podrobné legendy](../test/media/ltest_detailslegend.png)

2.  Zaškrtněte nebo zrušte zaškrtnutí políček u chyby, protokoly, testy, vyhledávání a stránky aspx, které jsou spojeny se zátěžovým testem.

     Graf aktivity virtuálního uživatele odpovídajícím způsobem aktualizuje.

     Graf aktivity virtuálního uživatele umožňuje filtrovat testy, stránky a transakce na základě několika různých kritérií. Můžete odebrat určité testy ze zobrazení, nebo odebrání všech úspěšných testů nebo odebrání testy, které se nezdařilo s některým chybám. Můžete také odebrat všechny testy, které nemají protokoly.

     Například můžete vybrat **(zvýraznit chyby)** možnost, která se zobrazí všechny chyby v košíku vybarvenými červeně. Můžete také vybrat **(zvýraznit výsledky s protokoly)** možnost, která se zobrazí všechny výsledky testů, které mají protokoly vybarvenými zeleně v grafu.

     **Filtrovat panel výsledků**

     ![Filtrovat panel výsledků](../test/media/ltest_filterresults.png)

3.  Ve výsledcích Filtr zaškrtněte nebo zrušte zaškrtnutí políček u následující možnosti filtru:

    -   **Zobrazit pouze výsledky s protokoly** zobrazí pouze výsledky, které mají protokolů testu k nim má přiřazené testů.

    -   **Zobrazit úspěšné výsledky** úspěšné výsledky se zobrazí.

    -   **Zobrazit výsledky s chybami** zobrazuje výsledky s chybami, které vám můžou pomoct při ladění.

        > [!NOTE]
        > Seznam typů chyb, které jsou uvedeny v části **zobrazit výsledky s chybami** uzel můžete zkoumat kliknutím na tlačítko tabulek v **prohlížeče výsledků testu výkonnosti webu** nástrojů. Další informace najdete v tématu [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

     Graf aktivity virtuálního uživatele odpovídajícím způsobem aktualizuje.

## <a name="see-also"></a>Viz také:

- [Analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)
- [Návod: Izolace potíží s pomocí graf aktivity virtuálního uživatele](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)