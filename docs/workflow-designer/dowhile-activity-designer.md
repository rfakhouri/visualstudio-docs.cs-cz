---
title: "Návrhář aktivity DoWhile | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: System.Activities.Statements.DoWhile.UI
ms.assetid: 948deb35-d72f-462b-bea6-4b119c10a148
caps.latest.revision: "7"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 041c63d45e70305495fd18ed595a31eee6772389
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="dowhile-activity-designer"></a>Návrhář aktivity DoWhile
<xref:System.Activities.Statements.DoWhile> Aktivita provádí aktivity obsažené v jeho <xref:System.Activities.Statements.DoWhile.Body%2A> alespoň jednou, dokud je zadaná podmínka vyhodnocena jako **false**. Pokud potřebujete aktivity obsažené v těla smyčky spouštění nula nebo více dobu, použijte <xref:System.Activities.Statements.While> aktivity místo.  
  
## <a name="dowhile-properties-in-the-workflow-designer"></a>Vlastnosti DoWhile v Návrháři pracovních postupů  
 V následující tabulce jsou velmi užitečné <xref:System.Activities.Statements.DoWhile> vlastnosti aktivity a popisuje, jak je používat v návrháři.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.DoWhile.Body%2A>|False|Aktivita provést, když je podmínka vyhodnocena jako **true**. Chcete-li přidat <xref:System.Activities.Statements.DoWhile.Body%2A> aktivity, vyřaďte aktivitu z panelu nástrojů do **textu** pole na **DoWhile** Návrhář aktivity s text nápovědy "Aktivity Sem přetáhněte".|  
|<xref:System.Activities.Statements.DoWhile.Condition%2A>|Hodnota TRUE|Podmínky pro vyhodnocení po každé iteraci smyčky. Nastavit <xref:System.Activities.Statements.DoWhile.Condition%2A>, zadejte [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] výrazu v **podmínku** pole na **DoWhile** aktivity návrháře nebo v tabulce vlastností.|  
  
## <a name="see-also"></a>Viz také  
 [Chvíli](../workflow-designer/while-activity-designer.md)   
 [Tok řízení](../workflow-designer/control-flow-activity-designers.md)