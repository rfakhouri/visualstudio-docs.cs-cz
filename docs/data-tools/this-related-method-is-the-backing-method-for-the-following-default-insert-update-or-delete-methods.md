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
ms.openlocfilehash: a5ae70462079589ba2b63ee50cf0b7a0570e056a
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/09/2019
ms.locfileid: "65457851"
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

- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)