---
title: Kontextové nabídky v Průzkumníku schématu XML
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: reference
ms.assetid: 42ab17ca-b8c1-40d7-beda-d033f66fe874
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: faf28fc44acd530cbc379c4a400c3488f98405ea
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2018
ms.locfileid: "34477818"
---
# <a name="context-menus-xml-schema-explorer"></a>Kontextové nabídky (Explorer schématu XML)

Následující položky kontextové nabídky se používají k provádění schématu konkrétní hledání a dalších operací.

## <a name="node-type-schema-set"></a>Typ uzlu: schéma nastavení

Následující tabulka popisuje možnosti, které jsou dostupné pro schéma nastavte uzel.

|Možnost|Popis|
|------------|-----------------|
|**Zobrazit nejpravděpodobnější kořenových elementů**|Vyhledá a označuje všechny globální prvky, které nejsou na něj odkazovat z globální prvky výjimkou sama sebe.|
|**Zobrazit globální typy**|Vyhledá a označuje všechny globální typy v sadě schématu.|
|**Zobrazit globální prvky**|Vyhledá a označuje všechny globální elementy ve schématu sady.|
|**Okno Vlastnosti**|Otevře se **vlastnosti** okno (pokud ještě není otevřený). Toto okno se zobrazí informace o uzlu.|

## <a name="node-type-namespace"></a>Typ uzlu: Namespace
 Následující tabulka popisuje možnosti, které jsou k dispozici pro uzlu oboru názvů.

|Možnost|Popis|
|------------|-----------------|
|**Zobrazit všechny příchozí odkazy**|Vyhledá a označuje soubory, které importovat vybraný obor názvů.|
|**Zobrazit všechny odchozí odkazy**|Pro každý soubor v oboru názvů vybrané najde a klade důraz následující:<br /><br /> -Všechny obory názvů, kterou se odkazuje v importovat příkazy bez `schemaLocation` atribut.<br />-Všechny soubory v oborech názvů než vybrané ve stanoveném `schemaLocation` v importu a zahrnují příkazy.|
|**Zobrazit globální typy**|Vyhledá a označuje všechny globální typy v vybraný obor názvů.|
|**Zobrazit globální prvky**|Vyhledá a označuje všechny globální elementy ve vybrané obor názvů.|
|**Okno Vlastnosti**|Otevře se **vlastnosti** okno (pokud ještě není otevřený). Toto okno se zobrazí informace o uzlu.|

## <a name="node-type-file"></a>Typ uzlu: soubor
 Následující tabulka popisuje možnosti, které jsou k dispozici pro uzel souboru.

|Možnost|Popis|
|------------|-----------------|
|**Zobrazit všechny příchozí odkazy**|Najde a všechny soubory, které určují vybraného souboru v klade důraz `schemaLocation` atributy jejich příkazy include a import.|
|**Zobrazit všechny odchozí odkazy**|Vyhledá a upozorňuje na následující:<br /><br /> -Import všech oborů názvů zadaný v oboru názvů atributy všechny příkazy, které nemají `schemaLocation` atribut.<br />-Všechny soubory v zadané `schemaLocation` atributy všech importovat a zahrnují příkazy.|
|**Zobrazit globální typy**|Vyhledá a označuje všechny globální typy v tomto souboru.|
|**Zobrazit globální prvky**|Vyhledá a označuje všechny globální prvky v tomto souboru.|
|**Zobrazení kódu**|Otevře se soubor, který obsahuje vybraný uzel v editoru XML. Položky vybrané v Průzkumníku schématu XML bude také vybrána v editoru XML.|
|**Okno Vlastnosti**|Otevře se **vlastnosti** okno (pokud ještě není otevřený). Toto okno se zobrazí informace o uzlu.|

## <a name="all-global-node-types"></a>Všechny typy globální uzlu
 Následující tabulka popisuje možnosti, které jsou k dispozici pro všechny uzly globální.

|Možnost|Popis|
|------------|-----------------|
|**V zobrazení grafů**|Otevře zobrazení grafu. Pokud vybraný uzel není v pracovním prostoru, přidá do pracovního prostoru a vybírá uzel.|
|**V zobrazení modelu obsahu**|Otevře zobrazení modelu obsahu. Pokud vybraný uzel není v pracovním prostoru, přidá do pracovního prostoru a vybírá uzel.|
|**Zobrazení kódu**|Otevře se soubor, který obsahuje vybraný uzel v editoru XML. Položky vybrané v Průzkumníku schématu XML bude také vybrána v editoru XML.|
|**Okno Vlastnosti**|Otevře se **vlastnosti** okno (pokud ještě není otevřený). Toto okno se zobrazí informace o uzlu.|

## <a name="node-type-element"></a>Typ uzlu: Element
 Kromě možností globální uzlu popsané výše kontextovou nabídku uzly elementu obsahuje následující možnosti:

|Možnost|Popis|
|------------|-----------------|
|**Přejděte do definice typu**|Přejde na definici typu vybraného prvku. To se vztahuje, když typ, který se používá pro element je typu globální.|
|**Přejděte do původní elementu**|Pro element odkazy přejde do skutečné definice elementu.|
|**Zobrazit všechny odkazy**|Pro globální prvky, najde a označuje všechny odkazy (elementy, které mají `ref="selectedElement"`) na vybraný prvek.|
|**Zobrazit členy substituční skupiny.**|Oznámení substituční skupiny, vyhledá a zvýrazňuje všechny elementy, které jsou členy skupiny nahrazení, který je členem je vybraný prvek. Ukazuje to přímé a nepřímé účastníky.|
|**Zobrazit substituční skupiny oznámení**|Pro globální prvky, které jsou členy skupiny nahrazení, vyhledá a označuje všechny přímé a nepřímé oznámení pro vybraný prvek, například následující:<br /><br /> -A nahrazování head skupiny zadáno u vybraného elementu.<br />-A nahrazování head skupiny zadané v jeho element head.|
|**Generovat ukázkovém kódu XML**|K dispozici pouze pro globální elementy. Generuje a ukázkový soubor XML pro element globální.|

## <a name="node-type-global-types"></a>Typ uzlu: globální typy
 Kromě možností globální uzlu popsané výše kontextové nabídky pro uzly globální typ obsahuje následující možnosti:

|Možnost|Popis|
|------------|-----------------|
|**Zobrazit základní typ**|Pokud je vybraný typ je odvozen od typu globální, přejde na základní typ vybraného typu.|
|**Zobrazit všechny odkazy**|Vyhledá a označuje všechny odkazy k vybranému typu. To zahrnuje elementy a atributy vybraného typu a typy odvozené z vybraného typu.|
|**Zobrazit všechny odvozené typy**|Vyhledá a označuje všechny typy, které jsou přímo a nepřímo odvozeny od vybraného typu.|
|**Zobrazení všech nadřazených**|Zobrazit všechny typy nadřazené (základní).|

## <a name="node-type-attribute"></a>Typ uzlu: atribut
 Kromě možností globální uzlu popsané výše kontextové nabídky pro uzly atribut obsahuje následující možnosti:

|Možnost|Popis|
|------------|-----------------|
|**Přejděte do definice typu**|Pokud typ, který se používá pro atribut typu globální, přejde do definice typu vybraného atributu.|
|**Přejděte do atribut původní**|Pro atribut odkazy přejde do skutečné definice atributu.|
|**Zobrazit všechny odkazy**|Globálními atributy, vyhledá a zvýrazňuje všechny odkazy (Další atributy, které mají `ref="selectedAttribute"`) pro vybraný atribut.|

## <a name="node-type-attribute-group"></a>Typ uzlu: Skupina atributů
 Kromě možností globální uzlu popsané výše kontextové nabídky pro uzly skupiny atribut obsahuje následující možnosti:

|Možnost|Popis|
|------------|-----------------|
|**Přechod na definici**|Odkazy přejde do skutečné definice atributu.|
|**Zobrazit všechny členy**|Vyhledá a označuje všechny členy skupiny atributů.|
|**Zobrazit všechny odkazy**|Vyhledá a zvýrazňuje všechny odkazy (atribut skupiny, které mají `ref="selectedAttributeGroup"`) ke skupině vybraného atributu.|

## <a name="node-type-named-group"></a>Typ uzlu: s názvem skupiny
 Kromě možností globální uzlu popsané výše kontextové nabídky pro uzly s názvem skupiny obsahuje následující možnosti:

|Možnost|Popis|
|------------|-----------------|
|**Přechod na definici**|Odkazy přejde do skutečné definice atributu.|
|**Zobrazit všechny členy**|Vyhledá a zvýrazňuje všichni členové s názvem skupiny.|
|**Zobrazit všechny odkazy**|Vyhledá a zvýrazňuje všechny odkazy (skupiny, které mají `ref="selectedGroup"`) do vybrané skupiny.|

## <a name="see-also"></a>Viz také

- [Průzkumník schémat XML](../xml-tools/xml-schema-explorer.md)
- [Hledání sadu schématu](../xml-tools/searching-the-schema-set.md)