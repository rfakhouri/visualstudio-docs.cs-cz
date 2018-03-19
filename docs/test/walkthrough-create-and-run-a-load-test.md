---
title: "Vytvoření a spuštění zátěžového testu v sadě Visual Studio | Microsoft Docs"
ms.date: 10/01/2016
ms.topic: article
helpviewer_keywords:
- unit tests, in load tests
- unit tests, load test walkthrough
- load tests, walkthrough
ms.assetid: bbf075a5-96d5-48ed-a03c-330f0fc04748
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 53bde20393f5acd55295bf106cb35f6f09e68bf3
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="walkthrough-create-and-run-a-load-test-that-contains-unit-tests"></a>Návod: Vytvoření a spuštění zátěžového testu, který obsahuje testování částí

V tomto návodu vytvoříte zátěžový test, který obsahuje testování částí.

Tento návod provede vás vytvořením a poté spuštění zátěžového testu pomocí Visual Studio Enterprise. Zátěžový test je kontejner testy výkonnosti webu a testování částí. Zátěžové testy vytvoříte pomocí nového Průvodce testovací načíst.

Zátěžový test také poskytuje mnoho vlastností spuštění, které je možné upravit ke generování simulace požadované zatížení. V tomto návodu použijete k přidání testů částí do testu zatížení načíst testování Průvodce novým.

V tomto návodu dokončí následující úkoly:

-   Vytvořte zátěžový test, který používá testování částí.

-   Změňte některá nastavení testu zatížení.

-   Spuštění zátěžového testu.

-   Proveďte kroky v [návod: vytváření a spuštěné testování částí pro spravovaný kód](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md) vytvořit jednoduché C# knihovny tříd obsahující webové výkon a zatížení testování projektu pomocí některé testy jednotek v ní.

## <a name="create-a-load-test-containing-unit-tests-using-the-new-load-test-wizard"></a>Vytvořte zátěžový Test obsahující testů jednotek pomocí nového Průvodce zátěžovým testem

### <a name="to-start-the-new-load-test-wizard"></a>Spuštění nového Průvodce zátěžovým testem

1.  Otevřete řešení Bank, který jste vytvořili v [návod: vytváření a spuštěné testování částí pro spravovaný kód](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md).

2.  V **Průzkumníku řešení**, otevřete místní nabídku pro uzel řešení Bank, zvolte **přidat**a potom zvolte **nový projekt**.

     Zobrazí se dialogové okno Přidat nový projekt.

3.  V dialogovém okně Přidat nový projekt rozbalte **Visual C#** a zvolte **Test**. V seznamu šablon vyberte **výkonu webu a zatížení testovacího projektu** a v **název** zadejte `BankLoadTest`. Zvolte **OK**.

     BankLoadTest webového výkon a zatížení testovacího projektu je přidán do řešení.

4.  Otevřete místní nabídky pro nové výkonu webu BankLoadTest a zatížení testování projektu, zvolte **přidat**a potom zvolte **načíst testování**.

5.  **Nového Průvodce zátěžovým testem** spustí.

6.  **Úvodní** stránky **nového Průvodce zátěžovým testem** je první stránka.

7.  Zvolte **Další**.

### <a name="to-edit-settings-for-load-test-scenario"></a>Chcete-li upravit nastavení pro scénáře zátěžového testu

1.  V **zadejte název pro scénáře zátěžového testu** textového pole, typ **ScenarioSample**.

     A *scénář* mechanismus seskupení. Skládá se ze sady testů a vlastnosti pro spuštění tyto testy zatížení.

2.  Nastavte **čas profil Považujte** k `Use normal distribution centered on recorded think times`. Dob uvažování představují čas, uživatel by všechny webové stránky před přechodem další stránku.

1.  Zvolte **Další** po dokončení.

### <a name="to-edit-load-pattern-setting-for-test-scenario"></a>Chcete-li upravit nastavení vzor zatížení pro test scénář

1.  Zvolte **krok zatížení**.

    > [!NOTE]
    > Můžete vybrat z dva typy vzorů zatížení: Konstanta a krok. Každý typ má jeho funkce v zátěžové testování, ale pro účely tohoto návodu zvolte **krok zatížení**.

2.  Nastavit **spustit počet uživatelů** 10 uživatelům.

3.  Nastavit **krok trvání** na 10 sekund.

4.  Nastavit **krok počet uživatelů** na uživatele nebo kroku 10.

5.  Nastavit **maximální počet uživatelů** až 100 uživatelů.

6.  Zvolte **Další**.

### <a name="to-select-test-mix-model-for-the-scenario"></a>Vyberte model kombinace testů pro scénář

1.  V části Jak modelovat poměru testů, vyberte **na základě celkového počtu testovací**.

2.  Zvolte **Další**.

### <a name="to-add-unit-tests-to-the-scenario"></a>Chcete-li přidat do scénáře testování částí

1.  Dalším krokem je **přidat testy na zatížení scénář otestovat a upravit poměru testů**.

2.  Zvolte **přidat** vyberte testy.

3.  Zvolte testování částí CreditTest uvedené v **dostupné testy** podokno, které jsou uvedeny všechny testy výkonnosti webu a testování částí v výkonu webu a zatížení testovacího projektu.

4.  Vyberte šipku přidat test jednotky CreditTest **vybrané testy** podokně.

5.  Zopakujte kroky 3 a 4 pro DebitTest a FreezeAccountTest testů jednotek.

6.  Až dokončíte přidávání testů tři jednotky, zvolte **OK**.

     Máte k ruce poměru testů.

7.  Nastavte posuvník pod distribuce pro CreditTest mírně práva k rozdělení testovací upravit. Všimněte si, že ostatní jezdce doleva automaticky přesunout tak, aby distribuce zůstává na 100 %.

8.  Zvolte **Další**.

### <a name="to-select-network-mix-for-test-scenario"></a>Vyberte kombinace sítí pro testovací scénář

1.  Vyberte typ připojení LAN pro přidání do poměr šířky pásma sítě.

     Můžete přidat další typy sítí. Upravte test distribuci a vyvážení pomocí posuvníků.

2.  Zvolte **Další**.

### <a name="to-specify-computers-to-monitor-with-counter-sets-during-load-test-run"></a>Chcete-li určit počítače monitorovat pomocí sady čítačů během spuštění zátěžového testu

1.  Zvolte **Další**.

     Další informace o sad čítačů najdete v tématu [zadání nastaví čítačů a mezních pravidel pro počítače v zátěžovém testu](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md).

### <a name="to-edit-run-setting-for-load-test"></a>Chcete-li upravit nastavení spouštění pro zátěžový test

1.  Vyberte **doba trvání testu zatížení** a poté nastavte **spustit trvání** 2 minut za účelem *kouře testovací* zátěžový test.

     Při sestavování zátěžové testy, je vhodné ověřit, že je vše správně nakonfigurovaná a spuštěná podle očekávání spuštěním krátký, světla zátěžový test. Tento proces se označuje jako *orientační testování*.

2.  Zvolte **Dokončit**. Zátěžový test je otevřen v **editoru zátěžových testů**.

## <a name="running-the-load-test"></a>Spuštění zátěžového testu
 Jakmile vytvoříte zátěžový test, spusťte ji chcete zobrazit, jak aplikaci pro bankovní reagují na simulace zatížení. Je spuštěn zátěžový test, uvidíte **načíst testování analyzátor** okno.

### <a name="to-run-the-load-test"></a>Ke spuštění zátěžového testu

1.  S otevřít v zátěžovém testu **editoru zátěžových testů**, zvolte zeleným **spustit Test** tlačítka na panelu nástrojů. Zátěžový test se spustí.

2.  Pokud vaše testovací simulace překračuje všechny prahové hodnoty, ikony se zobrazují v uzlu stromu ovládací prvek udávajících porušení prahové hodnoty. Chyby mít červené kolečko překrytí, upozornění mít žlutý trojúhelník překrytí. Můžete nalézt čítač překročení této mezní hodnoty a graf přetažením ikonu do grafu. Můžete k tomu je spuštěn test.

## <a name="see-also"></a>Viz také

- [Úpravy kombinace testů určující, které testy mají být zahrnuty scénáře zátěžového testu](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md)
- [Určení typů virtuálních sítí](../test/specify-virtual-network-types-in-a-load-test-scenario.md)
- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)
- [Úpravy vzorů zatížení pro modelování aktivit virtuálních uživatelů](../test/edit-load-patterns-to-model-virtual-user-activities.md)
- [Úpravy modelů kombinací určení pravděpodobnosti spuštění testu virtuálním uživatelem](../test/edit-test-mix-models-to-specify-the-probability-of-a-virtual-user-running-a-test.md)