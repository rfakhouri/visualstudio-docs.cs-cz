---
title: Změnu návratového typu metody DataContext nelze vrátit zpět.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 76b161fc-5075-4192-8d94-f15b02e199e9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.prod: visual-studio-dev15
ms.workload:
- data-storage
ms.openlocfilehash: c446849941131d44c7819882c36b952ce217adfc
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55003185"
---
# <a name="changing-the-return-type-of-a-datacontext-method-cannot-be-undone"></a>Změnu návratového typu metody DataContext nelze vrátit zpět.

Změnu návratového typu metody DataContext nelze vrátit zpět. Pokud chcete vrátit zpět k automaticky generovanému typu, je třeba přetáhnout položky z **Průzkumníka serveru** nebo **Průzkumník databáze** do Návrháře relací objektů znovu. Opravdu že chcete změnit návratový typ?

Návratový typ <xref:System.Data.Linq.DataContext> metoda se liší v závislosti na tom, kde přetáhnete položku do [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. Pokud přetáhnete položku přímo do existující entity třídy, <xref:System.Data.Linq.DataContext> metodu, která má návratový typ třídy entita se vytvoří. Pokud přetáhnete položku na prázdnou oblast [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], <xref:System.Data.Linq.DataContext> vytvořené metodou, která vrací automaticky generovanému typu. Můžete změnit návratový typ <xref:System.Data.Linq.DataContext> metoda po přidání do podokna metody. Zkontrolovat nebo změnit návratový typ <xref:System.Data.Linq.DataContext> metoda, vyberte ho a klikněte **návratový typ** vlastnost v **vlastnosti** okna.

## <a name="to-change-the-return-type-of-a-datacontext"></a>Chcete-li změnit návratový typ položkou DataContext

- Klikněte na **Ano**.

## <a name="to-exit-the-message-box-and-leave-the-return-type-unchanged"></a>Chcete ukončit okně se zprávou a ponechat beze změny návratový typ

- Klikněte na tlačítko **ne**.

## <a name="to-revert-to-the-original-return-type-after-changing-the-return-type"></a>Vrátit zpět na původní typ vrácené hodnoty po změnu návratového typu

1. Vyberte <xref:System.Data.Linq.DataContext> metodu [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] a odstraňte ho.

2. Vyhledejte položku v **Průzkumník serveru/Průzkumník databáze** a přetáhněte ji do [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)].

    A <xref:System.Data.Linq.DataContext> metodu je vytvořen s původní výchozí návratovým typem.

## <a name="see-also"></a>Viz také:

- [Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)
- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)