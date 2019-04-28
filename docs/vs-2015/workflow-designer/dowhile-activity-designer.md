---
title: Návrhář aktivity DoWhile | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.DoWhile.UI
ms.assetid: 948deb35-d72f-462b-bea6-4b119c10a148
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d09954409baccfdc5d9eb083a15bd02f5d16cb85
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62785256"
---
# <a name="dowhile-activity-designer"></a>Návrhář aktivity DoWhile
<xref:System.Activities.Statements.DoWhile> Aktivita provádí aktivity obsažené v jeho <xref:System.Activities.Statements.DoWhile.Body%2A> alespoň jednou, dokud je zadaná podmínka vyhodnocena jako **false**. Pokud potřebujete aktivity obsažené v těle smyčky mají být provedeny nulakrát nebo vícekrát, použijte <xref:System.Activities.Statements.While> aktivity místo.  
  
## <a name="dowhile-properties-in-the-workflow-designer"></a>Vlastnosti DoWhile v Návrháři postupu provádění  
 V následující tabulce jsou uvedeny nejužitečnější <xref:System.Activities.Statements.DoWhile> vlastnosti aktivit a popisuje, jak je používat v návrháři.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.DoWhile.Body%2A>|False|Aktivity ke spuštění, dokud podmínka **true**. Chcete-li přidat <xref:System.Activities.Statements.DoWhile.Body%2A> aktivity, rozevírací aktivitu z panelu nástrojů do **tělo** pole na **DoWhile** Návrhář aktivity s text nápovědy "Aktivity Sem přetáhněte".|  
|<xref:System.Activities.Statements.DoWhile.Condition%2A>|Pravda|Podmínka k vyhodnocení po každé iteraci smyčky. Chcete-li nastavit <xref:System.Activities.Statements.DoWhile.Condition%2A>, zadejte [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] výrazu v **podmínku** pole na **DoWhile** aktivity návrháře nebo v mřížce vlastností.|  
  
## <a name="see-also"></a>Viz také  
 [Při](../workflow-designer/while-activity-designer.md)   
 [Tok řízení](../workflow-designer/control-flow-activity-designers.md)