---
title: Tato související metoda je záložní metoda pro následující výchozí metody vložení, aktualizace nebo odstranění.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 62afa6da-97cf-48b9-8de3-33e4d72a0377
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: c79492c69f10d97c246d0d56b013fba5af17ec54
ms.sourcegitcommit: 5a65ca6688a2ebb36564657d2d73c4b4f2d15c34
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54204002"
---
# <a name="this-related-method-is-the-backing-method-for-the-following-default-insert-update-or-delete-methods"></a>Tato související metoda je záložní metoda pro následující výchozí metody vložení, aktualizace nebo odstranění.

Tato související metoda je záložní metoda pro následující výchozí `Insert`, `Update`, nebo `Delete` metody. Pokud se odstraní, odstraní se i tyto metody. Přejete si pokračovat?

Vybrané `DataContext` metoda se aktuálně používá jako jeden z `Insert`, `Update`, nebo `Delete` metody pro jednu z tříd entit na **O/R Designer**. Odstranění vybrané metody způsobí, že třídu entity, která se pomocí této metody vrátit zpět k výchozímu chování za běhu pro provádění vložení, aktualizaci nebo odstranění během aktualizace.

## <a name="selected-method-options"></a>Možnosti vybrané metody

- Pokud chcete odstranit vybrané metody způsobí třídu entity aktualizace modulu runtime, klikněte na tlačítko **Ano**.

   Odstraní vybranou metodu a všechny třídy, které používají tuto metodu pro přepsání nastavení aktualizace jsou vráceny pomocí výchozí LINQ na SQL chování za běhu.

- Zavření okna se zprávou, byste museli opustit vybrané metody beze změny, klikněte na tlačítko **ne**.

   Zavře okno se zprávou a nebudou provedeny žádné změny.

## <a name="see-also"></a>Viz také:

- [Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)
- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)