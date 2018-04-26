---
title: Pomocí graf aktivity virtuálního uživatele pro zátěžové testy v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, virtual user activity chart
- virtual user activity chart, isolating performance issues
ms.assetid: d1c10fb9-cfeb-4e7f-9991-2d1e1103699e
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: fedc9aebb4d57e258370179bbf820abdc8978940
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="walkthrough-using-the-virtual-user-activity-chart-to-isolate-issues"></a>Návod: Izolace problémů pomocí graf aktivity virtuálního uživatele

V tomto návodu se dozvíte, jak izolovat chybách, ke kterým došlo k chybě pro jednotlivé virtuální uživatele, které byly spuštěny zátěžového testu pomocí grafu aktivity virtuálního uživatele.

 Grafu aktivity virtuálního uživatele umožňuje vizualizace aktivity virtuálních uživatelů, který je přidružen zátěžový test. Každý řádek v tabulce představuje jednotlivých virtuálních uživatelů. Přesně co každý virtuálních uživatelů se provádí během testu ukazuje grafu aktivity virtuálního uživatele. To umožňuje izolovat problémy s výkonem pomocí zobrazení vzory aktivity uživatelů, vzory zátěže, korelovat testy selhání nebo pomalé a najdete v části požadavky, které ostatní aktivity virtuálních uživatelů. Grafu aktivity virtuálního uživatele je k dispozici až po zatížení po dokončení spuštění.

 V tomto návodu dokončí následující úkoly:

-   Naučte se používat tyto nástroje spojené s virtuální graf aktivity uživatele:

    -   Použití **zvětšení časové období** nástroj pro určení za určité časové období v grafu, který chcete analyzovat.

    -   Použití **podrobnosti legendy** panelu a **filtrování výsledků** panel použijte filtrování v grafu, který vám pomůže určit problémy.

-   Pomocí grafu aktivity virtuálního uživatele k analýze chybu, ke které došlo k chybě pro konkrétní virtuální uživatele a zobrazit podrobnosti o chybě problematické typu.

 Další informace najdete v tématu [analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md).

## <a name="prerequisites"></a>Požadavky

-   Visual Studio Enterprise

-   Provedení těchto postupů:

    -   [Zaznamenávejte a spuštění testu výkonnosti webu](http://msdn.microsoft.com/en-us/bd0a82fd-cec0-4861-bc09-e1b0b2d258ef).

    -   [Vytvoření a spuštění zátěžového testu](http://msdn.microsoft.com/en-us/7041cbcf-9ab1-4579-98ff-8f296aeaded4)

## <a name="open-the-colorwebapp-solution-created-in-the-previous-walkthroughs"></a>Otevřete řešení ColorWebApp vytvořené v předchozí návody

### <a name="open-the-solution"></a>Otevřete řešení

1.  Spuštění sady Visual Studio.

2.  Otevřete ColorWebApp řešení, které obsahuje LoadTest1.loadtest. Tato zatížení testovací výsledky z provádění kroků v tři názorné postupy, které jsou uvedené na začátku tohoto tématu v části předpoklady.

     Příklady zbývajících kroků v tomto návodu předpokládají webovou aplikaci s názvem ColorWebApp testu výkonnosti webu s názvem ColorWebAppTest.webtest a s názvem LoadTest1.loadtest zátěžový test.

## <a name="run-the-load-test"></a>Spuštění zátěžového testu
 Spusťte test zatížení ke shromažďování dat aktivity virtuálního uživatele.

### <a name="run-the-load-test-to-collect-virtual-user-activity-data"></a>Spusťte zátěžový test ke shromažďování dat aktivity virtuálního uživatele

-   Vyberte v editoru zátěžových testů **spustit** tlačítka na panelu nástrojů. LoadTest1 se spustí.

## <a name="isolate-issues-in-the-virtual-user-activity-chart"></a>Izolovat problémy v grafu aktivity virtuálního uživatele

Po spuštění zátěžového testu a shromažďují data aktivit virtuálních uživatelů, můžete zobrazit data ve výsledcích zátěžového testu pomocí zatížení testování analyzátor podrobnosti zobrazit v grafu aktivity virtuálního uživatele. Kromě toho můžete grafu aktivity virtuálního uživatele lze izolovat problémy s výkonem v zátěžovém testu.

### <a name="to-use-the-virtual-user-activity-chart-in-your-load-test-results"></a>Chcete-li použít virtuální graf aktivity uživatele ve vaší výsledcích zátěžového testu

1.  Po zatížení po dokončení testu spuštěna, souhrnná stránka výsledků zátěžových testů se zobrazí v analyzátoru načíst testování. Vyberte **grafy** tlačítka na panelu nástrojů.

     Zobrazí se zobrazení grafů.

2.  Na **doba odezvy stránky** graf, klikněte pravým tlačítkem na téměř jednu z ikon porušení prahové hodnoty a vyberte **přejít k podrobnostem uživatele**.

    > [!NOTE]
    > Můžete použít **podrobnosti** tlačítka na panelu nástrojů editoru zátěžových testů příliš otevřete grafu aktivity uživatelů. Ale pokud používáte **přejít k podrobnostem uživatele** možnost grafu aktivity virtuálního uživatele budou automaticky přibližte část test, který jste klikli pravým na v grafu.

     Zobrazení podrobností se zobrazí s **graf aktivity virtuálního uživatele** zaměřené na toto časové období, kdy došlo k překročení mezních hodnot.

     Na ose y představují vodorovné pozemků jednotlivých virtuálních uživatelů. Osy x zobrazí časovou osu pro zátěžový test, spustit.

3.  V **zvětšení časové období** nástroj níže **graf aktivity virtuálního uživatele**, upravte vlevo a vpravo posuvníky, dokud jsou obě zavřít na ikonu porušení prahové hodnoty. Tato operace změní ose v **graf aktivity virtuálního uživatele**

4.  V **podrobnosti legendy**, zaškrtněte políčko pro **(zvýrazněte chyby)**. Všimněte si, že je označený virtuální uživatele, který způsobil porušení prahové hodnoty.

5.  V **filtrování výsledků** panelu, zrušte zaškrtnutí políček u **zobrazit úspěšné výsledky** a **HttpError** , ale ponechte **ValidationRuleError**zaškrtnuté políčko.

     **Graf aktivity virtuálního uživatele** zobrazí pouze virtuálních uživatelů, které spotřebovávají více než 3 sekund na stránce Red.aspx podle specifikace porušení prahové hodnoty, které jsou nakonfigurované v předchozího návodu.

6.  Umístěte ukazatel myši nad vodorovném řádku, který představuje virtuální uživatele došlo k chybě ověření pravidla pro porušení prahové hodnoty.

7.  Popis tlačítka se zobrazí následující informace:

    -   **Id uživatele**

    -   **Scénář**

    -   **Test**

    -   **Výsledek**

    -   **Sítě**

    -   **Čas spuštění**

    -   **Doba trvání**

    -   **Agent**

    -   **Test protokolu**

8.  Všimněte si, že **testovací protokolu** je odkaz. Vyberte **testovací protokolu** odkaz.

9. Testu výkonnosti webu ColorWebTest, který je přidružen protokol otevře prohlížeč pro výsledky testů výkonnosti webu. Díky tomu můžete izolovat, kde došlo k překročení mezních hodnot.

     Různá nastavení můžete použít v obou **podrobnosti legendy** a **filtrování výsledků** panely k pomůže zjistit problémy s výkonem a chyby v zátěžových testech. Experiment s těmito nastaveními a **zvětšení časové období** nástroj, který najdete v části jak jsou poskytovány data virtuálních uživatelů **graf aktivity virtuálního uživatele**.

## <a name="see-also"></a>Viz také

- [Analýza aktivity virtuálních uživatelů v podrobném zobrazení](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)
- [Kontrolery testů a testovací agenti](configure-test-agents-and-controllers-for-load-tests.md)
- [Postupy: vytvoření nastavení testu pro distribuovaný zátěžový Test](../test/how-to-create-a-test-setting-for-a-distributed-load-test.md)
- [Instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md)
- [Shromažďování diagnostických informací s použitím nastavení testu](../test/collect-diagnostic-information-using-test-settings.md)