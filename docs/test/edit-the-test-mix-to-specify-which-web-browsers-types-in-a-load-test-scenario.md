---
title: Kombinace testů prohlížeče pro zatížení testování v sadě Visual Studio
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, web browser types
- load tests, scenarios
- load tests, adding browsers
- load tests, removing browsers
ms.assetid: 47f981d9-3038-45cc-a486-82b9daf9a9a1
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 121be2e1eb608bde001422282c4387bb5a7290e1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31967954"
---
# <a name="edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario"></a>Úpravy kombinace testů určit, které webové prohlížeče typy v zatížení testovací scénář

*Prohlížeče kombinace* poskytuje způsob k simulaci zatížení více reálně ve scénáři zátěžového testu. Zatížení je generována pomocí heterogenní směs webových prohlížečů místo jednom webovém prohlížeči. Můžete vytvořit blíže aproximace webových prohlížečů, které budou použity s vašimi aplikacemi.

 Určuje kombinaci prohlížeče pravděpodobnost virtuální uživatel, který se spustil konkrétní typ webového prohlížeče ve scénáři zátěžového testu. Když vytvoříte zátěžový test, můžete k simulaci, že je zatížení vygenerováno prostřednictvím více než jeden webového prohlížeče. Když přidáte typ webové prohlížeče s různými ze sady webových prohlížečů, které jsou k dispozici, sadu přidružené hlavičky pro vybrané webový prohlížeč se přidá na každý požadavek HTTP, který je odeslaný testu výkonnosti webu.

 Kombinace prohlížeče funguje jako další možnosti kombinaci. Typ webové prohlížeče je náhodně přidružený virtuálních uživatelů, založené na kombinaci prohlížeče. Spuštění testů tohoto uživatele na konkrétní webový prohlížeč, podle pravděpodobnost, že jste zadali v kombinaci.

 Po zadání kombinaci prohlížeče, abyste později přidávat a odebírat typy webových prohlížečů s různými. Distribuce prohlížeče kombinace můžete určit také pomocí ovládacího prvku kombinaci. Ovládací prvek kombinace umožňuje snadno nastavit rozložení prohlížečů ve scénáři.

## <a name="adding-new-browsers-to-a-scenario"></a>Přidávání nových prohlížečů pro určitý scénář

### <a name="to-add-new-browsers-to-a-scenario"></a>Chcete-li přidat nový prohlížečů pro určitý scénář

1.  Během procesu určení kombinace prohlížeče pro scénáře vyberte **přidat**.

     Nový záznam prohlížeče se přidá k mřížce.

    > [!NOTE]
    > K zobrazení **upravit kombinace prohlížeče** dialogové okno pole, klikněte pravým tlačítkem na existující scénář a pak zvolte **upravit kombinace prohlížeče**.

2.  V **typ prohlížeče** sloupce, zvolte šipku nové položky a typu požadovaného prohlížeče.

3.  (Volitelné) Upravte ovládacího prvku kombinace určení distribučních testu.

4.  Po dokončení přidávání prohlížečů, zvolte **OK**.

##  <a name="EditingTestMixSpecifyBrowserRemovingBrowserTypes"></a> Odebírání prohlížečů z scénáři

### <a name="to-remove-browsers-from-a-scenario"></a>K odebrání scénáři prohlížečů

1.  Otevřete zátěžový test.

2.  Klikněte pravým tlačítkem na scénář, ze kterého chcete odebrat prohlížeče a pak zvolte **upravit kombinace prohlížeče**.

     **Upravit kombinace prohlížeče** se zobrazí dialogové okno.

3.  Vyberte prohlížeče v mřížce a potom zvolte **odebrat**.

4.  (Volitelné) Upravte ovládacího prvku kombinace určení distribučních testu.

5.  Po dokončení odebírání prohlížečů, zvolte **OK**.

## <a name="about-the-mix-control"></a>O ovládacím prvku kombinaci

 Ovládací prvek kombinace umožňuje upravit procento zatížení, která se distribuuje mezi testy, typu prohlížeče nebo typy sítí ve scénáři zátěžového testu. Procentní hodnoty můžete upravit posunutím jezdce. Úprava kombinace pro typy prohlížeče určuje pravděpodobnost systémem typ konkrétní prohlížeče ve scénáři zátěžového testu virtuálním uživatelem.

 Při přesunutí jezdce procento hodnoty dostupné všechny položky změnit. Pokud máte více než dvě položky, velikost, můžete přidat nebo odebrat je rovnoměrně rozdělené mezi další položky. Je možné toto chování potlačit. Pokud vyberete políčko ve sloupci zámek pro konkrétní položky, zamknete tak zadaný procentuální hodnotu pro tuto položku. Pak, když přesouváte jezdce, velikost, můžete přidat nebo odebrat se použije pouze na všechny zbývající odemknout položky.

 **Distribuovat** tlačítko se používá k přidělení procentní hodnoty rovnoměrně mezi všechny položky. Například pokud máte tři položky, výběr **distribuovat** nastaví procentní hodnoty 34, 33 a 33.

> [!WARNING]
> **Distribuovat** tlačítko přepíše všechny položky, které jsou zamčené.

 Je také možné zadejte procentní hodnoty přímo do **%** sloupec místo pomocí posuvníků. Pokud zadáte hodnotu v procentech přímo, nebude automaticky upravte ostatní položky.

> [!NOTE]
> Posuvníků jsou zakázané, když celkové nepřidá až o 100 %, nebo při procentní hodnoty do **%** sloupce jsou desetinných míst.

 Když ručně zadáte procentní hodnoty, měli byste si ověřit, že součet všech položek je 100 %. Při ukládání kombinaci, pokud součet není 100 %, vyzve tak, aby přijímal procentní hodnoty, jako jsou, nebo se vrátit a jejich nastavení. Pokud zvolíte možnost je přijmout, protože se jedná o, bude poměrně rozložen na 100 %.  Například pokud máte dvě položky a je ručně nastavte na 80 % a 40 %, první položka bude nastavena pro 66.67 % (80 dělený 120) a druhá položka bude nastavena pro 33,33 % (40 dělený 120).

## <a name="see-also"></a>Viz také

- [Úpravy scénářů zátěžových testů](../test/edit-load-test-scenarios.md)