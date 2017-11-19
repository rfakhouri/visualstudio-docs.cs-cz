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
ms.openlocfilehash: 865c8f9fa91c24eed1e10bde68b239932237a62b
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="the-selected-class-cannot-be-deleted-because-it-is-used-as-a-return-type-for-one-or-more-datacontext-methods"></a>Vybrané třídy nelze odstranit, protože je používán jako návratový typ pro jednu nebo více metod DataContext
Návratový typ jednoho nebo více <xref:System.Data.Linq.DataContext> metody je třída vybrané entity. Odstraňování třídu entity, který se používá jako návratový typ pro <xref:System.Data.Linq.DataContext> způsobí, že metoda kompilace projektu selhání. Pokud chcete odstranit vybrané entity třídy, identifikovat <xref:System.Data.Linq.DataContext> metody, které ho použít a nastavte jejich návratové typy na třídu jiné entity.  
  
 Můžete obnovit návratové typy <xref:System.Data.Linq.DataContext> metody do jejich původního typy automaticky generovaný, nejprve odstranit <xref:System.Data.Linq.DataContext> metoda z podokna metody a přetáhněte objekt z **Průzkumníka serveru** / **Průzkumník databáze** na Návrhář relací objektů znovu.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Identifikovat <xref:System.Data.Linq.DataContext> metody, které používají třídu entity jako návratový typ výběrem <xref:System.Data.Linq.DataContext> metoda v metodách podokně a zkontrolujete **návratového typu** vlastnost **vlastnosti** okno .  
  
2.  Nastavte **návratového typu** jiné entity třídu nebo odstranění <xref:System.Data.Linq.DataContext> metoda z podokna metody.  
  
## <a name="see-also"></a>Viz také
[Návrhář relací objektů zprávy](../data-tools/o-r-designer-messages.md)  
[Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)