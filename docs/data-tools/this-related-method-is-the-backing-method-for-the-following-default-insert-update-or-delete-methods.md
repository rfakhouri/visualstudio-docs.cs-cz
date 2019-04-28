---
title: Tato související metoda je záložní metoda pro následující výchozí metody vložení, aktualizace nebo odstranění.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 62afa6da-97cf-48b9-8de3-33e4d72a0377
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: cc83bc78aace73cedf186b5ec925dce0a509b91d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62565469"
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