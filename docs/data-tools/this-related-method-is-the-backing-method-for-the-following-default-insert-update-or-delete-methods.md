---
title: "To se související s metoda metodu zálohování pro následující výchozí insert, update nebo delete metody | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 62afa6da-97cf-48b9-8de3-33e4d72a0377
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 3f8a31f886548d03f7acac58d392713ced297b42
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="this-related-method-is-the-backing-method-for-the-following-default-insert-update-or-delete-methods"></a>Tato metoda související je metoda zálohování pro následující výchozí insert, update nebo delete metody
Tato metoda související je metoda zálohování pro následující výchozí insert, update nebo delete metody. Pokud odstraníte, budou odstraněny také tyto metody. Chcete pokračovat?  
  
 Vybraný `DataContext` metoda se aktuálně používá jako jedna z metod Insert, Update nebo Delete pro jednu z tříd entit na Návrhář relací objektů. Odstranit vybranou metodu způsobit třídu entity, která byla pomocí této metody se vrátit k výchozí chování běhové pro provádění příkaz Insert, Update, nebo odstranit během aktualizace.  
  
### <a name="to-delete-the-selected-method-causing-the-entity-class-to-use-runtime-updates"></a>Chcete-li odstranit vybrané metody, způsobuje třídy entita s používáním aktualizací modulu runtime  
  
-   Klikněte na tlačítko **Ano**.  
  
     Odstraní vybranou metodu a všechny třídy, které používají tuto metodu pro přepsání nastavení aktualizace budou vrácené zpět pomocí výchozí LINQ SQL modul runtime chování.  
  
### <a name="to-close-the-message-box-leaving-the-selected-method-unchanged"></a>Zavřete okno se zprávou, beze změny a vybrané metody  
  
-   Klikněte na tlačítko **ne**.  
  
     Zavře okno se zprávou a nebudou provedeny žádné změny.  
  
## <a name="see-also"></a>Viz také
[Návrhář relací objektů zprávy](../data-tools/o-r-designer-messages.md)  
[Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)