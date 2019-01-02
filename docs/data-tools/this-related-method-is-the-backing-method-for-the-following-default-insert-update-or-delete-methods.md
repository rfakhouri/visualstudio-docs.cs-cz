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
ms.openlocfilehash: 1b5579c8916e81e3c49e9d6e24bf37ed85039c03
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53851820"
---
# <a name="this-related-method-is-the-backing-method-for-the-following-default-insert-update-or-delete-methods"></a>Tato související metoda je záložní metoda pro následující výchozí metody vložení, aktualizace nebo odstranění.

Tato související metoda je záložní metoda pro následující výchozí `Insert`, `Update`, nebo `Delete` metody. Pokud se odstraní, odstraní se i tyto metody. Přejete si pokračovat?

Vybrané `DataContext` metoda se aktuálně používá jako jeden z `Insert`, `Update`, nebo `Delete` metody pro jednu z tříd entit na **O/R Designer**. Odstranění vybrané metody způsobí, že třídu entity, která se pomocí této metody vrátit zpět k výchozímu chování za běhu pro provádění vložení, aktualizaci nebo odstranění během aktualizace.

## <a name="to-delete-the-selected-method-causing-the-entity-class-to-use-runtime-updates"></a>Chcete odstranit vybrané metody způsobí třídu entity aktualizace modulu runtime

- Klikněte na **Ano**.

    Odstraní vybranou metodu a všechny třídy, které používají tuto metodu pro přepsání nastavení aktualizace jsou vráceny pomocí výchozí LINQ na SQL chování za běhu.

## <a name="to-close-the-message-box-leaving-the-selected-method-unchanged"></a>Zavřete okno se zprávou, beze změny byste museli opustit vybrané metody

- Klikněte na tlačítko **ne**.

    Zavře okno se zprávou a nebudou provedeny žádné změny.

## <a name="see-also"></a>Viz také:

- [Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)
- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)