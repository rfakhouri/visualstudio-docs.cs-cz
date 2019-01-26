---
title: 'Postupy: Vyhodnocení výrazu XPath'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: 159ba4ef-75e4-4ac8-80dc-e064e0bec345
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9ab895bb10c9f1b70ba103aebeb0ad83cdb84418
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55000975"
---
# <a name="how-to-evaluate-an-xpath-expression"></a>Postupy: Vyhodnocení výrazu XPath

Můžete si vyzkoušet výrazy XPath s **QuickWatch** dialogové okno. Výraz XPath musí být platný podle doporučení W3C XPath 1.0. Aktuální kontext XSLT – to znamená, `self::node()` uzlu v **lokální** okno – poskytuje kontext vyhodnocení výrazu XPath.

 Následující seznam popisuje, jaké funkce jsou podporovány při vyhodnocování výrazu XPath:

-   Podporují se předdefinované funkce XPath.

-   Integrované funkce XSLT nejsou podporovány.

-   Uživatelem definované funkce nejsou podporovány.

> [!NOTE]
> Následující postup používá *belowAvg.xsl* a *books.xml* souborů z doručené pošty [názorný postup: Ladění stylů XSLT](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md) tématu.

## <a name="to-evaluate-an-xpath-expression"></a>Vyhodnocení výrazu XPath

1.  Vložit zarážku na `xsl:if` počáteční značka.

2.  Klikněte na tlačítko **ladění XSL** tlačítko na panelu nástrojů editoru XML.

     Ladicí program se spustí a dojde k porušení `xsl:if` značky.

3.  Klikněte pravým tlačítkem a vyberte **QuickWatch**.

     **QuickWatch** se zobrazí dialogové okno.

4.  Zadejte `./price/text()` v **výraz** pole **QuickWatch** dialogové okno a klikněte na tlačítko **přehodnotit**.

     Ceny pro aktuální uzel knihy se zobrazí v **hodnotu** pole.

5.  Změnit výraz XPath, který má `./price/text() < $bookAverage` a klikněte na tlačítko **přehodnotit**.

     **Hodnotu** poli se zobrazí, že vyhodnocení výrazu XPath má `true`.

## <a name="see-also"></a>Viz také:

- [Ladění XSLT](../xml-tools/debugging-xslt.md)