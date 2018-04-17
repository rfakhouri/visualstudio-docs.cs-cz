---
title: Jeden nebo více vybraných položek obsahovat datový typ, který není podporován v designeru | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 71dcd4f9-2946-42c5-9ce4-99c819ea2785
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 966adc7a4114c54479c0ad8c52a604e0fb5d3380
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="one-or-more-selected-items-contain-a-data-type-that-is-not-supported-by-the-designer"></a>Jeden nebo více vybraných položek obsahovat datový typ, který není podporován v designeru
Jeden nebo více položek přetažením z **Průzkumníka serveru**/**Průzkumník databáze** na [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] obsahuje datový typ, který není podporován [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] například [Uživatelem definované typy CLR](/dotnet/framework/data/adonet/sql/clr-user-defined-types).  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Vytvořit zobrazení, která je založená na požadovanou tabulku a který nezahrnuje nepodporovaným datovým typem.  
  
2.  Přetáhněte zobrazení **Průzkumníka serveru**/**Průzkumník databáze** do návrháře.  
  
## <a name="see-also"></a>Viz také
[Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)  
[Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)