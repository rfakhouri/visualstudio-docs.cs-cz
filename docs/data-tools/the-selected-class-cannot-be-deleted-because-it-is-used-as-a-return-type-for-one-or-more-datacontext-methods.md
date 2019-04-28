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
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62565417"
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