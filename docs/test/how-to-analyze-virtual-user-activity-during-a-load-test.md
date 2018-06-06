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
ms.openlocfilehash: f7da7f881cf70ebfdafb3dbaaf2821471327fa81
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751231"
---
# <a name="how-to-analyze-what-virtual-users-are-doing-during-a-load-test-using-the-virtual-user-activity-chart"></a>Postupy: Analýza činnosti virtuálních uživatelů během zátěžového testu pomocí graf aktivity virtuálního uživatele

Zobrazte aktivity virtuálních uživatelů, který je spojen s zátěžového testu pomocí grafu aktivity virtuálního uživatele. Každý řádek v tabulce představuje jednotlivých virtuálních uživatelů. Přesně co každý virtuálních uživatelů se provádí během testu ukazuje grafu aktivity virtuálního uživatele. Můžete najdete v části vzory aktivity uživatelů, vzory zátěže, korelovat testy selhání nebo pomalé a najdete v části požadavky, které ostatní aktivity virtuálních uživatelů. Grafu aktivity virtuálního uživatele je k dispozici až po dokončení běhu zátěžového testu.

Níže uvedených postupech ukazují, jak zobrazit grafu aktivity virtuálního uživatele, jak prozkoumat aktivitu příslušného uživatele a používání filtrování.

## <a name="to-view-the-virtual-user-activity-chart-in-your-load-test-results"></a>Chcete-li zobrazit grafu aktivity virtuálního uživatele ve vaší výsledcích zátěžového testu

1.  Chcete-li zobrazit data virtuálních uživatelů, musíte nejdřív nakonfigurovat **všech podrobností o jednotlivých** nastavení pro **úložiště podrobností časování** vlastnost, která souvisí s zátěžový test. Pak spusťte zátěžový test. Další informace najdete v tématu [postupy: Konfigurace shromažďování veškerých podrobností a zpřístupnění grafu aktivity virtuálního uživatele](../test/how-to-configure-load-tests-to-collect-full-details.md).

2.  Po zatížení test běží, se zobrazí stránce shrnutí výsledků testu. Vyberte **podrobnosti uživatele** tlačítka na panelu nástrojů.

     -nebo-

     Otevřete zobrazení grafů výběrem **grafy** tlačítka na panelu nástrojů. Klikněte pravým tlačítkem na graf a pak vyberte **přejít k podrobnostem uživatele**.

     Pokud použijete tuto možnost, grafu aktivity virtuálního uživatele budou automaticky přiblížení do části test, který jste klepli pravým tlačítkem myši. Například pokud se ukazatel myši nachází na přibližně 30 druhý označit, zobrazení podrobností se zobrazí přibližně na značce 30 druhý v **zvětšení časové období** nástroj v dolní části grafu aktivity virtuálního uživatele.

     Dále můžete prozkoumat podrobnosti o aktivitě konkrétním uživatelům v grafu aktivity virtuálního uživatele.

## <a name="to-investigate-a-specific-users-activity-in-the-virtual-user-activity-chart"></a>Prozkoumat konkrétní uživatele aktivity v grafu aktivity virtuálního uživatele

1.  Použijte funkce zvětšení čas období nástroj v dolní části grafu aktivity virtuálního uživatele vyberte oblast v grafu, ve které chcete prozkoumat podrobnosti na konkrétního uživatele.

2.  Podržte ukazatel myši nad podrobností v grafu. Všimněte si, že v popisu tlačítka se zobrazí následující informace:

    -   **Id uživatele**

    -   **Scénář**

    -   **Test**

    -   **Adresa URL** (nezobrazí v testovacím nebo transakce)

    -   **Výsledek**

    -   **Prohlížeč** (nezobrazí v testovacím nebo transakce)

    -   **Sítě**

    -   **Čas spuštění**

    -   **Doba trvání**

    -   **Agent**

    -   **Testování protokolu** (vytvořit odkaz na protokol testovací)

        > [!NOTE]
        > Jako pomoc při ladění aplikace, pokud se rozhodnete odkaz Test protokolu, se otevře výsledků testů webových nebo výsledků testů jednotek přidružené k protokolu.

     Dále můžete operace filtrování a zvýraznění, které jsou k dispozici v grafu aktivity virtuálního uživatele.

## <a name="to-use-filtering-options-in-the-virtual-user-activity-chart"></a>Použití možností filtrování v grafu aktivity virtuálního uživatele

1.  V legendě podrobnosti, pomocí rozevíracího seznamu vyberte buď **Test**, **stránky**, nebo **transakce**.

     **Panel podrobnosti legendy**

     ![Panel podrobnosti legendy](../test/media/ltest_detailslegend.png)

2.  Vyberte nebo zrušte zaškrtnutí políček u chyby, protokoly, testů, vyhledávání a stránky aspx, které jsou přidruženy zátěžový test.

     Grafu aktivity virtuálního uživatele se aktualizuje.

     Grafu aktivity virtuálního uživatele poskytuje možnost filtrovat testy, stránky a transakce na základě několika různých kritérií. Můžete odebrat určité testy ze zobrazení, nebo odeberte všechny testy úspěšné nebo odeberte testy, které se nezdařilo s určitým chybám. Rovněž můžete odebrat všechny testy, které nemají protokoly.

     Například můžete vybrat **(zvýrazněte chyby)** možnost, která se zobrazí všechny chyby v košíku označeno červeně. Můžete také vybrat **(zvýrazněte výsledků s protokoly)** možnost, která se zobrazí všechny výsledky testů, které mají protokoly označeno zeleně v grafu.

     **Výsledky panel Filtr**

     ![Výsledky panel Filtr](../test/media/ltest_filterresults.png)

3.  Ve výsledcích filtru vyberte nebo zrušte zaškrtnutí políčka pro následující možnosti filtru:

    -   **Zobrazit pouze výsledky s protokoly** zobrazí pouze zkušební výsledky, které mají protokolů testování s nimi spojených.

    -   **Zobrazit výsledky úspěšné** zobrazí výsledky úspěšné.

    -   **Zobrazit výsledky s chybami** zobrazí výsledky s chybami, které může být užitečné při ladění.

        > [!NOTE]
        > Seznam typů chyb, které jsou uvedeny v části **zobrazit výsledky s chybami** uzlu můžete zkoumat kliknutím na tlačítko tabulky na panelu nástrojů Prohlížeč výsledků testu výkonnosti webu. Další informace najdete v tématu [Analýza výsledků zátěžových testů a chyb v tabulkovém zobrazení](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

     Grafu aktivity virtuálního uživatele se aktualizuje.

## <a name="see-also"></a>Viz také:

- [Analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)
- [Návod: Izolace problémů pomocí graf aktivity virtuálního uživatele](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)