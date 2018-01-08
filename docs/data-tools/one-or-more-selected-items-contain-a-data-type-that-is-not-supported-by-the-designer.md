---
title: "Jeden nebo více vybraných položek obsahovat datový typ, který není podporován v designeru | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71dcd4f9-2946-42c5-9ce4-99c819ea2785
caps.latest.revision: "4"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 2a652cc1a48e851f0c13c1b50d4a145531b87147
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="one-or-more-selected-items-contain-a-data-type-that-is-not-supported-by-the-designer"></a>Jeden nebo více vybraných položek obsahovat datový typ, který není podporován v designeru
Jeden nebo více položek přetažením z **Průzkumníka serveru**/**Průzkumník databáze** na [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] obsahuje datový typ, který není podporován [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] například [Uživatelem definované typy CLR](/dotnet/framework/data/adonet/sql/clr-user-defined-types).  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Vytvořit zobrazení, která je založená na požadovanou tabulku a který nezahrnuje nepodporovaným datovým typem.  
  
2.  Přetáhněte zobrazení **Průzkumníka serveru**/**Průzkumník databáze** do návrháře.  
  
## <a name="see-also"></a>Viz také
[Zprávy Návrháře relací objektů](../data-tools/o-r-designer-messages.md)  
[Technologie LINQ to SQL nástroje v sadě Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)