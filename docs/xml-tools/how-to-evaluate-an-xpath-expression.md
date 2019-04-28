---
title: Vyhodnocení výrazu XPath při ladění
ms.date: 03/05/2019
ms.topic: conceptual
ms.assetid: 159ba4ef-75e4-4ac8-80dc-e064e0bec345
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1585b54d084e3471583f9388d63f5c17e65fc3a7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63002093"
---
# <a name="evaluate-xpath-expressions"></a>Vyhodnocení výrazů XPath

Pomocí můžete vyhodnotit výrazy XPath **QuickWatch** okno během ladění. Výraz XPath musí být platný podle doporučení W3C XPath 1.0. Aktuální kontext XSLT (to znamená, `self::node()` uzlu v **lokální** okno) poskytuje kontext vyhodnocení výrazu XPath.

Při vyhodnocování výrazu XPath:

- Podporují se předdefinované funkce XPath.

- Předdefinované funkce XSLT a uživatelem definované funkce nejsou podporovány.

> [!NOTE]
> Ladění XSLT je k dispozici pouze v edici Enterprise sady Visual Studio.

## <a name="evaluate-an-xpath-expression"></a>Vyhodnocení výrazu XPath

Následující postup používá *níže average.xsl* a *books.xml* souborů z doručené pošty [názorný postup: Ladění stylů XSLT](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md#sample-files) stránky.

1. Vložit zarážku na `xsl:if` počáteční značka.

2. Chcete-li spustit ladění, zvolte **XML** > **spustit ladění XSLT** na řádku nabídek (nebo stiskněte klávesu **Alt**+**F5** ).

   Ladicí program se spustí a dojde k porušení `xsl:if` značky.

3. Klikněte pravým tlačítkem a vyberte **QuickWatch**.

   **QuickWatch** otevře se okno.

4. Zadejte `./price/text()` v **výraz** pole **QuickWatch** dialogové okno a potom vyberte **přehodnotit**.

   Ceny pro aktuální uzel knihy se zobrazí v **hodnotu** pole.

   ![Vyhodnocení výrazu XPath v okně Quickwatch](media/quickwatch-price.png)

5. Změnit výraz XPath, který má `./price/text() < $bookAverage` a klikněte na tlačítko **přehodnotit**.

   **Hodnotu** poli se zobrazí, že vyhodnocení výrazu XPath má `true`.

## <a name="see-also"></a>Viz také:

- [Ladění XSLT](../xml-tools/debugging-xslt.md)