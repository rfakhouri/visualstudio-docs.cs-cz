---
title: "Objekty, které přidáváte do návrháře používat různé datové připojení, než je aktuálně pomocí návrháře | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 332ed2f3-3377-4d51-8e3b-fdb98231978e
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 715bb696819af901c04fc0d95747b51186868003
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="the-objects-you-are-adding-to-the-designer-use-a-different-data-connection-than-the-designer-is-currently-using"></a>Objekty, které přidáváte do návrháře používat různé datové připojení, než je aktuálně pomocí návrháře
Objekty, které přidáváte do návrháře používat různé datové připojení, než je aktuálně pomocí návrháře. Chcete nahradit připojení používané objektem návrháře?  
  
 Po přidání položek [!INCLUDE[vs_ordesigner_long](../data-tools/includes/vs_ordesigner_long_md.md)] ([!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]), všechny položky použít jedno připojení sdílená data. (Návrhovou plochu, která představuje <xref:System.Data.Linq.DataContext>, který používá jednoho připojení pro všechny objekty na povrchu.) Pokud přidáte objekt návrháře, který používá datové připojení, které se liší od aktuálně používá návrháře datové připojení, zobrazí se tato zpráva. Pokud chcete tuto chybu vyřešit, můžete zachovat existující připojení. Pokud provedete tuto volbu, nebude přidána vybraný objekt. Alternativně můžete k přidání objektu a obnovit <xref:System.Data.Linq.DataContext> připojení k nové připojení.  
  
> [!NOTE]
>  Pokud kliknete na tlačítko **Ano**, všechny entity třídy na [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] jsou namapované na nové připojení.  
  
### <a name="to-replace-the-existing-connection-with-the-connection-used-by-the-selected-object"></a>Chcete-li nahradit stávající připojení pomocí připojení používané objektem vybraného objektu.  
  
-   Klikněte na tlačítko **Ano**.  
  
     Vybraný objekt přidán do [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], a DataContext.Connection je nastavena na nové připojení.  
  
### <a name="to-continue-to-use-the-existing-connection-and-cancel-adding-the-selected-object"></a>Chcete-li nadále používat existující připojení a zrušit přidání vybraného objektu.  
  
-   Klikněte na tlačítko **ne**.  
  
     Je akce zrušena. DataContext.Connection zůstane nastavená na existující připojení.  
  
## <a name="see-also"></a>Viz také
[Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)  
[Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
 