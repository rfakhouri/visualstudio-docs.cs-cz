---
title: Zobrazení návrháře grafu schématu XML
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: reference
ms.assetid: 5881afde-3f24-4eb9-bff8-6cb3fc8aade7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5b95d8396cd96741187ae0146d2f727c3433b3ef
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2018
---
# <a name="graph-view"></a>Zobrazení grafu

Zobrazení grafu poskytuje grafické reprezentace globální schématu uzly a vztahy mezi uzly. Všimněte si, že jste ke změně rozložení schéma nastavit na návrhovou plochu, která neumožňuje zobrazení grafu. Zobrazení grafu zahrnuje taky panelu nástrojů Návrhář schématu XML a navigačního panelu.

 Následující obrázek znázorňuje zobrazení grafu se šesti globální uzly na jeho návrhové ploše.

 ![Zobrazení návrháře grafu schématu XML](../xml-tools/media/xsddesigner_graphview.gif "XSDDesigner_GraphView")

## <a name="design-surface"></a>Návrhové plochy

 Na plochu návrháře zobrazení grafu zobrazí obsah [prostoru Návrhář schématu XML](../xml-tools/xml-schema-designer-workspace.md). Pokud pracovní prostor obsahuje všechny globální uzly ze sady schématu, uzly se zobrazí na návrhovou plochu zobrazení grafu a dvojice šipek, které se mají vykreslovat mezi uzly, které mají vztahy.

 Dvakrát klikněte na uzel v zobrazení grafu se otevře se Editor XML.

 Pokud chcete odstranit vybrané uzly z pracovního prostoru, použijte panelu nástrojů programu XSD Designer nebo **odstranit** klíč.

 Pokud návrhovou plochu, která je prázdné, editoru XML **Explorer schématu XML**, a jsou zobrazeny vodoznak. *Vodoznak* seznam obsahuje odkazy na všechna zobrazení XSD Designer.

 ![Návrhář XSD; Graf zobrazení](../xml-tools/media/xsdgraphviewwatermark.gif "XSDGraphViewWatermark")

 Pokud sada schéma obsahuje chyby, zobrazí se následující text na konci seznamu: "K zobrazení a opravte chyby v sadě pomocí seznamu chyb."

## <a name="breadcrumb-bar"></a>Navigačního panelu

 Navigačního panelu v dolní části zobrazení grafu zobrazuje umístění vybraného uzlu v sadě schématu. Pokud je vybraných více položek, bude navigačního panelu prázdné.

## <a name="context-menu"></a>Kontextové nabídky

 Následující tabulka popisuje možnosti, které jsou k dispozici pro všechny uzly na návrhovou plochu zobrazení grafu.

|Možnost|Popis|
|------------|-----------------|
|**Zobrazit v Průzkumníku schématu XML**|Vloží fokus na schéma Průzkumníka a zvýrazňuje uzlu sady schématu.|
|**V zobrazení grafů**|Přepne do zobrazení grafu (šedě).|
|**Generovat ukázkovém kódu XML**|K dispozici pouze pro globální elementy. Generuje a ukázkový soubor XML pro element globální.|
|**Vymazat pracovního prostoru**|Vymaže pracovním prostoru a návrhovou plochu.|
|**Odeberte z pracovního prostoru**|Odebere vybrané uzly z pracovního prostoru a návrhovou plochu.|
|**Odeberte všechny kromě výběr z pracovního prostoru**|Odebere uzly, které nejsou vybrané z pracovního prostoru a návrhovou plochu.|
|**Exportovat Diagram jako obrázek**|Uloží na návrhovou plochu do soubor ve formátu XPS.|
|**Vybrat vše**|Vybere všechny uzly na návrhovou plochu.|
|**Zobrazení kódu**|Otevře se soubor, který obsahuje vybraný uzel v editoru XML. Položky, který je vybraný v **Explorer schématu XML** , vybere se také v editoru XML.|
|**Okno Vlastnosti**|Otevře se **vlastnosti** okno (pokud ještě není otevřený). Toto okno se zobrazí informace o uzlu.|

 Kromě běžných nastavení popsané výše kontextové nabídky pro globální elementy taky obsahuje následující možnosti:

|Možnost|Popis|
|------------|-----------------|
|**Přidání definice typu**|Přidá základní typ diagramu.|
|**Přidejte všechny odkazy na**|Přidá všechny uzly, které odkazují na element a nevykresluje šipky znázorňující vztahy mezi nimi.|
|**Přidání členů do skupiny nahrazení**|Přidá všechny členy skupiny nahrazení. Tato možnost se zobrazí v zobrazení, pokud je element head nebo člen skupiny pro nahrazení.|
|**Generovat ukázkovém kódu XML**|Generuje a ukázkový soubor XML pro element globální.|

 Kromě běžných nastavení popsané výše kontextovou nabídku globální jednoduché a globální komplexní typy taky obsahuje následující možnosti:

|Možnost|Popis|
|------------|-----------------|
|**Přidat základní typ**|Pokud je vybraný typ je odvozen od typu globální, přidá základní typ vybraného typu.|
|**Přidejte všechny odkazy na**|Přidá všechny odkazy vybraného typu. To zahrnuje elementy a atributy vybraného typu, a typy odvozené z vybraného typu.|
|**Přidejte všechny odvozené typy**|Přidá všechny typy, které jsou přímo a nepřímo odvozeny od vybraného typu.|
|**Přidání všech nadřazených**|Přidá všechny typy (základní) nadřazené.|

 Kromě běžných nastavení popsané výše kontextovou nabídku globálních skupin a skupin atributů má také následující možnosti:

|Možnost|Popis|
|------------|-----------------|
|**Přidejte všechny odkazy na**|Přidá všechny uzly, které odkazovat na tuto skupinu a nevykresluje šipky znázorňující vztahy mezi nimi.|
|**Přidat všechny členy**|Přidá všechny členy skupiny a nevykresluje šipky znázorňující vztahy mezi nimi.|

 V addtion běžné možnosti popsané výše kontextovou nabídku globálními atributy taky obsahuje následující možnosti:

|Možnost|Popis|
|------------|-----------------|
|**Přidejte všechny odkazy na**|Přidá všechny uzly, které odkazovat na tuto skupinu a nevykresluje šipky znázorňující vztahy mezi nimi.|

## <a name="properties-window"></a>Vlastnosti – okno

 Pomocí místní nabídky původně otevřete **vlastnosti** okno. Ve výchozím nastavení **vlastnosti** okno se zobrazí v pravém dolním rohu Visual Studio. Při kliknutí na uzel, který se vykreslí v zobrazení obsahu modelu, vlastnosti tento uzel se zobrazí v **vlastnosti** okno.

## <a name="xsd-toolbar"></a>XSD panelu nástrojů

 Tlačítka panelu nástrojů XSD následující jsou povolené, když je aktivní zobrazení grafu.

 ![XML schéma návrháře nástrojů](../xml-tools/media/xsdgraphviewtoolbar.gif "XSDGraphViewToolbar")

|Možnost|Popis|
|------------|-----------------|
|**Nastaví počáteční zobrazení**|Přepne do [spuštění zobrazení](../xml-tools/start-view.md). Toto zobrazení je přístupná pomocí klávesové zkratky: **Ctrl**+**1**.|
|**Nastaví zobrazení modelu obsahu**|Přepne do [modelu zobrazení obsahu](../xml-tools/content-model-view.md). Toto zobrazení je přístupná pomocí klávesové zkratky: **Ctrl**+**2**.|
|**Zobrazit zobrazení grafu**|Přepne do [graf zobrazení](../xml-tools/graph-view.md). Toto zobrazení je přístupná pomocí klávesové zkratky: **Ctrl**+**3**.|
|**Vymazat pracovního prostoru**|Vymaže pracovním prostoru a návrhovou plochu.|
|**Odeberte z pracovního prostoru**|Odebere vybrané uzly z pracovního prostoru a návrhovou plochu.|
|**Odeberte všechny kromě výběr z pracovního prostoru**|Odebere uzly, které nejsou vybrané z pracovního prostoru a návrhovou plochu. Tato možnost je povolená v zobrazení obsahu modelu a zobrazení grafu.|
|**Zleva doprava**|Rozložení v zobrazení grafu se změní na znázornění zleva doprava hierarchické uzlů. Tato možnost je přístupná pomocí klávesové zkratky: **Alt**+**šipku vpravo**.|
|**Zleva doprava.**|Rozložení v zobrazení grafu se změní na znázornění zprava doleva hierarchické uzlů. Tato možnost je přístupná pomocí klávesové zkratky: **Alt**+**šipku vlevo**.|
|**Shora dolů**|Rozložení v zobrazení grafu se změní na znázornění shora dolů hierarchické uzlů. Tato možnost je přístupná pomocí klávesové zkratky: **Alt**+**šipka dolů**.|
|**Zdola nahoru**|Rozložení v zobrazení grafu se změní na znázornění dolní horní hierarchické uzlů. Tato možnost je přístupná pomocí klávesové zkratky: **Alt**+**šipka nahoru**.|

## <a name="panscroll"></a>Pan/posuvníku

 Pomocí posuvníky nebo tím, že se můžete posunete zobrazení návrhovou plochu **Ctrl** klíče při klikněte a přetáhněte myší. Pokud provádíte posun na návrhovou plochu, klikněte na tlačítko a přetáhněte, kurzor se změní na čtyři křížového šipky směřující v čtyři směrech.

## <a name="undoredo"></a>Vrátit/opakovat

 Možnost zpět/opakování je povolena v zobrazení graf pro následující akce:

-   Přidávání do jednoho uzlu pomocí přetahování.

-   Přidání více uzlů z výsledků hledání v Průzkumníku schématu nebo spuštění zobrazení dotazů.

-   Odstranění jednoho nebo více uzlů.

## <a name="zoom"></a>Lupa

 Přiblížení je k dispozici v pravém dolním rohu zobrazení grafu.

 Přiblížení se dá řídit následujícími způsoby:

-   Tím, že se **Ctrl** klíč a otáčí myši kol při ukazatele myši na povrchu zobrazení grafu.

-   Pomocí posuvníku. Posuvník zobrazuje aktuální úroveň přiblížení.

Posuvník přiblížení je plné krytí, pokud vyberte ho, při přechodu nebo používají **Ctrl** kolečka myši pro přiblížení; v jinou dobu je transparentní.

## <a name="xml-editor-integration"></a>Integrace editor XML

 Můžete přepnout přepínat mezi zobrazení grafu a Editor souborů XML tak, že kliknete uzel pomocí místní nabídky zobrazení kódu.

 Pokud provedete změny schématu nastavení v editoru XML, změny budou synchronizovány v zobrazení grafu. Další informace najdete v tématu [integrace s editoru XML](../xml-tools/integration-with-xml-editor.md).

## <a name="see-also"></a>Viz také

- [Návrhové plochy](../xml-tools/xml-schema-designer-workspace.md)