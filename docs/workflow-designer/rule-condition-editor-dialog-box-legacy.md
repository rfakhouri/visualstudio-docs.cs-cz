---
title: "Editor podmínek pravidla dialogové okno (zastaralé) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- System.Workflow.Activities.Rules.Design.RuleConditionDialog.UI
helpviewer_keywords:
- Rule Condition dialog box
ms.assetid: c7ca8be9-de31-4a64-939c-4d53a50d5e29
caps.latest.revision: 
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload:
- multiple
ms.openlocfilehash: a4f38bed7fc164fd5283b98afe780bc81a6a7265
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="rule-condition-editor-dialog-box-legacy"></a>Editor podmínek pravidla dialogové okno (zastaralé)
Toto téma popisuje, jak používat **Editor podmínek pravidla** dialogovém okně pro starší verze [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]. Pomocí starší verze [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] když potřebujete cílit buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 Vytvořit a upravit podmínky deklarativní pravidla pomocí **Editor podmínek pravidla** dialogové okno. Tyto podmínky pravidla jsou zveřejněné jako vlastnosti na následujících out-of-box aktivit programovacího modelu Windows Workflow Foundation:  
  
-   [Skupina ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)  
  
-   [IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65034)  
  
-   [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)  
  
-   [Aktivita typu WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)  
  
-   [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040)  
  
-   [StateMachineWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65045)  
  
 Přístup **Editor podmínek pravidla** dialogové okno pomocí [vyberte podmínku dialogové okno (zastaralé)](../workflow-designer/select-condition-dialog-box-legacy.md).  
  
 Následující tabulka popisuje prvky uživatelského rozhraní (UI) **Editor podmínek pravidla** dialogové okno.  
  
|Prvek uživatelského rozhraní (UI)|Popis|  
|----------------|-----------------|  
|**Podmínky:**|Zadejte výraz pro podmínku pravidla.|  
|**OK**|Kliknutím uložíte podmínka pro pravidlo.|  
  
## <a name="entering-condition-expressions"></a>Zadávání podmínku výrazů  
 Podmínka výrazy se zadat jako text. Můžete zadat **to.** do editoru, chcete-li pole, vlastnosti a metody používané v pracovním postupu pomocí nabídky jako IntelliSense. Nebo můžete přímo zadat název člena pracovního postupu. Logické operátory můžete přidat podmínky, jako je například AND, OR a NOT. Můžete také přidat predikáty. Predikát je binární operátor a dva operandy. Binární operátory podporována jsou  **==** ,  **>** ,  **\<** ,  **>=** , a  **<=** . Podporované operandy jsou konstantní hodnoty, aritmetické funkce a oboru veřejné členy.  
  
 Můžete určit typ pro porovnání, a můžete porovnat s **null** nebo prázdný řetězec. Můžete provádět vnořené volání členům na proměnné, která obsahuje komplexní typ, například `this.Address.State == "WA"`.  
  
 Editor podmínek pravidla podporuje následující operátory:  
  
-   Relační operátory: ==, =,! =  
  
-   Operátory porovnání: <, \<=, >, > =  
  
-   Aritmetické operátory: +, -, *, /, MOD  
  
-   Logické operátory: A, & &, OR a &#124; &#124; Ne,!  
  
-   Bitové operátory: &, &#124;  
  
 Priorita operátorů výraz dodržuje pravidla priorit operátor C#.  
  
 Editor podmínek pravidla podporuje následující numerických výrazů:  
  
 this.i == 1D (překládá 1.0)  
  
 this.i == 1E1 (přeloží na 10.0)  
  
 this.i == 1L (vyřeší jako typ long)  
  
 this.i == 1 milion (vyřeší jako desetinné číslo)  
  
 this.i == 1F (přeloží jako jeden)  
  
 this.i == 1U (řeší jako nepodepsané int)  
  
 Další informace o podmínkách najdete v tématu [podmínky použití v pracovních postupech](http://go.microsoft.com/fwlink?LinkID=65009).  
  
## <a name="see-also"></a>Viz také  
 [IfElseActivity](http://go.microsoft.com/fwlink?LinkID=65033)   
 [Skupina ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)   
 [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)   
 [Aktivita typu WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)   
 [Dialogové okno Vyberte podmínku (zastaralé)](../workflow-designer/select-condition-dialog-box-legacy.md)   
 [Pomocí podmínek v pracovních postupech](http://go.microsoft.com/fwlink?LinkID=65009)   
 [Nápověda k uživatelskému rozhraní návrháře pro programovací model Windows Workflow Foundation](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)