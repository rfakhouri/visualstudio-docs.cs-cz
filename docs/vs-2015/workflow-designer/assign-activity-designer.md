---
title: Návrhář aktivity Assign | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Assign.UI
ms.assetid: ba3feb3c-f144-47ea-926d-cf752b804153
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 111f53ec5b427207a6bde5d590cf8f1c908ff130
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54766128"
---
# <a name="assign-activity-designer"></a>Návrhář aktivity Assign
**Přiřadit** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Assign> aktivity.  
  
## <a name="the-assign-activity"></a>Aktivitě Assign  
 <xref:System.Activities.Statements.Assign> Aktivity přiřazuje hodnotu proměnné nebo argumentu.  
  
### <a name="using-the-assign-activity-designer"></a>Návrhář aktivity Assign pomocí  
 **Přiřadit** návrháře aktivit najdete v **primitiv** kategorii **nástrojů**, který přistupuje po kliknutí **nástrojů**kartu (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **Přiřadit** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřazené k [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface kde někdy aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Assign> aktivity s výchozím **DisplayName** z přiřazení. <xref:System.Activities.Activity.DisplayName%2A> Můžete upravovat v záhlaví **přiřadit** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.  
  
### <a name="the-assign-properties"></a>Přiřazení vlastnosti  
 Následující tabulka ukazuje <xref:System.Activities.Statements.Assign> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti můžete upravit v mřížce vlastností a některé z nich bylo možné upravovat ve [!INCLUDE[wfd2](../includes/wfd2-md.md)] povrchu.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.Assign> aktivity. Výchozí hodnota je přiřadit. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není bezpodmínečně nutné, je osvědčeným postupem je použití jednoho.|  
|<xref:System.Activities.Statements.Assign.To%2A>|Pravda|Proměnné nebo argumentu, ke kterému <xref:System.Activities.Statements.Assign.Value%2A> je přiřazen. Toto musí být platným identifikátorem jazyka Visual Basic. Chcete-li nastavena vlastnost, zadejte výraz jazyka Visual Basic v **k** pole na **přiřadit** aktivity návrháře nebo v mřížce vlastností.|  
|<xref:System.Activities.Statements.Assign.Value%2A>|Pravda|Hodnota, která je přiřazená k proměnné. Chcete-li nastavit <xref:System.Activities.Statements.Assign.Value%2A>, zadejte výraz jazyka Visual Basic v **hodnotu** pole na **přiřadit** aktivity návrháře nebo v mřížce vlastností.|  
  
## <a name="see-also"></a>Viz také  
 [Primitiv](../workflow-designer/primitives-activity-designers.md)   
 [zpoždění](../workflow-designer/delay-activity-designer.md)   
 [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)   
 [WriteLine](../workflow-designer/writeline-activity-designer.md)