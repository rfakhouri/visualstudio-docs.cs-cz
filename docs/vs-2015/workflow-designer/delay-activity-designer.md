---
title: Návrhář aktivity zpoždění | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Delay.UI
ms.assetid: f51742a8-2c9a-47d1-8a23-18459d03ae19
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 012d5b9a9bb39221c5c9babdcf8010e28a24cb59
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669845"
---
# <a name="delay-activity-designer"></a>Návrhář aktivity Delay
**Zpoždění** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Delay> aktivity.  
  
## <a name="the-delay-activity"></a>Aktivitě Delay  
 <xref:System.Activities.Statements.Delay> Aktivity zpoždění spuštění pracovního postupu pro určenou dobu.  
  
### <a name="using-the-delay-activity-designer"></a>Návrhář aktivity Delay pomocí  
 **Zpoždění** návrháře aktivit najdete v **primitiv** kategorii **nástrojů**, který přistupuje po kliknutí **nástrojů**karty [!INCLUDE[wfd2](../includes/wfd2-md.md)] (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **Zpoždění** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřazené k [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface všude, kde aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Delay> aktivity s výchozím <xref:System.Activities.Activity.DisplayName%2A> zpoždění. <xref:System.Activities.Activity.DisplayName%2A> Můžete upravovat v záhlaví **zpoždění** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.  
  
### <a name="the-delay-properties"></a>Vlastnosti zpoždění  
 Následující tabulka ukazuje <xref:System.Activities.Statements.Delay> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti můžete upravit v mřížce vlastností a z nich můžete upravit některé na [!INCLUDE[wfd2](../includes/wfd2-md.md)]návrhové ploše.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.Delay> aktivity. Výchozí hodnota je zpoždění. I když <xref:System.Activities.Activity.DisplayName%2A> hodnota není bezpodmínečně nutné, je osvědčeným postupem je použití jednoho.|  
|<xref:System.Activities.Statements.Delay.Duration%2A>|Hodnota TRUE|Množství času zpoždění pracovní postup. Tato vlastnost je nastavena v mřížce vlastností. Zadejte buď literál <xref:System.TimeSpan> ve formátu 00:00:00 nebo výraz jazyka Visual Basic k určení časového intervalu.|  
  
## <a name="see-also"></a>Viz také  
 [Primitiv](../workflow-designer/primitives-activity-designers.md)   
 [přiřazení](../workflow-designer/assign-activity-designer.md)   
 [Návrhář aktivity delay](../workflow-designer/delay-activity-designer.md)   
 [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)   
 [WriteLine](../workflow-designer/writeline-activity-designer.md)