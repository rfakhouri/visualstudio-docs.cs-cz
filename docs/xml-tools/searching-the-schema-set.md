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
ms.openlocfilehash: c110344499281243628d633d005506af5cd801d0
ms.sourcegitcommit: d1824ab926ebbc4a8057163e0edeaf35cec57433
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2018
---
# <a name="search-the-schema-set"></a>Hledání sadu schématu

**Explorer schématu XML** umožňuje hledání schéma nastavit následujícími způsoby:

-   Hledání klíčových slov.

-   Hledání podle schématu.

## <a name="keyword-search"></a>Hledání klíčových slov

 Provádět – klíčové slovo hledání tak, že zadáte podřetězce v **vyhledávání SchemaSet** textovém poli **Explorer schématu XML** panelu nástrojů.

 ![Hledání klíčových slov Explorer schématu XML](../xml-tools/media/schemaexplorersearch.gif "SchemaExplorerSearch")

 **Explorer schématu XML** vyhledá schéma nastavení pro následující atributy:

-   Všechny `name` nebo `ref` atributy, které odpovídají zadaným klíčovým slovem. Prvky, atributy, typy a tak dále, můžete najít podle názvu.

-   `schemaLocation` Atributy zahrnovat příkazy.

-   `namespace` Atributy příkazy pro import.

## <a name="schema-specific-search"></a>Schéma konkrétní vyhledávání

 **Explorer schématu XML** také zahrnuje integrované hledání, kterým můžete přistupovat pomocí místní nabídku **Explorer schématu XML**. Další informace o dostupných kontextové nabídky, najdete v části [kontextové nabídky](../xml-tools/context-menus-xml-schema-explorer.md). Také můžete provádět vyhledávání specifické schématu ze zobrazení Start; Další informace najdete v části "Schématu nastavit podrobnosti" v [spuštění zobrazení](../xml-tools/start-view.md) tématu.

## <a name="display-and-navigate-search-results"></a>Zobrazení a přejděte výsledky hledání

 Po dokončení vyhledávání v podokně výsledků souhrnu se přidá do panelu nástrojů ve výsledcích hledání. Výsledky hledání jsou také vyznačené na **Explorer schématu XML** a označeny rysky svislém posuvníku. Výsledky hledání můžete procházet pomocí **přejít na další výsledek hledání** a **přejít na předchozí výsledek hledání** tlačítka v podokně shrnutí výsledků **Explorer schématu XML**nástrojů; pomocí klávesy **F3** a **Shift**+**F3**; nebo klepnutím na dílky na posuvníku.

 Výsledky hledání můžete přidat do pracovního prostoru kliknutím **přidat zvýrazněné uzly do pracovního prostoru** stisknutí tlačítka na panelu shrnutí výsledků.

 ![Výsledek hledání Explorer schématu XML](../xml-tools/media/schemaexplorersearchresult.gif "SchemaExplorerSearchResult")

## <a name="clear-search-results"></a>Vymazat výsledky hledání

 Pokud chcete vymazat výsledky hledání, klikněte na tlačítko **x** tlačítko v podokně souhrnu výsledků **Explorer schématu XML** vyhledávání panelu nástrojů.

## <a name="see-also"></a>Viz také

- [Průzkumník schémat XML](../xml-tools/xml-schema-explorer.md)