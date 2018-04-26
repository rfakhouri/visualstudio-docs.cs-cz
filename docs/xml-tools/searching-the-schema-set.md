---
title: Průzkumník schématu XML - hledání sadu schématu
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: ec1395e0-d03c-4130-810d-f2db656937bd
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 8b3aa631ab673f7b6d679cbe39459ecb9a5fbbaf
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="searching-the-schema-set"></a>Hledání sadu schématu

Průzkumník schématu XML umožňuje hledání schéma nastavit následujícími způsoby:

-   Hledání klíčových slov.

-   Hledání podle schématu.

## <a name="keyword-search"></a>Hledání klíčových slov

 Provádět – klíčové slovo hledání tak, že zadáte podřetězce v **vyhledávání SchemaSet** textového pole panelu nástrojů Průzkumníka schématu XML.

 ![Hledání klíčových slov Explorer schématu XML](../xml-tools/media/schemaexplorersearch.gif "SchemaExplorerSearch")

 Průzkumník schématu XML vyhledá schéma nastavení pro následující atributy:

-   Všechny `name` nebo `ref` atributy, které odpovídají zadaným klíčovým slovem. Umožňuje najít prvky, atributy, typy a tak dále, podle názvu.

-   `schemaLocation` Atributy zahrnovat příkazy.

-   `namespace` Atributy příkazy pro import.

## <a name="schema-specific-search"></a>Schéma konkrétní vyhledávání

 Průzkumník schématu XML obsahuje také integrované hledání, kterým můžete přistupovat pomocí místní nabídky Průzkumníku schématu XML. Další informace o dostupných kontextové nabídky, najdete v části [kontextové nabídky](../xml-tools/context-menus-xml-schema-explorer.md). Také můžete provádět vyhledávání specifické schématu ze zobrazení Start; Další informace najdete v části "Schématu nastavit podrobnosti" v [spuštění zobrazení](../xml-tools/start-view.md) tématu.

## <a name="displaying-and-navigating-search-results"></a>Zobrazení a navigace výsledky hledání

 Po dokončení vyhledávání v podokně výsledků souhrnu se přidá do panelu nástrojů ve výsledcích hledání. Výsledky hledání jsou také zvýrazněných v Průzkumníku schématu XML a označeny rysky svislém posuvníku. Výsledky hledání můžete procházet pomocí **přejít na další výsledek hledání** a **přejít na předchozí výsledek hledání** tlačítka v podokně souhrnu výsledků nástrojů Explorer schématu XML; pomocí klávesnice klíčů F3 a Shift + F3; nebo kliknutím značek na posuvníku.

 Výsledky hledání můžete přidat do pracovního prostoru kliknutím **přidat zvýrazněné uzly do pracovního prostoru** stisknutí tlačítka na panelu shrnutí výsledků.

 ![Výsledek hledání Explorer schématu XML](../xml-tools/media/schemaexplorersearchresult.gif "SchemaExplorerSearchResult")

## <a name="clearing-search-results"></a>Výsledky hledání Probíhá vymazání

 Pokud chcete vymazat výsledky hledání, klikněte na tlačítko **x** na podokně shrnutí výsledků hledání Explorer schématu XML panelu nástrojů zobrazí tlačítko.

## <a name="see-also"></a>Viz také

- [Průzkumník schémat XML](../xml-tools/xml-schema-explorer.md)