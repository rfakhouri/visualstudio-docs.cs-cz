---
title: Průzkumník schémat XML – prohledání sady schémat
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: ec1395e0-d03c-4130-810d-f2db656937bd
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 898b79e53773c09d60e32a3ef262346b0371d2af
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2019
ms.locfileid: "68926806"
---
# <a name="search-the-schema-set"></a>Hledání v sadě schémat

**Průzkumník schémat XML** umožňuje vyhledat sadu schémat následujícími způsoby:

- Hledání klíčových slov

- Hledání specifické pro schéma.

## <a name="keyword-search"></a>Hledání klíčových slov

Hledání klíčových slov provedete tak, že do textového pole **Hledat schemaSet** v panelu nástrojů **Průzkumníka schémat XML** zadáte podřetězec.

![Hledání klíčového slova Průzkumníka schémat XML](../xml-tools/media/schemaexplorersearch.gif)

**Průzkumník schémat XML** vyhledá v sadě schémat následující atributy:

- Všechny `name` atributy `ref` nebo, které odpovídají zadanému klíčovému slovu. Můžete najít prvky, atributy, typy a tak dále podle názvu.

- `schemaLocation` Atributy příkazů include

- `namespace` Atributy příkazů import.

## <a name="schema-specific-search"></a>Hledání specifické pro schéma

**Průzkumník schémat XML** také obsahuje Vestavěná hledání, ke kterým můžete přistupovat pomocí nabídky kontextu (pravého kliknutím) v **Průzkumníku schémat XML**. Další informace o dostupných kontextových nabídkách naleznete v tématu [kontextové nabídky](../xml-tools/context-menus-xml-schema-explorer.md). Můžete také provést hledání specifické pro schéma v zobrazení Start; Další informace najdete v části Podrobnosti o sadě schémat v tématu [spuštění zobrazení](../xml-tools/start-view.md) .

## <a name="display-and-navigate-search-results"></a>Zobrazení a navigace ve výsledcích hledání

Po dokončení hledání se podokno souhrnné výsledky přidá na panel nástrojů s výsledky hledání. Výsledky hledání jsou také zvýrazněny v **Průzkumníku schémat XML** a označeny značkami na svislém posuvníku. Výsledky hledání můžete procházet pomocí možnosti **Přejít na další výsledek hledání** a **Přejít na předchozí** tlačítka výsledků hledání v podokně souhrnné výsledky hledání na panelu nástrojů **Průzkumníka schémat XML** . pomocí kláves klávesnice **F3** a **SHIFT**+**F3**nebo kliknutím na značky na posuvníku.

Výsledky hledání můžete přidat do pracovního prostoru kliknutím na tlačítko **Přidat zvýrazněné uzly do pracovního prostoru** v podokně souhrnné výsledky.

![Výsledek hledání v Průzkumníkovi schémat XML](../xml-tools/media/schemaexplorersearchresult.gif)

## <a name="clear-search-results"></a>Vymazat výsledky hledání

Chcete-li vymazat výsledky hledání, klikněte na tlačítko **x** v podokně souhrnné výsledky na panelu nástrojů hledání v **Průzkumníkovi schémat XML** .

## <a name="see-also"></a>Viz také:

- [Průzkumník schémat XML](../xml-tools/xml-schema-explorer.md)