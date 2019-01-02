---
title: Dialogové okno Schémata XML
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: reference
ms.assetid: 0271fa26-2205-49bd-96e0-ae1441571808
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: b1f8f4824d18618b40ad4073dc6be0c81d9aba37
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53835203"
---
# <a name="xml-schemas-dialog-box"></a>Dialogové okno schémata XML

**Schémat XML** se používá dialogové okno pro výběr které schématu definice jazyk (XSD) schématu XML pro přidružení k dokumentu XML. Můžete vybrat schéma z mezipaměti schémat nebo zadejte schéma, které se nenachází v mezipaměti. Vybrané schémata jsou považovány za součást této sadě schémat. Sadě schémat se používá technologie IntelliSense a také ověření dokumentu XML.

Můžete přistupovat **schémat XML** dialogové okno kliknutím **schémata** tlačítka v okně Vlastnosti dokumentu, nebo výběrem **schémata** z **XML** nabídky.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní
 **Použití**

 Vyberte, jak má být použita schématu XML.

-   **Automatické**. Toto schéma není používán aktuální dokument, ale je k dispozici pro automatické přidružení. Pokud dokument XML deklaruje obor názvů, který odpovídá `targetNamespace` tohoto schématu schématu bude automaticky přiřazen a je zahrnuté v sadě schémat.

-   **Použít tohle schéma**. Toto schéma používá aktuální dokument. Uživatel má explicitně požadována, že kliknete na tomto sloupci používat toto schéma nebo schématu byl automaticky k podle odpovídající `targetNamespace`.

-   **Nepoužívat vybraná schémata**. Toto schéma není používán aktuální dokument i v případě schématu nemá odpovídající `targetNamespace`. Toto nastavení může být užitečné při řešení konfliktů, pokud existuje více než jedna verze stejného schématu v mezipaměti schémat nebo řešení.

**Target Namespace**

Zobrazí související s XML schématu cílový obor názvů.

**Název souboru**

Zobrazuje název souboru schématu XML.

**Add**

Otevře **otevřít schéma XSD** dialogové okno, které vám umožní vybrat další schémata pro přidání do sady schémat. Při přidávání schématu do schématu nastavit **použití** nastavena na hodnotu sloupce **použít tohle schéma**.

**odebrat**

Odebere aktuálně vybrané schéma v sadě schémat. Tato operace odebere schéma z mezipaměti schémat v paměti, ale ne ze systému souborů.

## <a name="see-also"></a>Viz také:

- [Součásti editoru XML](../xml-tools/xml-editor-components.md)
- [Postupy: Výběr schémat XML pro použití](../xml-tools/how-to-select-the-xml-schemas-to-use.md)
- [Mezipaměti schémat](../xml-tools/schema-cache.md)