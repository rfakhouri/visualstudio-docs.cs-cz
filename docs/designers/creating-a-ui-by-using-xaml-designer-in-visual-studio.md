---
title: Vytvoření uživatelského rozhraní pomocí Návrháře XAML v sadě Visual Studio
ms.date: 07/17/2017
ms.technology: vs-ide-designers
ms.topic: conceptual
f1_keywords:
- VS.XamlDesigner
- VS.DevicePanel
- VS.XamlEditor
- VS.DocumentOutline
ms.assetid: c54969a7-d75a-4a35-9b37-af7a596a7c24
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 9eadc306b0b2f7c53dffc01d27590bc5d4cf4b52
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="creating-a-ui-by-using-xaml-designer-in-visual-studio"></a>Vytvoření uživatelského rozhraní pomocí Návrháře XAML v sadě Visual Studio
Návrhář XAML v sadě Visual Studio poskytuje vizuální rozhraní vám pomohou návrhu založených na XAML Windows a webové aplikace. Uživatelská rozhraní pro vaše aplikace můžete vytvořit tak, že přetáhnete ovládacích prvků z **sada nástrojů** a nastavení vlastností ve **vlastnosti** okno. Můžete taky upravit XAML přímo v zobrazení jazyka XAML.

 Pokročilé úlohy návrhu XAML například animace a chování najdete v části [vytvoření uživatelského rozhraní pomocí nástroje Blend for Visual Studio](../designers/creating-a-ui-by-using-blend-for-visual-studio.md). Viz také [navrhování XAML v sadě Visual Studio a nástroj Blend for Visual Studio](../designers/designing-xaml-in-visual-studio.md) porovnání mezi nástroje.

## <a name="xaml-designer-workspace"></a>Pracovní prostor Návrhář XAML
 Pracovní prostor v Návrháři XAML se skládá z několika součástí visual rozhraní. Patří mezi ně návrhové plochy editoru XAML, zařízení oken, Osnova dokumentu – okno a vlastnosti – okno. Chcete-li otevřít návrháře XAML, klikněte pravým tlačítkem na soubor XAML v **Průzkumníku řešení** a zvolte **Návrhář zobrazení**.

## <a name="authoring-views"></a>Vytváření zobrazení
 Návrhář XAML poskytuje zobrazení jazyka XAML a synchronizované zobrazení návrhu vykreslované značky XAML vaší aplikace. S XAML soubor otevřete v sadě Visual Studio, můžete přepnout mezi návrhového zobrazení a zobrazení jazyka XAML pomocí **návrhu** a **XAML** karty. Můžete použít **Prohodit podokna** tlačítko pro přepínání okna se zobrazí v horní části: kreslicí plochy nebo editoru XAML.

 V návrhovém zobrazení obsahující okno *návrhové plochy* je aktivní okno a můžete ji použít jako primární pracovní prostor. Můžete ho použít pro vizuální návrh stránky v aplikaci přidáním nebo kreslení elementy a poté podle jejich změně. Další informace najdete v tématu [práce s prvky v Návrháři XAML](../designers/working-with-elements-in-xaml-designer.md). Tento obrázek ukazuje návrhové plochy v zobrazení návrhu.

 ![Návrh zobrazení návrháře XAML](../designers/media/xaml_editor_design_view.png "xaml_editor_design_view")

 Tyto funkce jsou dostupné v kreslicí plochy:

 **Zarovnávací čáry** zarovnávacích čar jsou *zarovnání hranice* , zobrazovat jako řádky přerušovanou red zobrazíte, když je zarovnán okrajů ovládacích prvků, nebo když směrné plány text je zarovnán. Zarovnání hranice zobrazí pouze tehdy, když **přichycení k zarovnávací čáry** je povoleno.

 **Které mřížky** `Grid` které se používají ke správě řádků a sloupců v [mřížky](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.grid.aspx) panelu. Můžete vytvářet a odstraňovat řádků a sloupců a jejich relativní šířky a výšky můžete upravit. Svislé mřížky liště, která se zobrazí na levé straně návrhové plochy, je použit pro řádky a vodorovné čáry, která se zobrazí v horní části, je použít pro sloupce.

 **Ozdobného prvku mřížky** A `Grid` adorner se zobrazí jako trojúhelníček, který má svislé nebo vodorovné čáry k němu připojen na `Grid` liště. Při přetažení `Grid` adorner, šířky nebo výšky sousedících sloupců a řádků aktualizovat jako pohybu myší.

 `Grid` ozdobného prvku slouží k řízení šířka a Výška `Grid`na řádků a sloupců. Můžete přidat nový sloupec nebo řádek kliknutím v `Grid` které. Když přidáte nový řádek sloupce či řádku pro `Grid` panel, který má dvě nebo více sloupců nebo řádků, zkrácená panelu nástrojů zobrazí mimo liště, která umožňuje explicitně nastavená šířka a výška. Zkrácená nástrojů můžete nastavit nastavení velikosti možností pro `Grid` řádků a sloupců.

 **Změnit velikost popisovače** zpracovává změny velikosti se zobrazují v vybrané ovládací prvky a umožňují změnit velikost ovládacího prvku. Při změně velikosti ovládacího prvku, šířku a výšku hodnoty se obvykle zobrazuje můžete velikost ovládacího prvku. Další informace o manipulace s ovládacím prvkům v zobrazení návrhu najdete v tématu [práce s prvky v Návrháři XAML](../designers/working-with-elements-in-xaml-designer.md).

 **Okraje** okraje představují množství pevné mezery mezi hraniční ovládacího prvku a hrany jejímu kontejneru. Okraje ovládacího prvku lze nastavit pomocí [okraj](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.frameworkelement.margin.aspx) vlastnosti v rámci **rozložení** v okně Vlastnosti.

 **Okrajů ozdobného prvku** ozdobného okraj prvku můžete změnit okraje elementu vzhledem k jejímu kontejneru rozložení. Při adorner okraj, není nastaven okraj a okraj adorner zobrazí porušený řetězec. Pokud u okraje není nastavená, bude elementy zůstávají na svém místě, při změně velikosti kontejneru rozložení v době běhu. Při zavření okraj adorner adorner okraj zobrazí Nepřerušený řetěz a elementy se přesune s okraj při změně velikosti kontejneru rozložení v době běhu (okraj zůstává pevná).

 **Element popisovače** upravíte elementu pomocí elementu obslužných rutin, které se zobrazují na návrhové plochy při přesunutí ukazatele nad rozích modrou značku, která obklopuje element. Tyto obslužné rutiny umožňují otáčet, změnit velikost, překlopit, přesunout nebo přidejte do elementu rohu radius. Symbol pro element popisovač se liší podle funkce a změny v závislosti na přesné umístění ukazatele. Pokud nevidíte element obslužných rutin, ujistěte se, že je vybraný element.

 V návrhovém zobrazení jsou k dispozici v levé dolní části obrazovky návrhové plochy další příkazy, jak je vidět tady:

 ![Návrh zobrazení příkazy](../designers/media/xaml_editor_design_controls.png "xaml_editor_design_controls")

 Tyto příkazy jsou k dispozici tento panel nástrojů:

 **Zvětšení** přiblížení umožňuje velikost návrhovou plochu. Zvětšení z 12,5 % 800 %, nebo vybrat možnosti, například **přizpůsobit výběru** a **přizpůsobit na všechny**.

 **Zobrazit nebo skrýt snap mřížky** zobrazí nebo skryje snap mřížky, který ukazuje mřížky. Mřížky se používají při buď **přichycení k mřížky** nebo **přichycení k zarovnávací čáry** je povoleno.

 **Zapnutí nebo vypnutí přichycení k mřížky** Pokud **přichycení k mřížky** je povoleno při přetažení element na návrhové plochy, element obvykle zarovnané s nejbližší vodorovného a svislého mřížky.

 **Zapne nebo vypne přichycení k zarovnávací čáry** zarovnávací čáry usnadňují zarovnání ovládací prvky relativní k sobě navzájem. Pokud **přichycení k zarovnávací čáry** je povoleno, když přetáhněte ovládací prvek relativně k další ovládací prvky, zarovnání zobrazena při okrajů a některé ovládací prvky text je zarovnán vodorovně nebo svisle. Hranici zarovnání se zobrazuje jako červený přerušovanou čáru.

 V zobrazení jazyka XAML okno obsahuje editoru XAML je aktivní okno a editoru XAML, je primární nástroj pro vytváření. Extensible aplikace Markup Language (XAML) obsahuje slovník deklarativní, na základě XML určení uživatelské rozhraní aplikace. Zobrazení XAML zahrnuje IntelliSense, automatického formátování, zvýraznění syntaxe a značky navigace. Tento obrázek ukazuje zobrazení jazyka XAML:

 ![Zobrazení jazyka XAML](../designers/media/xaml_editor.png "xaml_editor")

 **Zobrazení příčku** příčku zobrazení se zobrazí v horní části zobrazení jazyka XAML, když je editoru XAML, v okně nižší. Zobrazení příčku vám umožňuje řídit relativní velikosti zobrazení návrhu a zobrazení jazyka XAML. Můžete také exchange umístění zobrazení (pomocí **Prohodit podokna** tlačítko), zadejte, zda jsou vodorovně nebo svisle uspořádané zobrazení a sbalit buď zobrazení.

 **Přiblížení značek** přiblížení značek vám umožňuje zobrazení jazyka XAML velikost. Můžete zvětšit z 20 % na 400 %.

## <a name="device-window"></a>Okno zařízení
 Okno zařízení v Návrháři XAML umožňuje simulovat v době návrhu různých zobrazení, zobrazí a zobrazit možnosti pro váš projekt. Okno zařízení je k dispozici na **návrhu** nabídky, když pracujete v Návrháři XAML. Tady je bude vypadat takto:

 ![Okno zařízení](../designers/media/xaml_editor_device_panel.png "xaml_editor_device_panel")

 Toto jsou možnosti k dispozici v okně zařízení:

 **Zobrazit** určuje různé velikosti zobrazení a řešení pro aplikaci.

 **Orientace** Určuje jinou orientace pro aplikaci: **na šířku** nebo **na výšku**.

 **Okraj** Určuje zarovnání různých edge pro vaši aplikaci: **i**, **doleva**, **vpravo**, nebo **žádné**.

 **Vysoký kontrast** Náhled aplikace na základě nastavení vybrané kontrastu. Toto nastavení, pokud jiné než nastavíte hodnotu **výchozí**, přepíše `RequestedTheme` sady vlastností v App.xaml.

 **Přepsání škálování** vypíná a zapíná emulace dokumentu škálování v rámci návrhovou plochu. To umožňuje zvýšit škálování procento jediný faktor. Zaškrtněte políčko Zapnout emulace. Například pokud je vaše škálování procento 100 %, dokumentu v rámci návrhovou plochu, která bude škálovat až 140 %. Tato možnost je zakázaná, pokud je aktuální škálování procento 180.

 **Minimální šířka** určuje nastavení minimální šířky. Minimální šířka lze změnit v App.xaml.

 **Motiv** určuje motiv aplikace. Například může přepínat mezi tmavý a motiv světlý.

 **Zobrazit chrome** vypíná a zapíná rámečku simulované tablet okolí vaší aplikace v zobrazení návrhu. Zaškrtněte políčko Zobrazit rámečku.

 **Klip zobrazíte** Určuje režim zobrazení. Zaškrtněte políčko k oříznutí dokumentu velikost na velikost zobrazení.

## <a name="document-outline-window"></a>Osnova dokumentu – okno
 Okno Osnova dokumentu v Návrháři XAML slouží k provádění těchto úkolů:

-   Zobrazení hierarchická struktura všechny elementy na návrhové plochy.

-   Vyberte elementy, aby mohl upravovat je (přesunout je přibližně v hierarchii, je upravit na návrhové plochy, nastavit jejich vlastnosti v okně vlastností a tak dále). Další informace najdete v tématu [práce s prvky v Návrháři XAML](../designers/working-with-elements-in-xaml-designer.md)

-   Vytvoření a úprava šablon pro prvky, které jsou ovládací prvky.

-   Pomocí místní nabídky pro vybrané elementy. V nabídce stejné je také k dispozici pro vybrané elementy návrhové plochy.

 Chcete-li zobrazit okno Osnova dokumentu, na řádku nabídek zvolte **zobrazení**, **ostatní okna**, **Osnova dokumentu**.

 ![Osnova dokumentu – okno](../designers/media/xaml_editor_doc_outline.png "xaml_editor_doc_outline")

 Toto jsou možnosti k dispozici v okně Osnova dokumentu:

 **Osnova dokumentu** hlavní zobrazení v okně Osnova dokumentu zobrazí hierarchii dokumentu ve stromové struktuře. Hierarchická povaha Osnova dokumentu můžete prozkoumat dokumentu na různých úrovních podrobností a při zamykání a skrýt elementy samostatně nebo ve skupinách.

 **Zobrazit nebo skrýt** zobrazí nebo skryje elementy návrhové plochy, které odpovídají položkám v osnově dokumentu. Použití **zobrazit či skrýt** tlačítka, která zobrazí symbol přehled při ukazuje nebo stiskněte kombinaci kláves CTRL + H skrýt elementy a SHIFT + CTRL + H k jejich zobrazení.

 **Uzamčení** uzamkne nebo odemkne návrhové plochy elementy, které odpovídají položkám v osnově dokumentu. Nemůže být upraven uzamčeném elementy. Použití **uzamčení** tlačítka, které budou zobrazovat visací zámek symbolů po zamčení nebo stiskněte klávesu CTRL + L na zámek elementy a SHIFT + CTRL + L k odemčení.

 **Vrátit obor pageRoot** možnosti v horní části okna Osnova dokumentu, která zobrazuje symbol aktuálním šipky, vrátí do předchozí oboru Osnova dokumentu. Obor si lze použít pouze v případě, že jste v oboru styl nebo šablony.

## <a name="properties-window"></a>Vlastnosti – okno
 Okno vlastností umožňuje nastavování hodnot vlastností ovládacích prvků. Tady je bude vypadat takto:

 ![Vlastnosti – okno](../designers/media/xaml_editor_prop_window.png "xaml_editor_prop_window")

 Existují různé možnosti v horní části okna Vlastnosti. Název aktuálně vybraného elementu můžete změnit pomocí **název** pole. V levém horním rohu je ikonu, která představuje aktuálně vybraného elementu. Chcete-li uspořádat vlastnosti podle kategorie a abecedně, klikněte na tlačítko **kategorie**, **název**, nebo **zdroj** v **uspořádat podle** seznamu. Chcete-li zobrazit seznam událostí pro ovládací prvek, klikněte na tlačítko **události** tlačítko, které zobrazí symbol lightning funkcí bolt. Vyhledat vlastnosti, spusťte pro název vlastnosti v typu **vlastností vyhledávání** pole. V okně Vlastnosti se zobrazí vlastnosti, které odpovídají kritériím hledání během psaní. Některé vlastnosti umožňují nastavit upřesňující vlastnosti tak, že vyberete šipku dolů. Další informace o používání vlastnosti a zpracování událostí najdete v tématu [rychlé spuštění: Přidání ovládacích prvků a zpracování událostí](http://go.microsoft.com/fwlink/?LinkID=247983)

 Napravo od každou vlastnost hodnota je *značka vlastnosti* které se zobrazí jako pole symbolu. Vzhled značky vlastnost určuje, jestli je datová vazba nebo použít pro vlastnost prostředku. Například symbol bílé pole určuje výchozí hodnotu, symbol černé políčko obvykle označuje, že byl použit místní prostředek, a oranžové pole obvykle značí, že byl použit datová vazba. Po kliknutí na tlačítko Vlastnosti značky, přejděte na definici stylu, otevřete Tvůrce vazby dat nebo otevřít dialogové okno Výběr prostředků.

## <a name="see-also"></a>Viz také

- [Práce s elementy v Návrháři XAML](../designers/working-with-elements-in-xaml-designer.md)
- [Postup vytvoření a použití prostředku](../designers/how-to-create-and-apply-a-resource.md)
- [Návod: Vazba s daty v Návrháři XAML](../designers/walkthrough-binding-to-data-in-xaml-designer.md)