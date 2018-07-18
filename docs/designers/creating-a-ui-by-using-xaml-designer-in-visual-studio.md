---
title: Vytvoření uživatelského rozhraní pomocí Návrháře XAML v sadě Visual Studio
ms.date: 07/17/2017
ms.prod: visual-studio-dev15
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
ms.openlocfilehash: 3daf20ee3fcb2472e88d2387abf870862b0d5c47
ms.sourcegitcommit: 522ba712c0d625e51352506146b0556414681964
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/06/2018
ms.locfileid: "37889964"
---
# <a name="creating-a-ui-by-using-xaml-designer-in-visual-studio"></a>Vytvoření uživatelského rozhraní pomocí Návrháře XAML v sadě Visual Studio
Návrhář XAML v sadě Visual Studio poskytuje vizuální rozhraní při návrhu na základě XAML Windows a Web apps. Uživatelská rozhraní pro vaše aplikace můžete vytvořit přetažením ovládacích prvků **nástrojů** a nastavení vlastností ve **vlastnosti** okno. XAML můžete také upravit přímo v XAML zobrazení.

 Pokročilé úlohy návrhu XAML například animace a chování, naleznete v tématu [vytvoření uživatelského rozhraní pomocí nástroje Blend pro Visual Studio](../designers/creating-a-ui-by-using-blend-for-visual-studio.md). Viz také [návrh XAML v sadě Visual Studio a nástroje Blend for Visual Studio](../designers/designing-xaml-in-visual-studio.md) porovnání mezi službou nástroje.

## <a name="xaml-designer-workspace"></a>Pracovní prostor návrháře XAML
 Pracovní prostor v Návrháři XAML se skládá z několika prvků vizuální rozhraní. Patří mezi ně **návrhové plochy**, **editoru XAML**, **zařízení** okně **Osnova dokumentu** okně a **vlastnosti**  okna. Chcete-li otevřít Návrhář XAML, klikněte pravým tlačítkem na soubor XAML v **Průzkumníka řešení** a zvolte **Návrhář zobrazení**.

## <a name="authoring-views"></a>Zobrazení pro vytváření
 Návrhář XAML zobrazuje XAML a synchronizované zobrazení návrhu vaší aplikace vykreslované značky XAML. S XAML soubor otevřít v sadě Visual Studio, můžete přepínat mezi návrhové a XAML zobrazení pomocí **návrhu** a **XAML** karty. Můžete použít **zaměnit podokna** tlačítkem přepnete okna se zobrazí v horní části: návrhové ploše nebo v editoru XAML.

 V návrhovém zobrazení okna obsahující *návrhové plochy* aktivní okno a slouží jako primární pracovní plocha. Můžete ho použít přidáním nebo výkresu prvky a jejich úpravou vizuálně navrhnout stránku ve vaší aplikaci. Další informace najdete v tématu [práce s elementy v Návrháři XAML](../designers/working-with-elements-in-xaml-designer.md). Tento obrázek ukazuje návrhové ploše v zobrazení Návrh.

 ![Zobrazení návrhu Návrháře XAML](../designers/media/xaml_editor_design_view.png)

 Tyto funkce jsou dostupné v návrhové plochy:

 **Zarovnávacích čar** jsou zarovnávacích čar *hranicích zarovnání* , která se zobrazují jako přerušovaná red řádky k zobrazení při okraji ovládací prvky odpovídají nebo když jsou zarovnané text směrné plány. Hranice pro zarovnání se zobrazí pouze tehdy, když **přichycování k zarovnávacím čárám** je povolená.

 **Mřížka rails** `Grid` rails se používají ke správě řádků a sloupců v [mřížky](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.grid.aspx) panelu. Můžete vytvářet a odstraňovat řádky a sloupce a můžeme upravit jejich relativní šířky a výšky. Svislé lišty mřížky, které se zobrazí na levé straně návrhové plochy, se používá pro řádky a vodorovná čára, která se zobrazí v horní části, se používá pro sloupce.

 **Doplňky pro úpravy mřížky** doplněk pro úpravy A mřížky se zobrazí jako trojúhelník, který má k němu připojený v mřížce lišty řádek svislý nebo vodorovný. Při přetažení pro úpravy mřížky šířky nebo výšky sousedící sloupce nebo řádky aktualizovat, protože najeďte myší.

 Doplňky pro úpravy mřížky se používají k řízení šířky a výšky řádků a sloupců do mřížky. Můžete přidat nový sloupec nebo řádek kliknutím v mřížce rails. Když přidáte nový řádek nebo sloupec řádku pro panel mřížky, která má dvě nebo více sloupců nebo řádků, se zobrazí zkrácené nástrojů mimo lišty, která umožňuje explicitně nastavit šířku a výšku. Zkrácené nástrojů vám umožní nastavit možnosti nastavení velikosti pro mřížce řádků a sloupců.

 **Úchyty pro změnu velikosti** úchyty pro změnu velikosti, zobrazí se na vybraných ovládacích prvků a vám umožní změnit velikost ovládacího prvku. Při změně velikosti ovládacího prvku se zobrazí hodnoty šířky a výšky obvykle umožňují upravit velikost ovládacího prvku. Další informace o manipulaci s ovládacích prvků v **návrhu** zobrazení naleznete v tématu [práce s elementy v Návrháři XAML](../designers/working-with-elements-in-xaml-designer.md).

 **Okraje** okraje představují velikost pevné mezery mezi okrajem ovládacího prvku a hraničními zařízeními svého kontejneru. Můžete nastavit okraje ovládacího prvku pomocí [okraj](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.frameworkelement.margin.aspx) pod **rozložení** v okně Vlastnosti.

 **Doplňky pro úpravy okrajů** Změna okrajů elementu vzhledem k jeho kontejner rozložení můžete použít doplňků pro úpravy rozpětí. Při otevření okrajů není nastavená okraj a doplněk pro úpravy rozpětí zobrazí porušený řetězec. Pokud není nastavena na okraj, zůstanou prvky na místě, při změně velikosti kontejneru rozložení v době běhu. Při zavření okrajů okrajů zobrazí Nepřerušený řetěz a prvky přesunuty spolu s okrajem při změně velikosti kontejneru rozložení v době běhu (na okraj zůstanou pevné).

 **Element popisovače** upravíte elementu pomocí elementu popisovače, které se zobrazí na návrhové ploše při přesunutí ukazatele myši do rohů modrý obdélník, který kolem prvku. Tyto manipulační body umožňují otočení, změna velikosti, překlopit, přesunout nebo přidat poloměr na prvek. Značka pro element popisovač se liší podle funkcí a mění v závislosti na přesné umístění ukazatele. Pokud nevidíte element popisovače, ujistěte se, že je vybraný prvek.

 V **návrhu** zobrazení návrhové plochy další příkazy jsou k dispozici v oblasti levého dolního rohu obrazovky, jak je znázorněno zde:

 ![Návrhové zobrazení příkazů](../designers/media/xaml_editor_design_controls.png)

 Tyto příkazy jsou k dispozici na tomto panelu nástrojů:

 **Přiblížení** přiblížení umožňuje změnit velikost na návrhovou plochu. Můžete zvětšit z % 12,5 800 % nebo vyberte možnosti, jako je například **přizpůsobit výběru** a **přizpůsobit všechny**.

 **Zobrazit/skrýt přichytávací mřížku** zobrazí nebo skryje přichytávací mřížku, která zobrazuje mřížky. Mřížka se používají, když povolíte buď **přichycování k čarám mřížky** nebo **přichycování k zarovnávacím čárám**.

 **Zapnutí a vypnutí přichycování k čarám mřížky** Pokud **přichycování k čarám mřížky** zapnutý, při přetahování prvku na návrhové ploše, element obvykle bylo v souladu s nejbližší vodorovné a svislé mřížky.

 **Zapnout či vypnout přichycování k zarovnávacím čárám** usnadňují zarovnávacích čar zarovnání určuje relativní vzhledem k sobě navzájem. Pokud **přichycování k zarovnávacím čárám** je povolena, když přetahujete ovládacího prvku vzhledem k další ovládací prvky, zarovnání hranice zobrazí, když okrajů a text některé ovládací prvky jsou zarovnaná vodorovně nebo svisle. Hranici zarovnání se zobrazí jako červená přerušovaná čára.

 V **XAML** zobrazení okna obsahujícího editoru XAML je aktivní okno a editoru XAML je primární nástroj pro vytváření. Rozšiřitelné aplikace Markup Language (XAML) obsahuje slovník deklarativní, založený na formátu XML pro zadání uživatelského rozhraní aplikace. Zobrazení XAML obsahuje technologie IntelliSense, automatického formátování, zvýrazňování syntaxe a navigace značek. Tento obrázek ukazuje XAML zobrazení:

 ![Zobrazení XAML](../designers/media/xaml_editor.png)

 **Zobrazení příčku** příčku zobrazení se zobrazí v horní části zobrazení XAML, když je editoru XAML v dolním okně. Zobrazení příčku umožňuje řídit relativní velikosti **návrhu** zobrazení a **XAML** zobrazení. Můžete také exchange umístění zobrazení (pomocí **zaměnit podokna** tlačítko), určete, zda jsou vodorovně nebo svisle uspořádané zobrazení a následně sbalí buď zobrazení.

 **Přiblížení značek** přiblížení značky vám umožní na velikost **XAML** zobrazení. Můžete zvětšit z 20 % na 400 %.

## <a name="device-window"></a>Okno zařízení
 **Zařízení** okno v Návrháři XAML umožňuje simulovat v době návrhu různá zobrazení, zobrazení a zobrazení možností pro váš projekt. **Zařízení** okno je k dispozici na **návrhu** nabídky při práci v Návrháři XAML. Zde je, jak to funguje:

 ![Okno zařízení](../designers/media/xaml_editor_device_panel.png)

 Jedná se o možnostech dostupných v okně zařízení:

 **Zobrazit** určuje různé velikosti zobrazení a řešení pro aplikaci.

 **Orientace** Určuje jinou orientace aplikace: **na šířku** nebo **na výšku**.

 **Edge** Určuje zarovnání různých edge pro vaši aplikaci: **obě**, **vlevo**, **vpravo**, nebo **žádný**.

 **Vysoký kontrast –** zobrazte si náhled aplikace podle vybraného nastavení kontrastu. Toto nastavení, při nastavení na hodnotu jiné než **výchozí**, přepíše `RequestedTheme` nastavenou *App.xaml*.

 **Přepsat škálování** Zapne nebo vypne emulace škálování na návrhovou plochu dokumentu. To umožňuje škálování procento zvýšit jediný faktor. Zaškrtněte políčko Zapnout emulace. Například pokud vaše škálování procentuální hodnota je 100 %, dokumentu na návrhové ploše se bude škálovat 140 %. Tato možnost je zakázaná, pokud je aktuální procento škálování 180.

 **Minimální šířka** určuje nastavení minimální šířky. Minimální šířka lze změnit v *App.xaml*.

 **Motiv** určuje motivu aplikace. Například může přepínat mezi **tmavě** a **světla** motiv.

 **Zobrazit chrome** Zapne nebo vypne simulované tablet rámeček okolo vaší aplikace v návrhovém zobrazení. Zaškrtněte políčko Zobrazit rámce.

 **Oříznout přesahy displeje** Určuje režim zobrazení. Zaškrtněte políčko do Galerie velikost dokumentu na velikost zobrazení.

## <a name="document-outline-window"></a>Osnova dokumentu – okno
 Okno osnovy dokumentu v Návrháři XAML umožňuje provádět tyto úkoly:

-   Zobrazte hierarchickou strukturu všech prvků na návrhové ploše.

-   Vyberte elementy tak, aby možno upravovat (přesunout je kolem v hierarchii, je upravovat návrhovou plochu, nastavit jejich vlastnosti v okně Vlastnosti a tak dále). Další informace najdete v tématu [práce s elementy v Návrháři XAML](../designers/working-with-elements-in-xaml-designer.md)

-   Vytvářet a upravovat šablony pro prvky, které jsou ovládací prvky.

-   Pomocí místní nabídky pro vybrané elementy. Stejnou nabídku je také k dispozici pro vybrané elementy na návrhovou plochu.

 Chcete-li zobrazit **Osnova dokumentu** okna na řádku nabídek zvolte **zobrazení** > **ostatní Windows** > **Osnova dokumentu**.

 ![Osnova dokumentu – okno](../designers/media/xaml_editor_doc_outline.png)

 Jedná se o možnostech dostupných v **Osnova dokumentu** okno:

 **Osnova dokumentu** zobrazení hlavní **Osnova dokumentu** okno zobrazuje hierarchii dokumentu ve stromové struktuře. Hierarchickou povahu Osnova dokumentu můžete použít k prozkoumání dokumentu na různých úrovních podrobností a k uzamčení nebo skrytí prvků jednotlivě nebo ve skupinách.

 **Zobrazit/skrýt** zobrazí nebo skryje prvky návrhové plochy, které odpovídají položkám v Osnova dokumentu. Použití **zobrazit/skrýt** tlačítka, které se zobrazí symbol oka, když se zobrazí, nebo stisknutím klávesy **Ctrl**+**H** skrýt elementy a **Shift** + **Ctrl**+**H** k jejich zobrazení.

 **Zamknout/odemknout** zamkne a odemkne prvky návrhové plochy, které odpovídají položkám v Osnova dokumentu. Uzamčené elementy se nedá upravit. Použití **Zamknout/odemknout** tlačítka, které se zobrazí symbol visacího zámku nezobrazuje, když uzamčené, nebo stisknutím klávesy **Ctrl**+**L** prvkům zámek a **Shift** + **Ctrl**+**L** odemknout.

 **Obnovit obor na pageRoot** možnosti v horní části **Osnova dokumentu** okna, která zobrazuje symbol šipku nahoru, vrátí do předchozího oboru Osnova dokumentu. Přesouvání rozsahu směrem nahoru platí pouze v případě, že jste v rámci stylu nebo šablony.

## <a name="properties-window"></a>Vlastnosti – okno
 **Vlastnosti** okno umožňuje nastavit hodnoty vlastností v ovládacích prvcích. Zde je, jak to funguje:

 ![Vlastnosti – okno](../designers/media/xaml_editor_prop_window.png)

 Existují různé možnosti v horní části **vlastnosti** okna. Můžete změnit název aktuálně vybraného prvku s použitím **název** pole. V levém horním rohu je ikona, která reprezentuje aktuálně vybraný element. Chcete-li seřadit vlastnosti podle kategorie nebo abecedy, klikněte na tlačítko **kategorie**, **název**, nebo **zdroje** v **uspořádat podle** seznamu. Pokud chcete zobrazit seznam událostí pro ovládací prvek, klikněte na tlačítko **události** tlačítko, které zobrazí symbol boltu blesku. Vyhledejte vlastnost, začněte zadáním názvu vlastnosti v **vlastnosti hledání** pole. **Vlastnosti** okně zobrazí vlastnosti, které odpovídají zadanému hledání během psaní. Některé vlastnosti umožňují nastavit upřesňující vlastnosti tak, že vyberete šipku dolů. Další informace o používání vlastnosti a zpracování událostí naleznete v tématu [rychlý start: Přidání ovládacích prvků a zpracování událostí](http://go.microsoft.com/fwlink/?LinkID=247983)

 Vpravo od každé vlastnosti je hodnota *značka vlastnosti* , který se zobrazí jako pole symbolu. Vzhled značky vlastnost označuje, zda je datové vazby nebo prostředek použitý pro vlastnost. Například symbol bílé pole určuje výchozí hodnotu, symbol černé skříňky obvykle označuje, že použití místního prostředku a oranžová pole se obvykle označuje, že byl použit datové vazby. Po kliknutí na značku vlastnosti, můžete přejít na definici stylu, otevřete Tvůrce vazeb dat nebo otevřít výběr prostředku.

## <a name="see-also"></a>Viz také:

- [Práce s elementy v Návrháři XAML](../designers/working-with-elements-in-xaml-designer.md)
- [Postup vytvoření a použití prostředku](../designers/how-to-create-and-apply-a-resource.md)
- [Návod: Vazba s daty v Návrháři XAML](../designers/walkthrough-binding-to-data-in-xaml-designer.md)