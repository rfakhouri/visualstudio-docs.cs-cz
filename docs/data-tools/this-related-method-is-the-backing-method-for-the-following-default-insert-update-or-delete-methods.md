---
title: Tato metoda související je metoda zálohování pro následující výchozí insert, update nebo delete metody
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 62afa6da-97cf-48b9-8de3-33e4d72a0377
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: fdb359ebe4a42e0ddad8b93c1e746922ac609f60
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="this-related-method-is-the-backing-method-for-the-following-default-insert-update-or-delete-methods"></a>Tato metoda související je metoda zálohování pro následující výchozí insert, update nebo delete metody

Tato metoda související je metoda zálohování pro následující výchozí insert, update nebo delete metody. Pokud odstraníte, budou odstraněny také tyto metody. Chcete pokračovat?

Vybraný `DataContext` metoda se aktuálně používá jako jedna z metod Insert, Update nebo Delete pro jednu z tříd entit na Návrhář relací objektů. Odstranit vybranou metodu způsobit třídu entity, která byla pomocí této metody se vrátit k výchozí chování běhové pro provádění příkaz Insert, Update, nebo odstranit během aktualizace.

## <a name="to-delete-the-selected-method-causing-the-entity-class-to-use-runtime-updates"></a>Chcete-li odstranit vybrané metody, způsobuje třídy entita s používáním aktualizací modulu runtime

- Klikněte na tlačítko **Ano**.

    Odstraní vybranou metodu a všechny třídy, které používají tuto metodu pro přepsání nastavení aktualizace budou vrácené zpět pomocí výchozí LINQ SQL modul runtime chování.

## <a name="to-close-the-message-box-leaving-the-selected-method-unchanged"></a>Zavřete okno se zprávou, beze změny a vybrané metody

- Klikněte na tlačítko **ne**.

    Zavře okno se zprávou a nebudou provedeny žádné změny.

## <a name="see-also"></a>Viz také

- [Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)
- [Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)