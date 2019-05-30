---
title: Objekty přidané do návrháře použít odlišné datové připojení
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 332ed2f3-3377-4d51-8e3b-fdb98231978e
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: c85e0c17eeb4cfbd786faac338c8b908c5a7f363
ms.sourcegitcommit: 117ece52507e86c957a5fd4f28d48a0057e1f581
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/28/2019
ms.locfileid: "66260928"
---
# <a name="the-objects-you-are-adding-to-the-designer-use-a-different-data-connection-than-the-designer"></a>Objekty, které přidáváte do návrháře použít odlišné datové připojení než návrháře

Objekty, které přidáváte do návrháře použijte odlišné datové připojení, než momentálně používané návrhářem. Opravdu chcete připojení používané návrhářem nahradit?

Při přidávání položek do **Návrhář relací objektů** (**O/R Designer**), všech položek se používají sdílené datové připojení. (Na návrhovou plochu představuje <xref:System.Data.Linq.DataContext>, který používá jedno připojení pro všechny objekty na povrchu.) Pokud chcete přidat objekt do návrháře, který používá datové připojení, které se liší od aktuálně používá v Návrháři datové připojení, tato zpráva se zobrazí. Chcete-li vyřešit tuto chybu, můžete zachovat existující připojení. Pokud tuto volbu, nebude přidán vybraný objekt. Alternativně můžete přidat objekt a obnovit <xref:System.Data.Linq.DataContext> připojení k nové připojení.

## <a name="connection-options"></a>Možnosti připojení

- Pokud chcete nahradit stávající připojení pomocí připojení používané objektem vybraný objekt, klikněte na tlačítko **Ano**.

   Vybraný objekt se přidá do **O/R Designer**a *DataContext.Connection* je nastavena na nové připojení.

   > [!NOTE]
   > Vyberete-li **Ano**, tříd na všech entit **O/R Designer** jsou mapovány na nového připojení.

- Chcete-li pokračovat v používání existujícího připojení a zrušit přidávání vybraný objekt, klikněte na tlačítko **ne**.

   Akce zrušena. *DataContext.Connection* zůstane nastavena na existující připojení.

## <a name="see-also"></a>Viz také:

- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
