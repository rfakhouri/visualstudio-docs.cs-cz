---
title: Vybranou třídu nejde odstranit, protože se používá jako návratový typ pro minimálně jednu metodu DataContext.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: d68254a0-f3a1-47e2-aed3-a83471e1d711
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 5d63abefc67d54734380e6a1dc7f3364d5400c03
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/08/2019
ms.locfileid: "55926200"
---
# <a name="the-selected-class-cannot-be-deleted-because-it-is-used-as-a-return-type-for-one-or-more-datacontext-methods"></a>Vybranou třídu nejde odstranit, protože se používá jako návratový typ pro minimálně jednu metodu DataContext.

Návratový typ jednoho nebo více <xref:System.Data.Linq.DataContext> metody je třída vybrané entity. Odstraňuje třídu entity, která se používá jako návratový typ <xref:System.Data.Linq.DataContext> metoda způsobí, že kompilace projektu selže. Pokud chcete odstranit vybrané entity třídy, identifikovat <xref:System.Data.Linq.DataContext> metody, které použije a nastavte typy vrácených hodnot na jiné entity třídy.

Obnova návratové typy <xref:System.Data.Linq.DataContext> metody do jejich původního automaticky vygenerovaných typů, odstraňte nejdříve <xref:System.Data.Linq.DataContext> metodu z **metody** podokně a pak přetáhněte objekt z **Průzkumníka serveru** / **Průzkumník databáze** na **O/R Designer** znovu.

## <a name="to-correct-this-error"></a>Oprava této chyby

1. Identifikace <xref:System.Data.Linq.DataContext> metody, které používají entity třídy jako návratový typ tak, že vyberete <xref:System.Data.Linq.DataContext> metoda ve **metody** podokně a zkontrolujete **návratový typ** vlastnost **Vlastnosti** okna.

2. Nastavte **návratový typ** třída jiné entity nebo delete <xref:System.Data.Linq.DataContext> metoda z podokna metody.

## <a name="see-also"></a>Viz také:

- [Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)
- [Nástroje LINQ to SQL v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)