---
title: Úpravy programových testů uživatelského rozhraní
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
f1_keywords:
- vs.codedUItest.testeditor
helpviewer_keywords:
- coded UI test, Coded UI Test Editor
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 88c42b710b08ca7dae8d779da3d6e093179ddca6
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/01/2018
ms.locfileid: "34692366"
---
# <a name="edit-coded-ui-tests-using-the-coded-ui-test-editor"></a>Úpravy programových testů UI pomocí editoru programových testů uživatelského rozhraní

Editor programového testu uživatelského rozhraní lze snadno upravit programových testů uživatelského rozhraní. Pomocí editoru testování uživatelského rozhraní programového, můžete vyhledat, zobrazit a upravit vlastnosti testovací metody a akcí uživatelského rozhraní. Kromě toho můžete použít ovládací prvek mapy uživatelského rozhraní zobrazení a jejich odpovídající ovládacích prvcích pro úpravy.

**Požadavky**

- Visual Studio Enterprise
- Programového testu součást uživatelského rozhraní

## <a name="features-of-the-coded-ui-test-editor"></a>Funkce z editoru programových testů UI

Pomocí editoru testování uživatelského rozhraní programového je rychlejší a efektivnější než úpravy kódu v vaše programové metody testu uživatelského rozhraní pomocí editoru kódu. S programového uživatelského rozhraní editoru testu, nástrojů a v místní nabídky můžete použít k rychlému vyhledání a upravte hodnoty vlastností, které jsou spojené s akcí uživatelského rozhraní a ovládací prvky. Například programového uživatelského rozhraní editoru testu na panelu nástrojů můžete provést následující příkazy:

![Editor testu uživatelského rozhraní](../test/media/uitesteditor.png)

1. [Najít](../ide/finding-and-replacing-text.md) pomáhá při hledání akcí uživatelského rozhraní a ovládací prvky.

2. **Odstranit** odebere nežádoucích akcí uživatelského rozhraní.

3. **Přejmenujte** změní názvy pro testovací metody a ovládací prvky.

4. **Vlastnosti** otevře **vlastnosti** okna pro vybranou položku.

5. **Rozdělení do nové metody** umožňuje rozčlenění moduly akcí uživatelského rozhraní.

6. **Přesunout kód** přidá vlastní kód pro zkušební metody.

7. **Vložit zpoždění před** přidá pozastavení před akci uživatelského rozhraní, zadaný v milisekundách.

8. **Vyhledejte kontrolní mechanismus uživatelského rozhraní** identifikuje umístění ovládacího prvku v uživatelském rozhraní aplikace v rámci testu.

9. **Vyhledejte všechny** ověříte pomáhá řídit vlastnost a významné změny do aplikace ovládacích prvků.

Když otevřete *UIMap.uitest* souboru spojit s vaší programového testu uživatelského rozhraní v nástroji otevře programových testů uživatelského rozhraní **programového Editor testů uživatelského rozhraní**. Následující postupy popisují, jak můžete najít a upravit testovací metod a vlastností akce uživatelského rozhraní a ovládacích prvků pomocí nástrojů editoru a místní nabídky.

## <a name="open-a-coded-ui-test"></a>Otevřete programového testu uživatelského rozhraní

Můžete zobrazit a upravit vaše Visual C# a na základě jazyka Visual Basic programové uživatelského rozhraní testování pomocí **programového Editor testů uživatelského rozhraní**.

![Kontextové nabídky Upravit s programového Tvůrce testu uživatelského rozhraní](../test/media/editcodeduitest.png)

V **Průzkumníku řešení**, otevřete místní nabídku pro *UIMap.uitest* a zvolte **otevřete**. Programového testu uživatelského rozhraní se zobrazí v **programového Editor testů uživatelského rozhraní**. Nyní můžete zobrazit a upravit zaznamenaná metody, akce a odpovídající ovládacích prvků v programových testů uživatelského rozhraní.

> [!TIP]
> Když vyberete akci uživatelského rozhraní, který je umístěný v metodě v **akcí uživatelského rozhraní** zvýrazní podokně odpovídající ovládacího prvku. Můžete také upravit vlastnosti ovládacích prvků nebo akci uživatelského rozhraní.

## <a name="modify-ui-action-and-control-properties"></a>Změnit vlastnosti akce a ovládacích prvků uživatelského rozhraní

Pomocí editoru testování uživatelského rozhraní programového můžete rychle vyhledat a zobrazit všechny akce uživatelského rozhraní v zkušební metody. Když vyberete akci uživatelského rozhraní v editoru, zvýrazní se automaticky odpovídající ovládacího prvku. Podobně pokud vyberete ovládacího prvku, jsou vyznačené přidružené akce uživatelského rozhraní. Když vyberete akci uživatelského rozhraní nebo ovládací prvek, je pak snadno okno Vlastnosti použít k úpravě vlastností, které odpovídají s ním.

![Vlastností akce uživatelského rozhraní](../test/media/codeduiedituiaction.png)

Postup úpravy vlastností akce uživatelského rozhraní v **akci uživatelského rozhraní** podokně rozbalte testovací metody, která obsahuje akci uživatelského rozhraní, kterou chcete upravit vlastnosti, vyberte akci uživatelského rozhraní a potom upravte vlastnosti pomocí okna Vlastnosti.

Například pokud server není k dispozici, a máte akci uživatelského rozhraní související s webovým prohlížečem, který stavy **přejděte na webovou stránku sehttp://Contoso1/default.aspx'**, můžete změnit adresu URL `'http://Contoso2/default.aspx'`.

![Vlastnosti ovládacích prvků](../test/media/codeduitestcontrolprop.png)

Úprava vlastností ovládacího prvku se provádí stejným způsobem jako akce uživatelského rozhraní. V **mapy ovládacího prvku uživatelského rozhraní** podokně vyberte ovládací prvek, který chcete upravit a upravit její vlastnosti pomocí okna Vlastnosti.

Například může vývojář změnili **(ID)** vlastnost u prvku tlačítko ve zdrojovém kódu aplikace testuje z "idSubmit" na "idLogin." Pomocí **(ID)** vlastnost změnit v aplikaci, nebude možné najít ovládací prvek tlačítko programového testu uživatelského rozhraní a se nezdaří. V takovém případě můžete otevřít nástroj tester **vlastností vyhledávání** kolekce a změňte **Id** vlastnost tak, aby odpovídala nové hodnoty, které vývojář použitou v aplikaci. Zkušební zařízení také můžete změnit **popisný název** hodnota vlastnosti z "Odeslat" na "Přihlášení". Tím, že tato změna, přidružené akce uživatelského rozhraní v programových uživatelského rozhraní editoru testu je aktualizována z "Vyberte"Odeslat"button" na "Vyberte"Přihlášení"tlačítko."

Po dokončení úprav, uložte změny do souboru UIMap.Designer výběrem **Uložit** na panelu nástrojů Visual Studio.

### <a name="tips"></a>Tipy

- Pokud **vlastnosti** se nezobrazí okno, stiskněte a podržte **Alt** a stiskněte klávesu **Enter**, nebo stiskněte klávesu **F4**.

- Chcete-li vrátit zpět provedené změny vlastnosti, vyberte **vrátit zpět** z **upravit** nabídky, nebo klikněte na tlačítko **Ctrl**+**Z**.

- Můžete použít **najít** tlačítka na panelu nástrojů editoru programového testu uživatelského rozhraní v sadě Visual Studio otevřete nástroj Najít a nahradit. Potom můžete najít ovládací prvek najít akci uživatelského rozhraní v editoru programového testu uživatelského rozhraní. Například můžete zkusit najít "klikněte na tlačítko"Přihlášení"." To může být užitečné v testech velké. Nahrazení funkce nelze použít v nástroji Najít a nahradit v programových uživatelského rozhraní editoru testu. Další informace najdete v tématu najít řídit ve [hledání a nahrazování textu](../ide/finding-and-replacing-text.md).

- V některých případech může být obtížné vizualizovat, kde se nachází ovládací prvky v uživatelském rozhraní aplikace v rámci testu. Jednou z možností editoru programových testů uživatelského rozhraní je, můžete vybrat ovládacího prvku uvedené v mapy ovládacího prvku uživatelského rozhraní a zobrazte její umístění v aplikaci v rámci testu. Další informace najdete v tématu [vyhledání prvku uživatelského rozhraní v aplikaci testovaného](#CodedUITestEditor_LocateUIControl) najít další níže v tomto článku.

- Může být potřeba rozbalte kontejner ovládací prvek, který obsahuje ovládací prvek, který chcete upravit. Další informace najdete v tématu [umísťování ovládacího prvku a jeho následníky](#CodedUITestEditor_LocateDecendants) najít další níže v tomto článku.

## <a name="delete-unwanted-ui-actions"></a>Odstranění nežádoucích akcí uživatelského rozhraní

Můžete snadno odebrat nežádoucích akcí uživatelského rozhraní v programového testu uživatelského rozhraní.

![Odstranit akci uživatelského rozhraní](../test/media/codeduideleteuiaction.png)

V **akci uživatelského rozhraní** podokně rozbalte testovací metody, která obsahuje akci uživatelského rozhraní, které chcete odstranit. Otevřete místní nabídku pro akci uživatelského rozhraní a zvolte **odstranit**.

## <a name="split-a-test-method-into-two-separate-methods"></a>Test metody rozdělit na dvě samostatné metody

Je možné rozdělit testovací metoda Upřesnit a rozčlenění moduly akcí uživatelského rozhraní. Například svůj test může mít jeden testovací metodu s akcí uživatelského rozhraní v ovládacích prvcích dvě kontejneru. Akce uživatelského rozhraní může být lépe modulární v dvě metody, které odpovídají s jeden kontejner.

![Rozdělení metody za testu](../test/media/codeduitestsplitmethod1.png)

![Dvou testovacích metody](../test/media/codeduitestsplitmethod2.png)

V **akci uživatelského rozhraní** podokně rozbalte zkušební metody, kterou chcete rozdělit na dvě samostatné metody a vyberte místo, kam chcete nová metoda testovací zahájíte akci uživatelského rozhraní. Buď otevřete místní nabídku pro akci uživatelského rozhraní a zvolte **rozdělit do nové metody**, nebo zvolte **rozdělit do nové metody** tlačítka na panelu nástrojů editoru programových testů UI. Nová metoda testů se zobrazí v podokně akcí uživatelského rozhraní. Obsahuje akcí uživatelského rozhraní od akce, které jste zadali rozdělení.

Po dokončení rozdělení metodu, uložte změny do souboru UIMap.Designer výběrem **Uložit** na panelu nástrojů Visual Studio.

> [!WARNING]
> Pokud jste rozdělení metody, je třeba upravit kód, který volá metodu existující také zavolat metodu nové, které se chystáte vytvořit, pokud stále chcete těchto akcí uživatelského rozhraní, které jsou zahrnuty. Při rozdělování metodu, zobrazí se dialogové okno Microsoft Visual Studio. Ho vás varuje, že je třeba upravit kód, který zavolá metodu existující také zavolat metodu, kterou se chystáte vytvořit nové. Zvolte **Ano**.

### <a name="tips"></a>Tipy

- Chcete-li zrušit rozdělení, zvolte **vrátit zpět** z **upravit** nabídky, nebo klikněte na tlačítko **Ctrl**+**Z**.

- Metoda new můžete přejmenovat. Vyberte v podokně akcí uživatelského rozhraní a zvolte **přejmenovat** tlačítka na panelu nástrojů editoru programových testů UI.

   -nebo-

   Otevřete místní nabídku pro nový test – metoda a zvolte **přejmenovat**.

   Zobrazí se dialogové okno aplikace Microsoft Visual Studio. Ho vás varuje, že je třeba upravit kód, který odkazuje na metodu. Zvolte **Ano**.

## <a name="move-a-test-method-to-the-uimap-file-to-facilitate-customization"></a>Přesunutí testovacího metody do zdroje UIMap souboru usnadňuje přizpůsobení

Pokud zjistíte, že jeden testovací metody v uživatelském rozhraní programového testu vyžaduje vlastní kód, musí přesuňte jej do souboru UIMap.cs nebo UIMap.vb. Váš kód, jinak budou přepsány, vždy, když znovu zkompiluje programového testu uživatelského rozhraní. Pokud přesunete není metodu, vlastní kód, budou přepsány pokaždé, když znovu zkompiluje test.

V **akci uživatelského rozhraní** podokně, vyberte znovu zkompiluje zkušební metody, které chcete přesunout do souboru UIMap.cs nebo UIMap.vb usnadňuje funkce vlastní kód, který nebude přepsána při testovacího kódu. V dalším kroku vyberte **přesunout kódu** tlačítka na panelu nástrojů programového Editor testů uživatelského rozhraní nebo otevřete místní nabídku pro metodu test a zvolte **přesunout kód**. Testovací metoda je odebrána ze souboru UIMap.uitest a v podokně Akce uživatelského rozhraní se již nezobrazí. Upravit soubor test, který jste přesunuli, otevřete UIMap.cs nebo UIMap.vb soubor v Průzkumníku řešení.

Po dokončení přesunu metodu, uložit změny do souboru UIMap.Designer výběrem **Uložit** na panelu nástrojů Visual Studio.

> [!WARNING]
> Po přesunutí metodu, můžete ji pomocí editoru programových testů UI již upravit. Musíte přidat vlastní kód a spravovat jej pomocí Editoru kódu. Když přesouváte metodu, se zobrazí dialogové okno Microsoft Visual Studio. Ho varuje, že metoda přesunou se ze souboru UIMap.uitest UIMap.cs nebo UIMap.vb souboru a že jste už nebude moci upravit metodu pomocí editoru programových testů uživatelského rozhraní. Zvolte **Ano**.

### <a name="tips"></a>Tipy

Chcete-li vrátit zpět přesunutí, vyberte **vrátit zpět** z **upravit** nabídky, nebo klikněte na tlačítko **Ctrl**+**Z**. Nicméně je nutné pak ručně odebrat kód ze souboru UIMap.cs nebo UIMap.vb.

## <a name="locate-a-ui-control-in-the-application-under-test"></a>Vyhledejte v aplikaci testovaného ovládacího prvku uživatelského rozhraní

V některých případech může být obtížné vizualizovat, kde se nachází ovládací prvky v uživatelském rozhraní aplikace v rámci testu. Jednou z možností editoru programových testů uživatelského rozhraní je, můžete vybrat ovládacího prvku uvedené v mapy ovládacího prvku uživatelského rozhraní a zobrazte její umístění v aplikaci v rámci testu. Pomocí **najít kontrolní mechanismus uživatelského rozhraní** funkce na aplikaci testovaného lze také ověřit vyhledávání vlastnost úpravy provedené do ovládacího prvku.

![Vyhledejte kontrolní mechanismus uživatelského rozhraní](../test/media/codeduilocatecontrol.png)

![Ovládací prvek nachází v aplikaci v rámci testu](../test/media/codeduilocatecontrol2.png)

V **mapy ovládacího prvku uživatelského rozhraní** podokně, vyberte ovládací prvek, který chcete najít v aplikaci přidružený test. Dále otevřete místní nabídku pro ovládací prvek a potom zvolte **najít kontrolní mechanismus uživatelského rozhraní**. V aplikaci, která se testuje je určen ovládací prvek s modré ohraničení.

> [!NOTE]
> Předtím, než můžete vyhledat ovládacího prvku uživatelského rozhraní, ověřte, zda je spuštěna aplikace spojené s test.

### <a name="tips"></a>Tipy

Můžete použít **najít všechny** možnosti ověříte, že všechny ovládací prvky v kontejneru mohou být správně nachází. Tato možnost je popsaná v další části.

## <a name="locate-a-control-and-its-descendants"></a>Najít ovládací prvek a jeho následníky

Můžete ověřit, že všechny ovládací prvky v části kontejner může být správně umístěn v uživatelském rozhraní aplikace v rámci testu. To může být užitečný při ověřování vyhledávání vlastnost provedené změny může mít v kontejneru. Kromě toho dojde-li významné změny v uživatelském rozhraní aplikace testovaného, můžete ověřit stávající vlastností ovládacího prvku vyhledávání správnost stále.

![Vyhledejte všechny odvozené ovládací prvky](../test/media/codeduilocateall.png)

![Všechny ovládací prvky, které jsou umístěné](../test/media/codeduilocateall2.png)

V **mapy ovládacího prvku uživatelského rozhraní** podokně vyberte ovládacího prvku kontejneru, který chcete vyhledat a zobrazit všechny následníky pro. Dále otevřete místní nabídku pro ovládací prvek a vyberte **najít všechny**. Ovládacího prvku kontejner a všechny její následné ovládací prvky, jsou označené v programových uživatelského rozhraní editoru testu s zelená značka zaškrtnutí nebo červený symbol "X". Tyto značky umožňují vědět, pokud se ovládací prvky úspěšně nacházely v aplikaci v rámci testu.

> [!NOTE]
> Před vyhledáním ovládacích prvků uživatelského rozhraní, ověřte, zda je spuštěna aplikace spojené s test.

## <a name="insert-a-delay-before-a-ui-action"></a>Vložení prodlevy před akci uživatelského rozhraní

V některých případech můžete chtít provést test čekat na určité události proběhnout, jako je například okno se objeví indikátor průběhu zmizí a tak dále. Pomocí editoru programových testů uživatelského rozhraní, můžete k tomu lze vložení prodlevy před akci uživatelského rozhraní. Můžete určit, kolik sekund má být zpoždění.

![Vložení prodlevy před akci uživatelského rozhraní](../test/media/codeduidelay.png)

![Zpoždění přidána s 5 sekund](../test/media/codeduidealy2.png)

V **akci uživatelského rozhraní** podokně rozbalte metodu test, který obsahuje, kterou chcete vložení prodlevy před akci uživatelského rozhraní. Vyberte akci uživatelského rozhraní. Dále otevřete místní nabídku pro akci uživatelského rozhraní a zvolte **vložit zpoždění před**. Zpoždění je vložit a zvýrazněná, před vybranou akci uživatelského rozhraní s následujícím textem: **počkejte 1 sekundy pro uživatele zpoždění mezi akce**. V okně vlastností změňte hodnotu **zpoždění** vlastnost na požadovanou hodnotu v milisekundách.

Po dokončení vkládání zpoždění, uložte změny do souboru UIMap.Designer výběrem **Uložit** na panelu nástrojů Visual Studio.

Pokud je potřeba zajistit, že určitý ovládací prvek je k dispozici před akci uživatelského rozhraní, měli byste zvážit přidání vlastní kód pro metodu test pomocí příslušné metody UITestControl.WaitForControlXXX(). Další informace najdete v tématu [provedení programového uživatelského rozhraní testy počkejte pro konkrétní události při přehrávání](../test/making-coded-ui-tests-wait-for-specific-events-during-playback.md).

## <a name="see-also"></a>Viz také:

- [Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)
- [Vytváření programové testy uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md)
- [Vytvoření datově řízeného programového testu UI](../test/creating-a-data-driven-coded-ui-test.md)
- [Návod: Vytváření, upravování a údržba programového testu UI](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md)