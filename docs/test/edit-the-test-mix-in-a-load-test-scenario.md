---
title: "Poměr testů pro scénáře zátěžového testu v sadě Visual Studio | Microsoft Docs"
ms.date: 10/19/2016
ms.topic: article
helpviewer_keywords:
- load tests, adding tests
- test mix
- load tests, test mix
- load tests, removing tests
ms.assetid: 303e1d70-5d98-424a-b51e-e0898e16d3f8
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-ide-test
ms.openlocfilehash: 20437bf88d62943d6f0dbf3d9df320836c5e9e36
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/19/2018
---
# <a name="edit-the-test-mix-to-specify-which-web-performance-unit-and-coded-ui-tests-to-include-in-a-load-test-scenario"></a>Úpravy poměru testů k určení, které výkonnosti webu, částí a programové testy uživatelského rozhraní mají být zahrnuty scénáře zátěžového testu

*Kombinace testů* scénáře je kombinací výběru webové výkonu a jednotka testy, které jsou obsažené v tomto scénáři a distribuci tyto testy ve scénáři. Distribuce je nastavení, které můžete zadat pro pravděpodobnost, že konkrétní test bude vybrán ve virtuálních uživatelů během spuštění testu zatížení.

 Po přidání sadu testů pro zátěžový test, *kombinace testů* funguje jako jiný kombinovat možnosti. Virtuální uživatel náhodně vybere testu podle pravděpodobnost, že jste zadali v kombinaci. Například pokud máte dva testy, každý 50 procent v kombinaci, nový virtuální uživatel rozhodne ke spuštění prvního testu přibližně poloviny doby. V kombinaci 50/50 Pokud jeden test je dlouhá a jiné short, pochází další zatížení z dlouho test.

 Po přidání testy s různými, můžete je odebrat. Pomocí ovládacího prvku kombinace můžete určit také distribuci poměru testů. Ovládací prvek kombinace umožňuje snadno nastavit distribuce testů ve scénáři.

> [!NOTE]
> Distribuce je míra pravděpodobnosti, že konkrétní test bude vybrán ve virtuálních uživatelů během spuštění testu zatížení. Distribuce je vyjádřený v procentech. Proto součet čísel distribuce pro všechny testy, které jsou obsaženy ve scénáři je 100. Například pokud scénář obsahuje pouze jeden test, distribuce pro tento test je 100 procent.

## <a name="add-new-tests-to-a-test-mix-in-an-existing-scenario"></a>Přidat nové testů do poměru testů ve scénáři s existující

Když vytvoříte nový scénář pomocí Průvodce novým testování zatížení, můžete zadat webových testů výkonu a jednotky pro přidání do nové scénáře poměru testů.

Pomocí editoru zátěžových testů, můžete přidat další výkon webové a testování částí pro text směs scénáři.

![Přidání testu do existující zátěžový test](../test/media/ltest_addingtests.png "LTest_AddingTests")

### <a name="to-add-more-tests-to-an-existing-scenario"></a>Chcete-li přidat další testy se scénářem existující

1.  Otevřete zátěžový test.

2.  V editoru zátěžových testů, klikněte pravým tlačítkem na existující scénář a pak zvolte **přidat testy**.

     **Přidat testy** se zobrazí dialogové okno. Všechny webové výkon, částí a programové testy uživatelského rozhraní ve vašem řešení, které ještě nejsou ve vašem scénáři je možné přidat do scénáře.

3.  V **dostupné testy** podokně vyberte výkonu webové, částí a programové testy uživatelského rozhraní, které chcete přidat. Zvolte se šipkou doprava přidejte testy, abyste **vybrané testy** podokně.

4.  Po dokončení přidávání testy, vyberte **OK**.

     Testy jsou přidány do poměru testů. Nová distribuce je automaticky přiřadit k testy v poměru testů.

5.  (Volitelné) Upravte ovládacího prvku kombinace určení distribučních testu. Další informace najdete v tématu [o kombinaci řídicí](../test/edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario.md).

##  <a name="EditingTestMixRemoveTest"></a> Odebírání testů z scénáři
 ![Odebrání testu z existující zátěžový test](../test/media/ltest_removetest.png "LTest_RemoveTest")

### <a name="to-remove-tests-from-a-scenario"></a>K odebrání scénáři testů

1.  Otevřete zátěžový test.

2.  V načíst testování editoru ve stromové struktuře zatížení testu, klikněte pravým tlačítkem na scénář, ze kterého chcete odebrat test a vyberte **úpravy kombinace testů**. **Úpravy poměru testů** se zobrazí dialogové okno.

3.  Vyberte Web výkonu, jednotky nebo programového testu uživatelského rozhraní v mřížce a zvolte **odebrat**.

    > [!NOTE]
    > Po odebrání test upravte poměru testů do upřednostňovaných distribučních.

4.  Po dokončení odstraňování testy, vyberte **OK**.

##  <a name="EditingTestMixAboutMixControl"></a> O ovládacím prvku kombinaci
 Ovládací prvek kombinace umožňuje upravit procento zatížení, která se distribuuje mezi testy, typu prohlížeče nebo typy sítí ve scénáři zátěžového testu. Procentní hodnoty můžete upravit posunutím jezdce. Úprava kombinace pro testy určuje pravděpodobnost virtuální uživatel, který se spustil konkrétní test ve scénáři zátěžového testu.

 Při přesunutí jezdce procento hodnoty dostupné všechny položky změnit. Pokud máte více než dvě položky, velikost, můžete přidat nebo odebrat je rovnoměrně rozdělené mezi další položky. Je možné toto chování potlačit. Pokud vyberete políčko ve sloupci zámek pro konkrétní položky, zamknete tak zadaný procentuální hodnotu pro tuto položku. Pak, když přesouváte jezdce, velikost, můžete přidat nebo odebrat se použije pouze na všechny zbývající odemknout položky.

 **Distribuovat** tlačítko se používá k rozdělení procenta rovnoměrně mezi všechny položky. Například pokud máte tři položky, výběr **distribuovat** nastaví procentní hodnoty 34, 33 a 33.

> [!WARNING]
>  **Distribuovat** tlačítko přepíše všechny položky, které jsou zamčené.

 Je také možné zadejte procentní hodnoty přímo do  **%**  sloupec místo pomocí posuvníků. Pokud zadáte hodnotu v procentech přímo, nebude automaticky upravte ostatní položky.

> [!NOTE]
>  Posuvníků jsou zakázané, když celkové nepřidá až o 100 %, nebo při procentní hodnoty do  **%**  sloupce jsou desetinných míst.

 Když ručně zadáte procentní hodnoty, měli byste si ověřit, že součet všech položek je 100 %. Při ukládání kombinaci, pokud součet není 100 %, vyzve tak, aby přijímal procentní hodnoty, jako jsou, nebo se vrátit a jejich nastavení. Pokud zvolíte možnost je přijmout, protože se jedná o, bude poměrně rozložen na 100 %.  Například pokud máte dvě položky a je ručně nastavte na 80 % a 40 %, první položka bude nastavena pro 66.67 % (80 dělený 120) a druhá položka bude nastavena pro 33,33 % (40 dělený 120).

## <a name="see-also"></a>Viz také

- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)