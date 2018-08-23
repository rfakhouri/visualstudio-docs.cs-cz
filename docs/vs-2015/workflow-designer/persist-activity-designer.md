---
title: Návrhář aktivity Persist | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Persist.UI
ms.assetid: be8648dd-3eb9-4a50-8ec1-57a8be804692
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: e48538b5878b2b80a5babc531d2a7aba8a249fe9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627845"
---
# <a name="persist-activity-designer"></a>Návrhář aktivity Persist
**Trvalého** Návrhář aktivity se používá k vytvoření a konfigurace <xref:System.Activities.Statements.Persist> aktivity.  
  
## <a name="the-persist-activity"></a>Uchování aktivity  
 <xref:System.Activities.Statements.Persist> Aktivity uloží pracovní postup na disk, pokud je to možné. <xref:System.Activities.Statements.Persist> Aktivitu nelze v zóně není trvalost jako je třeba provést v rámci <xref:System.Activities.Statements.TransactionScope> aktivity. Pokud použijete <xref:System.Activities.Statements.Persist> aktivity v oboru bez trvalost, dojde k výjimce za běhu.  
  
### <a name="using-the-persist-activity-designer"></a>Použití Návrhář aktivity Persist  
 **Trvalého** návrháře aktivit najdete v **Runtime** kategorie **nástrojů**, který přistupuje po kliknutí **nástrojů** Karta (případně vyberte možnost **nástrojů** z **zobrazení** nabídky nebo CTRL + ALT + X.)  
  
 **Trvalého** návrháře aktivit můžete přetáhnout z **nástrojů** a vyřazené k [!INCLUDE[wfd2](../includes/wfd2-md.md)] surface všude, kde aktivity jsou obvykle umístěny, například jako uvnitř <xref:System.Activities.Statements.Sequence>. Tím se vytvoří <xref:System.Activities.Statements.Persist> aktivity s výchozím **DisplayName** trvalého. <xref:System.Activities.Activity.DisplayName%2A> Můžete upravovat v záhlaví **trvalého** Návrhář aktivity nebo v **DisplayName** pole mřížku vlastností.  
  
### <a name="the-persist-properties"></a>Zachovat vlastnosti  
 Následující tabulka ukazuje <xref:System.Activities.Statements.Persist> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti můžete upravit v mřížce vlastností a některé z nich bylo možné upravovat ve [!INCLUDE[wfd2](../includes/wfd2-md.md)] povrchu.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Popisný název <xref:System.Activities.Statements.Persist> aktivity. Výchozí hodnota je zachovat. I když zobrazovaný název není bezpodmínečně nutné, je osvědčeným postupem použít zobrazovaný název.|  
  
## <a name="see-also"></a>Viz také  
 [Modul runtime](../workflow-designer/runtime-activity-designers.md)   
 [TerminateWorkflow](../workflow-designer/terminateworkflow-activity-designer.md)