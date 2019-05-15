---
title: Tato související metoda je záložní metoda pro následující výchozí vložení, aktualizace nebo odstranění metody | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: 62afa6da-97cf-48b9-8de3-33e4d72a0377
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b78f424e20adbfc92b4e33cc91ce6aed10c18ca8
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65700210"
---
# <a name="this-related-method-is-the-backing-method-for-the-following-default-insert-update-or-delete-methods"></a>Tato související metoda je záložní metoda pro následující výchozí metody vložení, aktualizace nebo odstranění.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato související metoda je záložní metoda pro následující výchozí vložení, aktualizace nebo odstranění metody. Pokud se odstraní, odstraní se i tyto metody. Přejete si pokračovat?  
  
 Vybrané `DataContext` metoda se aktuálně používá jako jeden z metody Insert, Update nebo Delete pro jednu z tříd entit na Návrháře relací objektů. Odstranění vybrané metody třídy entity, která se pomocí této metody vrátit zpět k výchozímu chování za běhu pro provádění Insert, Update, nebo odstranit během aktualizace.  
  
### <a name="to-delete-the-selected-method-causing-the-entity-class-to-use-runtime-updates"></a>Chcete odstranit vybrané metody způsobí třídu entity aktualizace modulu runtime  
  
- Klikněte na **Ano**.  
  
     Odstraní vybranou metodu a všechny třídy, které používají tuto metodu pro přepsání nastavení aktualizace jsou vráceny pomocí výchozí LINQ na SQL chování za běhu.  
  
### <a name="to-close-the-message-box-leaving-the-selected-method-unchanged"></a>Zavřete okno se zprávou, beze změny byste museli opustit vybrané metody  
  
- Klikněte na tlačítko **ne**.  
  
     Zavře okno se zprávou a nebudou provedeny žádné změny.  
  
## <a name="see-also"></a>Viz také  
 [Metody DataContext (O/R Designer)](../data-tools/datacontext-methods-o-r-designer.md)   
 [Postupy: Přiřazení uložených procedur za účelem aktualizace, vložení a odstranění (O/R Designer)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)   
 [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](https://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)
