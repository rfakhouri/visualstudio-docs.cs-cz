---
title: Řazení, filtrování a seskupování v Průzkumník schémat XML
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 4a914de0-9ffc-4526-9603-92e460e52513
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 740fd46d453a6e6a51285d418374d036d83bc598
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62808103"
---
# <a name="sorting-filtering-and-grouping-xml-schema-explorer"></a>Řazení, filtrování a seskupování (Průzkumník schémat XML)

Toto téma popisuje možnosti, které jsou k dispozici prostřednictvím **řazení, filtrování a možnosti seskupení** nabídce **Průzkumníka schémat XML** nástrojů.

## <a name="filter-options"></a>Možnosti filtrování

 Jsou k dispozici následující možnosti filtru. Ve výchozím nastavení **zobrazit obory názvů** a **zobrazit soubory schémat** jsou vybrané možnosti.

- **Zobrazit obory názvů**.

- **Zobrazit soubory schémat**.

- **Zobrazit tvůrce (pořadí/volba/all)**.

## <a name="sorting-options"></a>Možnosti řazení

 Jsou k dispozici následující možnosti řazení. Výchozí hodnota je **řazení podle typu**. **Řadit podle** možnosti se nevztahují na soubory a obory názvů.

- **Seřadit podle typu**.

- **Seřadit podle názvu**.

- **Zdokumentujte pořadí**.

### <a name="sort-by-type"></a>Seřadit podle typu

 Když **řazení podle typu** je vybraná možnost, jsou globální uzly seřazeny v uvedeném pořadí. Uzly jsou pak seřazená podle abecedy v rámci jednotlivých skupin.

1. `import` uzly.

2. `include` uzly.

3. `redefine` uzly.

4. `attribute` uzly.

5. `attributeGroup` uzly.

6. `complexType` uzly.

7. `simpleType` uzly.

8. `element` uzly.

9. `group` uzly.

### <a name="sort-by-name"></a>Seřadit podle názvu

 Když **seřadit podle názvu** je vybraná možnost, jsou globální uzly seřazeny v následujícím pořadí:

1. `import` uzly (v abecedním pořadí oborů názvů).

2. `include` uzly (v abecedním pořadí podle `schemaLocation` atributy).

3. `redefine` uzly (v abecedním pořadí podle `schemaLocation` atributy).

4. Jiné globální uzly v abecedním pořadí.

### <a name="document-order"></a>Pořadí dokumentů

 **Pořadí dokumentů** možnost je k dispozici, když **zobrazit soubory schémat** je vybraná možnost. Když **pořadí dokumentů** je vybraná globální uzly jsou zobrazeny v pořadí, v jakém jsou uvedeny v souboru schématu.

## <a name="persisting-sortfilter-options"></a>Zachování možnosti řazení a filtrování

 Řazení, filtrování a možnosti seskupení jsou uložena do registru pro každého uživatele, bez ohledu na to, které řešení nebo soubory byly otevřeny Pokud byla nastavení změněna.