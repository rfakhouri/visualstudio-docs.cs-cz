---
title: Zobrazení návrháře modelu obsahu schématu XML
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: e8db7c7d-31cf-479e-9dcc-299759891795
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b5f275683309d630f147940e97f924496af79179
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62838573"
---
# <a name="content-model-view"></a>Zobrazení modelu obsahu

Zobrazení modelu obsahu poskytuje grafické znázornění schématu místní a globální uzlů a jejich komponent, včetně jednoduché a komplexní typy prvků, skupiny modelů, atributy a skupiny atributů. Komentáře XML a pokyny pro zpracování nelze zobrazit v zobrazení modelu obsahu. Zobrazení modelu obsahu obsahuje dva panely: **pracovní prostor** panel, který obsahuje seznam uzlů v [pracovní prostor návrháře schémat XML](../xml-tools/xml-schema-designer-workspace.md)a návrhovou plochu, ve kterém uvidíte modelu obsahu schématu uzly, které jsou vybrány v **pracovní prostor** panelu. Zobrazení modelu obsahu také obsahuje panel nástrojů Návrhář schémat XML a panelu navigace s popisem cesty.

Na následujícím obrázku **pracovní prostor** panel obsahuje šest uzlů schémat. `purchaseOrder` v při výběru uzlu **pracovní prostor** panelu a zobrazí se v návrhové ploše.

![Zobrazení návrháře modelu obsahu schématu XML](../xml-tools/media/xsddesigner_contentmodelview.gif)

## <a name="workspace-panel"></a>Panelu pracovního prostoru

Po přidání uzlů do pracovního prostoru, zobrazí se seznam uzlů v **pracovní prostor** panel ovládacího prvku zobrazení modelu obsahu. Když vyberete uzly v **pracovní prostor** panelu, zobrazí se na povrchu návrhu zobrazení modelu obsahu. Odstranění uzlů z pracovního prostoru, pomocí tohoto panelu nástrojů návrháře XSD **pracovní prostor** nabídky panelu klikněte pravým tlačítkem, nebo **odstranit** klíč.

Informace o přidání uzlů najdete v tématu v části "Přidání uzlů do pracovní prostor" [pracovní prostor návrháře schémat XML](../xml-tools/xml-schema-designer-workspace.md).

## <a name="design-surface"></a>Návrhová plocha

Vybrání uzlu v **pracovní prostor** panel, přidá se do zobrazení modelu obsahu návrhovou plochu, kde najdete podrobnosti o uzlu.

Model obsahu uzlu je reprezentován rozšíření grafické stromu s prvky a atributy vyskytující se jako uzly stromu. Ve výchozím nastavení je rozšířit jenom jedna úroveň. Další informace, jako je například tvůrce, názvy typů, skupiny a další kontejnery jsou umístěny v svislá čára (při rozbalení) podél elementy a atributy, které jsou uzavřete. Když dvakrát kliknete na svislý pruh, stane se vodorovný a sbalí stromu. Když dvakrát kliknete na vodorovný pruh, stane se svislé a strom roste směrem. Výběr svislá čára vybere všechny uzly v kontejneru. Rozšíření se zobrazí na pravé straně uzlu v případě, že element může být rozbalená nebo sbalená.

Pokud návrhové ploše je prázdné, editoru XML **Průzkumníka schémat XML**, a jsou uvedeny vodoznak. *Vodoznak* seznam obsahuje odkazy na všechna zobrazení návrháře XSD. Pokud sadě schémat obsahuje chyby, zobrazí se na konci seznamu následující text: "K zobrazení a opravte chyby v sadě pomocí seznamu chyb."

## <a name="breadcrumb-bar"></a>Navigační panel

Na panelu navigace s popisem cesty v dolní části zobrazení modelu obsahu zobrazuje umístění vybraného uzlu v sadě schémat.

## <a name="context-menus"></a>Místní nabídky

Když kliknete pravým tlačítkem na položku na návrhovou plochu nebo **pracovní prostor** panelu, zobrazí se kontextová nabídka. Následující tabulka popisuje možnosti, které jsou k dispozici pro zobrazení modelu obsahu návrhovou plochu.

|Možnost|Popis|
|-|-----------------|
|**Zobrazit v Průzkumníkovi schémat XML**|Umístí fokus na Průzkumník schémat a zvýrazní schématu sady uzlu.|
|**Zobrazit v zobrazení grafu**|Přepne do zobrazení grafu.|
|**Generovat ukázkový soubor XML**|K dispozici pouze pro globální prvky. Generuje ukázkový soubor XML pro prvek globální.|
|**Zobrazit dokumentaci**|Zobrazí nebo skryje obsah uzlu poznámky a dokumentaci.|
|**Exportovat Diagram jako obrázek**|Uloží soubor ve formátu XPS návrhové ploše.|
|**Zobrazit kód**|Otevře soubor, který obsahuje vybraný uzel v editoru XML. Položky vybrané v **Průzkumníka schémat XML** je také vybraná v editoru XML.|
|**Okno Vlastnosti**|Otevře **vlastnosti** okna (pokud ještě není otevřený). Toto okno zobrazuje informace o uzlu.|

Následující tabulka popisuje možnosti, které jsou k dispozici pro **pracovní prostor** panelu.

|Možnost|Popis|
|-|-----------------|
|**Zobrazit v Průzkumníkovi schémat XML**|Umístí fokus na Průzkumník schémat a zvýrazní schématu sady uzlu.|
|**Zobrazit v zobrazení grafu**|Přepne do zobrazení grafu.|
|**Vymazat pracovní prostor**|Vymaže pracovní prostor a návrhovou plochu.|
|**Odebrat z pracovního prostoru**|Odebere vybrané uzly z pracovního prostoru a návrhovou plochu.|
|**Odeberte všechny kromě výběru z pracovního prostoru**|Odebere uzly, které nejsou vybrané z pracovního prostoru a návrhovou plochu.|
|**Generovat ukázkový soubor XML**|K dispozici pouze pro globální prvky. Generuje ukázkový soubor XML pro prvek globální.|
|**Vybrat vše**|Vybere všechny uzly v **pracovní prostor** panelu.|
|**Zobrazit kód**|Otevře soubor, který obsahuje vybraný uzel v editoru XML. Položky vybrané v **Průzkumníka schémat XML** je také vybraná v editoru XML.|
|**Okno Vlastnosti**|Otevře **vlastnosti** okna (pokud ještě není otevřený). Toto okno zobrazuje informace o uzlu.|

## <a name="properties-window"></a>Vlastnosti – okno

Prvním spuštění pomocí nabídky (objektu context) klikněte pravým tlačítkem **vlastnosti** okna. Ve výchozím nastavení **vlastnosti** okno se zobrazí v pravém dolním rohu sady Visual Studio. Po kliknutí na uzel, který se vykreslí v zobrazení modelu obsahu, vlastnosti uzlu se zobrazují v **vlastnosti** okna.

## <a name="xsd-designer-toolbar"></a>Panel nástrojů návrháře XSD

Při aktivním zobrazení modelu obsahu jsou povoleny následující tlačítka panelu nástrojů návrháře XSD.

![Panel nástrojů návrháře schémat XML](../xml-tools/media/xsdcontentmodelviewtoolbar.gif)

|Možnost|Popis|
|-|-----------------|
|**Ukázat počáteční zobrazení**|Přepne [počáteční zobrazení](../xml-tools/start-view.md). Toto zobrazení je přístupný pomocí klávesové zkratky: **Ctrl**+**1**.|
|**Ukázat zobrazení modelu obsahu**|Přepne [zobrazení modelu obsahu](../xml-tools/content-model-view.md). Toto zobrazení je přístupný pomocí klávesové zkratky: **Ctrl**+**2**.|
|**Ukázat zobrazení grafu**|Přepne [grafu zobrazení](../xml-tools/graph-view.md). Toto zobrazení je přístupný pomocí klávesové zkratky: **Ctrl**+**3**.|
|**Vymazat pracovní prostor**|Vymaže pracovní prostor a návrhovou plochu.|
|**Odebrat z pracovního prostoru**|Odebere vybrané uzly z pracovního prostoru a návrhovou plochu.|
|**Odeberte všechny kromě výběru z pracovního prostoru**|Odebere uzly, které nejsou vybrané z pracovního prostoru a návrhovou plochu.|
|**Zobrazit dokumentaci**|Zobrazí nebo skryje obsah uzlu poznámky a dokumentaci.|

## <a name="panscroll"></a>Posun/posuvníku

S použitím se posuvníky nezobrazovaly nebo tak, že se můžete pohybovat návrhovou plochu **Ctrl** klávesu klikněte a přetáhněte myší. Při posouvání návrhové plochy, klikněte na tlačítko a přetáhněte ukazatel se změní na čtyři překřížené šipky směřující do čtyř směrů.

## <a name="undoredo"></a>Zpět/znovu

Funkce Zpět/znovu je povolená v zobrazení modelu obsahu pro následující akce:

- Přidání jednoho uzlu pomocí přetahování.

- Přidání více uzlů z výsledků hledání v Průzkumníkovi schémat.

- Přidávání uzlů ze zobrazení spuštění.

- Odstraňuje se jeden nebo více uzlů.

## <a name="zoom"></a>Lupa

Přiblížení je k dispozici v pravém dolním rohu zobrazení modelu obsahu.

Zvětšení lze řídit následujícími způsoby:

- Tím, že se **Ctrl** klíč a zprovozňování myši kol, když myš je přesunutá na plochu zobrazení modelu obsahu.

- Pomocí posuvníku. Posuvník zobrazuje aktuální úroveň přiblížení.

Posuvník přiblížení je neprůhledný, když vyberte ho, najeďte myší nad ním nebo použijte **Ctrl** kolečkem myši pro přiblížení; v jinou dobu, je transparentní.

## <a name="xml-editor-integration"></a>Integrace editoru XML

Můžete přepínat mezi **XSD návrháře** a editor souborů XML pomocí nabídky klikněte pravým tlačítkem (objektu context).

Pokud provedete změny ve schématu se nastavují v editoru XML změny jsou synchronizovány do zobrazení modelu obsahu. Další informace najdete v tématu [integrace s editorem XML](../xml-tools/integration-with-xml-editor.md).

## <a name="see-also"></a>Viz také:

- [Pracovní prostor Návrháře schémat XML](../xml-tools/xml-schema-designer-workspace.md)