---
title: Zobrazení návrháře modelu obsahu schématu XML
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: reference
ms.assetid: e8db7c7d-31cf-479e-9dcc-299759891795
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 355fe0485327c5c92441cd54d42253d022c7bb6e
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2018
---
# <a name="content-model-view"></a>Zobrazení obsahu modelu

Zobrazení obsahu modelu poskytuje grafické reprezentace místní a globální schématu uzlů a jejich komponent, včetně jednoduché a komplexní typy, elementy, skupiny modelů, atributy a skupin atributů. XML – komentáře a pokyny pro zpracování nelze zobrazit v zobrazení obsahu modelu. Zobrazení modelu obsahu obsahuje dva panely: **prostoru** panel, který obsahuje seznam uzlů v [prostoru Návrhář schématu XML](../xml-tools/xml-schema-designer-workspace.md)a na návrhovou plochu, kde se můžete podívat modelu obsahu schématu uzly, které jsou vybrány v **prostoru** panelu. Zobrazení obsahu modelu zahrnuje taky panelu nástrojů Návrhář schématu XML a navigačního panelu.

 Na následujícím obrázku **prostoru** panel obsahuje šest uzly schématu. `purchaseOrder` Vybrán uzel **prostoru** panelu a v návrhovou plochu, která se zobrazí.

 ![Zobrazení návrháře modelu obsahu schématu XML](../xml-tools/media/xsddesigner_contentmodelview.gif "XSDDesigner_ContentModelView")

## <a name="workspace-panel"></a>Pracovní prostor panely

 Po přidání uzlů do pracovního prostoru, zobrazí se seznam uzlů v **prostoru** panel zobrazení obsahu modelu. Když vyberete uzly v **prostoru** panelu, zobrazí se na návrhovou plochu zobrazení obsahu modelu. K odstranění uzlů z pracovního prostoru, použijte panelu nástrojů návrháře XSD **prostoru** panely kontextové nabídky, nebo **odstranit** klíč.

 Informace o přidání uzlů, najdete v části "Přidání uzlů do prostoru" v [prostoru Návrhář schématu XML](../xml-tools/xml-schema-designer-workspace.md).

## <a name="design-surface"></a>Návrhové plochy

 Vybrání uzlu v **prostoru** panelu, přidá se na návrhovou plochu zobrazení obsahu modelu, kde můžete zobrazit podrobnosti o uzlu.

 Model obsahu uzlu je reprezentována rozšíření grafické stromu s elementů a atributů, které jsou uvedeny jako uzly stromu. Ve výchozím nastavení je rozšířit pouze jedna úroveň. Další informace, jako je například compositors, názvy typů, skupiny a další kontejnery jsou umístěny v svislá čára (Pokud rozbalen) podél elementů a atributů, které budou uzavřete. Když dvakrát kliknete na svislá čára stane vodorovné a sbalí stromu. Když dvakrát kliknete na vodorovném řádku stane svislé a rozšíří stromu. Výběr svislá čára vybere všechny uzly v kontejneru. Rozšíření se objeví na pravé straně uzlu, pokud element můžete rozbalit nebo sbalit.

 Pokud návrhovou plochu, která je prázdné, editoru XML **Explorer schématu XML**, a jsou zobrazeny vodoznak. *Vodoznak* seznam obsahuje odkazy na všechna zobrazení XSD Designer. Pokud sada schéma obsahuje chyby, zobrazí se následující text na konci seznamu: "K zobrazení a opravte chyby v sadě pomocí seznamu chyb."

## <a name="breadcrumb-bar"></a>Navigačního panelu

 Navigačního panelu v dolní části zobrazení obsahu modelu zobrazuje umístění vybraného uzlu v sadě schématu.

## <a name="context-menus"></a>Kontextové nabídky

 Když kliknete pravým tlačítkem na položku na návrhovou plochu nebo **prostoru** panelu, zobrazí se z kontextové nabídky. Následující tabulka popisuje možnosti, které jsou k dispozici pro zobrazení obsahu modelu návrhovou plochu.

|Možnost|Popis|
|------------|-----------------|
|**Zobrazit v Průzkumníku schématu XML**|Vloží fokus na schéma Průzkumníka a zvýrazňuje uzlu sady schématu.|
|**V zobrazení grafů**|Přepne do zobrazení grafu.|
|**Generovat ukázkovém kódu XML**|K dispozici pouze pro globální elementy. Generuje a ukázkový soubor XML pro element globální.|
|**Zobrazit dokumentaci**|Zobrazí nebo skryje poznámky nebo dokumentaci uzlu obsah.|
|**Exportovat Diagram jako obrázek**|Uloží na návrhovou plochu do soubor ve formátu XPS.|
|**Zobrazení kódu**|Otevře se soubor, který obsahuje vybraný uzel v editoru XML. Položky, který je vybraný v **Explorer schématu XML** , vybere se také v editoru XML.|
|**Okno Vlastnosti**|Otevře se **vlastnosti** okno (pokud ještě není otevřený). Toto okno se zobrazí informace o uzlu.|

 Následující tabulka popisuje možnosti, které jsou dostupné pro **prostoru** panelu.

|Možnost|Popis|
|------------|-----------------|
|**Zobrazit v Průzkumníku schématu XML**|Vloží fokus na schéma Průzkumníka a zvýrazňuje uzlu sady schématu.|
|**V zobrazení grafů**|Přepne do graf zobrazení.|
|**Vymazat pracovního prostoru**|Vymaže pracovním prostoru a návrhovou plochu.|
|**Odeberte z pracovního prostoru**|Odebere vybrané uzly z pracovního prostoru a návrhovou plochu.|
|**Odeberte všechny kromě výběr z pracovního prostoru**|Odebere uzly, které nejsou vybrané z pracovního prostoru a návrhovou plochu.|
|**Generovat ukázkovém kódu XML**|K dispozici pouze pro globální elementy. Generuje a ukázkový soubor XML pro element globální.|
|**Vybrat vše**|Vybere všechny uzly v **prostoru** panelu.|
|**Zobrazení kódu**|Otevře se soubor, který obsahuje vybraný uzel v editoru XML. Položky, který je vybraný v **Explorer schématu XML** , vybere se také v editoru XML.|
|**Okno Vlastnosti**|Otevře se **vlastnosti** okno (pokud ještě není otevřený). Toto okno se zobrazí informace o uzlu.|

## <a name="properties-window"></a>Vlastnosti – okno

 Pomocí místní nabídky původně otevřete **vlastnosti** okno. Ve výchozím nastavení **vlastnosti** okno se zobrazí v pravém dolním rohu Visual Studio. Při kliknutí na uzel, který se vykreslí v zobrazení obsahu modelu, vlastnosti tohoto uzlu se zobrazí v **vlastnosti** okno.

## <a name="xsd-designer-toolbar"></a>XSD návrháře panelu nástrojů

 Následující tlačítka panelu nástrojů Návrhář XSD je zapnuté, pokud je aktivní zobrazení obsahu modelu.

 ![XML schéma návrháře nástrojů](../xml-tools/media/xsdcontentmodelviewtoolbar.gif "XSDContentModelViewToolbar")

|Možnost|Popis|
|------------|-----------------|
|**Nastaví počáteční zobrazení**|Přepne do [spuštění zobrazení](../xml-tools/start-view.md). Toto zobrazení je přístupná pomocí klávesové zkratky: **Ctrl**+**1**.|
|**Nastaví zobrazení modelu obsahu**|Přepne do [modelu zobrazení obsahu](../xml-tools/content-model-view.md). Toto zobrazení je přístupná pomocí klávesové zkratky: **Ctrl**+**2**.|
|**Zobrazit zobrazení grafu**|Přepne do [graf zobrazení](../xml-tools/graph-view.md). Toto zobrazení je přístupná pomocí klávesové zkratky: **Ctrl**+**3**.|
|**Vymazat pracovního prostoru**|Vymaže pracovním prostoru a návrhovou plochu.|
|**Odeberte z pracovního prostoru**|Odebere vybrané uzly z pracovního prostoru a návrhovou plochu.|
|**Odeberte všechny kromě výběr z pracovního prostoru**|Odebere uzly, které nejsou vybrané z pracovního prostoru a návrhovou plochu.|
|**Zobrazit dokumentaci**|Zobrazí nebo skryje poznámky nebo dokumentaci uzlu obsah.|

## <a name="panscroll"></a>Pan/posuvníku

 Pomocí posuvníky nebo tím, že se můžete posunete zobrazení návrhovou plochu **Ctrl** klíče při klikněte a přetáhněte myší. Pokud provádíte posun na návrhovou plochu, klikněte na tlačítko a přetáhněte, kurzoru změní na čtyři křížového šipky směřující do čtyř směrů.

## <a name="undoredo"></a>Vrátit/opakovat

 Možnost zpět/opakování je povoleno v zobrazení obsahu modelu pro následující akce:

-   Přidávání do jednoho uzlu pomocí přetahování.

-   Přidání více uzlů z výsledků hledání v Průzkumníku schématu.

-   Přidání uzlů ze zobrazení spustit.

-   Odstranění jednoho nebo více uzlů.

## <a name="zoom"></a>Lupa

 Přiblížení je k dispozici v pravém dolním rohu zobrazení obsahu modelu.

 Přiblížení se dá řídit následujícími způsoby:

-   Tím, že se **Ctrl** klíč a otáčí myši kol při myši ukazatele myši na povrch zobrazení obsahu modelu.

-   Pomocí posuvníku. Posuvník zobrazuje aktuální úroveň přiblížení.

Posuvník přiblížení je plné krytí, pokud vyberte ho, při přechodu nebo používají **Ctrl** kolečka myši pro přiblížení; v jinou dobu je transparentní.

## <a name="xml-editor-integration"></a>Integrace editor XML

 Můžete přepínat mezi přepnout **Návrhář XSD** a Editor souborů XML pomocí místní nabídky.

 Pokud provedete změny schématu nastavení v editoru XML jsou synchronizovány změny v modelu zobrazení obsahu. Další informace najdete v tématu [integrace s editoru XML](../xml-tools/integration-with-xml-editor.md).

## <a name="see-also"></a>Viz také

- [Pracovní prostor Návrháře schémat XML](../xml-tools/xml-schema-designer-workspace.md)