---
title: "Pořadí Návrhář aktivity | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Sequence.UI
ms.assetid: 51c8d3cb-4d43-458f-9631-b63755f9ac94
caps.latest.revision: 
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload:
- multiple
ms.openlocfilehash: 5d0635839b9d875c5c519ec41c6dcfa6dc02fa2c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sequence-activity-designer"></a>Návrhář aktivity pořadí
<xref:System.Activities.Statements.Sequence> Aktivity obsahuje uspořádanou kolekci podřízené aktivity, které se provede v pořadí.  
  
 Jiný způsob, jak spustit sadu aktivit, aby se má používat <xref:System.Activities.Statements.Flowchart> aktivity. Zvažte použití [vývojový diagram](../workflow-designer/flowchart-activity-designer.md) Pokud máte jednoduchý vytvoření větve nebo opakování ve smyčce toku programu, který chcete diagramem modelu.  
  
## <a name="using-the-sequence-activity-designer"></a>Pomocí návrháře pořadí aktivity  
 Chcete-li přidat <xref:System.Activities.Statements.Sequence> aktivity, přetáhněte **pořadí** Návrhář aktivity z **sada nástrojů** a umístěte jej do [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] prostor. Přidání podřízené aktivity k tomuto <xref:System.Activities.Statements.Sequence> aktivity, přetáhněte některé aktivity z **sada nástrojů** a umístěte jej na trojúhelníček do pole s textem pomocný parametr "Sem umístěte aktivity".  
  
### <a name="sequence-activity-properties-in-the-workflow-designer"></a>Vlastnosti aktivity pořadí v Návrháři pracovních postupů  
 Následující tabulce je zobrazena <xref:System.Activities.Statements.Sequence> vlastnosti a popisuje, jak se používají v návrháři. Tyto vlastnosti se dá upravit v mřížce vlastnost nebo na plochu návrháře.  
  
|Název vlastnosti|Požadováno|Použití|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Určuje popisný název <xref:System.Activities.Statements.Sequence> Návrhář aktivity v hlavičce. Výchozí hodnota je pořadí. Hodnota se dá upravit v mřížku vlastností, nebo přímo v hlavičce Návrhář aktivity.<br /><br /> I když <xref:System.Activities.Activity.DisplayName%2A> striktně nevyžaduje, je osvědčeným postupem použít.|  
  
## <a name="see-also"></a>Viz také  
 [Vývojový diagram](../workflow-designer/flowchart-activity-designer.md)   
 [Tok řízení](../workflow-designer/control-flow-activity-designers.md)