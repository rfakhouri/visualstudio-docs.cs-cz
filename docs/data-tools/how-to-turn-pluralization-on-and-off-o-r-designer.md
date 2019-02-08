---
title: 'Postupy: Pluralizace zapnutí a vypnutí (Návrhář O-R)'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 9b693bc3-303a-40a9-97ee-9cef5ca3ae81
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 51ca5704bae6d52bf6957b97ac01d2b587c05970
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55943555"
---
# <a name="how-to-turn-pluralization-on-and-off-or-designer"></a>Postupy: Pluralizace zapnutí a vypnutí (O/R Designer)
Ve výchozím nastavení se při přetažení databázových objektů, které mají jména končící na s nebo dokumentu z **Průzkumníka serveru** nebo **Průzkumník databáze** na [technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md), názvy generovaných tříd entit se mění v množném čísle pro singulární. To slouží k reprezentaci přesněji skutečnost, že třída vytvořenou instanci entity se mapuje na jeden záznam dat. Například přidáním `Customers` tabulky **O/R Designer** výsledkem třídu entity s názvem `Customer` protože třídy bude obsahovat data pro jediného zákazníka.

> [!NOTE]
>  Pluralizace je ve výchozím pouze v anglické jazykové verzi sady Visual Studio.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

### <a name="to-turn-pluralization-on-and-off"></a>K zapnutí a vypnutí pluralizace

1.  Na **nástroje** nabídky, klikněte na tlačítko **možnosti**.

2.  V **možnosti** dialogového okna rozbalte **databázové nástroje**.

    > [!NOTE]
    >  Vyberte **zobrazit všechna nastavení** Pokud **databázové nástroje** uzel není viditelný.

3.  Klikněte na tlačítko **O/R Designer**.

4.  Nastavte **Pluralizaci názvů** k **povoleno** = **False** nastavit **O/R Designer** tak, aby neměnil názvy tříd .

5.  Nastavte **Pluralizaci názvů** k **povoleno** = **True** použít pluralizace pravidla pro názvy tříd objektů, které jsou přidány do **O/R Návrhář**.

## <a name="see-also"></a>Viz také:

- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [Přístup k datům v sadě Visual Studio](../data-tools/accessing-data-in-visual-studio.md)