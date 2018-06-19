---
title: Objekty, které přidáváte do návrháře používat různé datové připojení, než je aktuálně pomocí návrháře
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 332ed2f3-3377-4d51-8e3b-fdb98231978e
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 33a6083fb9e52ebdafbc827fc19666c1df9a3f7e
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31924513"
---
# <a name="the-objects-you-are-adding-to-the-designer-use-a-different-data-connection-than-the-designer"></a>Objekty, které přidáváte do návrháře používat různé datové připojení než návrháře

Objekty, které přidáváte do návrháře používat různé datové připojení, než je aktuálně pomocí návrháře. Chcete nahradit připojení používané objektem návrháře?

Po přidání položek [!INCLUDE[vs_ordesigner_long](../data-tools/includes/vs_ordesigner_long_md.md)] ([!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]), všechny položky použít jedno připojení sdílená data. (Návrhovou plochu, která představuje <xref:System.Data.Linq.DataContext>, který používá jednoho připojení pro všechny objekty na povrchu.) Pokud přidáte objekt návrháře, který používá datové připojení, které se liší od aktuálně používá návrháře datové připojení, zobrazí se tato zpráva. Pokud chcete tuto chybu vyřešit, můžete zachovat existující připojení. Pokud provedete tuto volbu, nebude přidána vybraný objekt. Alternativně můžete k přidání objektu a obnovit <xref:System.Data.Linq.DataContext> připojení k nové připojení.

> [!NOTE]
> Pokud kliknete na tlačítko **Ano**, všechny entity třídy na [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] jsou namapované na nové připojení.

## <a name="to-replace-the-existing-connection-with-the-connection-used-by-the-selected-object"></a>Chcete-li nahradit stávající připojení pomocí připojení používané objektem vybraného objektu.

- Klikněte na tlačítko **Ano**.

    Vybraný objekt přidán do [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], a DataContext.Connection je nastavena na nové připojení.

## <a name="to-continue-to-use-the-existing-connection-and-cancel-adding-the-selected-object"></a>Chcete-li nadále používat existující připojení a zrušit přidání vybraného objektu.

- Klikněte na tlačítko **ne**.

    Je akce zrušena. DataContext.Connection zůstane nastavená na existující připojení.

## <a name="see-also"></a>Viz také

- [Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)
- [Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
