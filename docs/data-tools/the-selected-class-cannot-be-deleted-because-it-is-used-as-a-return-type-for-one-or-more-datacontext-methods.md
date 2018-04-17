---
title: Vybrané třídy nelze odstranit, protože je používán jako návratový typ pro jednu nebo více metod DataContext | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: d68254a0-f3a1-47e2-aed3-a83471e1d711
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 0b5781508083524a5cf7374a12fd962f0fe34aaf
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="the-selected-class-cannot-be-deleted-because-it-is-used-as-a-return-type-for-one-or-more-datacontext-methods"></a>Vybrané třídy nelze odstranit, protože je používán jako návratový typ pro jednu nebo více metod DataContext
Návratový typ jednoho nebo více <xref:System.Data.Linq.DataContext> metody je třída vybrané entity. Odstraňování třídu entity, který se používá jako návratový typ pro <xref:System.Data.Linq.DataContext> způsobí, že metoda kompilace projektu selhání. Pokud chcete odstranit vybrané entity třídy, identifikovat <xref:System.Data.Linq.DataContext> metody, které ho použít a nastavte jejich návratové typy na třídu jiné entity.  
  
 Můžete obnovit návratové typy <xref:System.Data.Linq.DataContext> metody do jejich původního typy automaticky generovaný, nejprve odstranit <xref:System.Data.Linq.DataContext> metoda z podokna metody a přetáhněte objekt z **Průzkumníka serveru** / **Průzkumník databáze** na Návrhář relací objektů znovu.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Identifikovat <xref:System.Data.Linq.DataContext> metody, které používají třídu entity jako návratový typ výběrem <xref:System.Data.Linq.DataContext> metoda v metodách podokně a zkontrolujete **návratového typu** vlastnost **vlastnosti** okno .  
  
2.  Nastavte **návratového typu** jiné entity třídu nebo odstranění <xref:System.Data.Linq.DataContext> metoda z podokna metody.  
  
## <a name="see-also"></a>Viz také
[Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)  
[Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)