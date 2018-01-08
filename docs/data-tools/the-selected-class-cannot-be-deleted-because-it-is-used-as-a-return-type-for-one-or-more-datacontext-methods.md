---
title: "Vybrané třídy nelze odstranit, protože je používán jako návratový typ pro jednu nebo více metod DataContext | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d68254a0-f3a1-47e2-aed3-a83471e1d711
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 78107218af8c4b32e1cace3137fa15fe31fcbc52
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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