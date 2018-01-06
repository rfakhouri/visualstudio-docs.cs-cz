---
title: InvokeDelegate | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- InvokeDelegate Designer
- System.Activities.Statements.InvokeDelegate.UI
ms.assetid: 289a7498-5127-453f-beb5-05f05b80d26f
caps.latest.revision: "3"
ms.author: sdanie
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 56b132403d51a591a8832c1417bec73bde442266
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="invokedelegate"></a>InvokeDelegate
**InvokeDelegate** designer se používá k vytvoření a konfigurace <xref:System.Activities.Statements.InvokeDelegate> aktivity.  
  
## <a name="the-invokedelegate-activity"></a>InvokeDelegate aktivity  
 <xref:System.Activities.Statements.InvokeDelegate> Volá veřejný delegát.  
  
### <a name="using-the-invokedelegate-activity-designer"></a>Pomocí návrháře InvokeDelegate aktivity  
 **InvokeDelegate** Návrhář aktivity naleznete v **primitiv** kategorii **sada nástrojů**, který přistupuje kliknutím **sady nástrojů** kartě [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CRTL + ALT + X.)  
  
 **InvokeDelegate** Návrhář aktivity můžete přetáhnout z **sada nástrojů** a vynechaných na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] prostor kde je to aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.InvokeDelegate> aktivitu výchozí <xref:System.Activities.Activity.DisplayName%2A> z InvokeDelegate. <xref:System.Activities.Activity.DisplayName%2A> Lze upravit v hlavičce **InvokeDelegate** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.  
  
### <a name="the-invokedelegate-properties"></a>Vlastnosti InvokeDelegate  
 Následující tabulce je zobrazena <xref:System.Activities.Statements.InvokeDelegate> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti lze upravit v tabulce vlastností a některé můžete upravit na [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]plochu návrháře.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.InvokeDelegate> aktivity. Výchozí hodnota je InvokeDelegate.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít.|  
|<xref:System.Activities.Statements.InvokeDelegate.Delegate%2A>|Hodnota TRUE|Název <xref:System.Activities.ActivityDelegate> volána, když aktivita provede. Tuto vlastnost lze upravit na plochu návrháře. Toto je povinná vlastnost.|  
|<xref:System.Activities.Statements.InvokeDelegate.DelegateArguments%2A>|False|Argument kolekce volaný delegát. Klíče jsou názvy objektů parametr na <xref:System.Activities.ActivityDelegate> a hodnoty jsou argumenty, jejichž výrazy jsou vyhodnotit a přiřadit k objektům odpovídající parametr. V tabulce vlastností klikněte na tlačítko se třemi tečkami v **DelegateArguments** pole, zobrazuje **DelegateArguments** dialogové okno, abyste mohli tuto vlastnost nastavit. Klikněte **vytvořit Argument** pole, které chcete přidat argumenty.|  
  
## <a name="see-also"></a>Viz také  
 [Postupy: Definování a použití delegátů aktivit v návrháři postupu provádění](../workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer.md)