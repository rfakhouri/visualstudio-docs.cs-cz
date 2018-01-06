---
title: "Hledání sadu schématu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec1395e0-d03c-4130-810d-f2db656937bd
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: a61221f8349064305bbd925016121da01d52515b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="searching-the-schema-set"></a>Hledání sadu schématu
Průzkumník schématu XML umožňuje hledání schéma nastavit následujícími způsoby:  
  
-   Hledání klíčových slov.  
  
-   Hledání podle schématu.  
  
## <a name="keyword-search"></a>Hledání klíčových slov  
 Provádět – klíčové slovo hledání tak, že zadáte podřetězce v **vyhledávání SchemaSet** textového pole panelu nástrojů Průzkumníka schématu XML.  
  
 ![Hledání klíčových slov Explorer schématu XML](../xml-tools/media/schemaexplorersearch.gif "SchemaExplorerSearch")  
  
 Průzkumník schématu XML vyhledá schéma nastavení pro následující:  
  
-   Všechny `name` nebo `ref` atributy, které odpovídají zadaným klíčovým slovem. Umožňuje najít prvky, atributy a typy, a tak dále podle názvu.  
  
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
 [Průzkumník schémat XML](../xml-tools/xml-schema-explorer.md)