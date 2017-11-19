---
title: "Postupy: vytvoření podmínky deklarativní pravidla (zastaralé) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- declarative rule conditions
- condition statements, declarative rule conditions
- Rule Condition Editor dialog box
ms.assetid: 804b6129-c433-408f-a424-46987967730c
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 736c36df419d601c27998d8d34bde9abe5976a17
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="how-to-create-a-declarative-rule-condition-legacy"></a>Postupy: vytvoření podmínky deklarativní pravidla (zastaralé)
Toto téma popisuje podmínku pravidla pomocí starší verze deklarovat [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)] s cílem [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 Příkaz podmínky se vyhodnocuje **True** nebo **False**. Deklarativní pravidlo podmínku je příkaz podmínky, která je vytvořená pomocí [dialogové okno pravidla podmínku Editor (zastaralé)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md) a uložit jako XML s pracovním postupem. Může zahrnovat predikáty, které porovnávají stav pracovního postupu a algebra logická hodnota, které se kombinuje několik predikáty.  
  
 Podmínky deklarativní pravidla se používají v níže uvedených aktivit out-of-box modelu Windows Workflow Foundation:  
  
-   [Skupina ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)  
  
-   [IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65034)  
  
-   [ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)  
  
-   [Aktivita typu WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)  
  
-   [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040)  
  
-   [StateMachineWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65045)  
  
### <a name="to-create-a-declarative-rule-condition-using-the-rule-condition-editor"></a>Chcete-li vytvořit podmínku deklarativní pravidla pomocí Editor podmínek pravidla  
  
1.  V rámci aktivity **vlastnosti** okně klikněte na tlačítko **podmínku** vlastnost nebo **UntilCondition** vlastnost, v závislosti na aktivity.  
  
2.  Vyberte **deklarativní podmínku pravidla** ze seznamu pro vlastnost.  
  
3.  Rozbalte **podmínku** nebo **UntilCondition** vlastnost.  
  
4.  Klikněte **ConditionName** vlastnost.  
  
5.  Klikněte **ConditionName** třemi tečkami **[...]**  otevřete **vyberte podmínku** dialogové okno.  
  
6.  Klikněte na tlačítko **novou podmínku** otevřete **Editor podmínek pravidla** dialogové okno.  
  
7.  Zadejte výraz pro stav v **podmínku** textové pole.  
  
     Informace o tom, jak vytvořit podmínku výrazy najdete v tématu [dialogové okno pravidla podmínku Editor (zastaralé)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md).  
  
8.  Až budete hotovi, vytváření výraz podmínky, klikněte na tlačítko **OK** a zavřete dialogové okno Vytvořit podmínka pro pravidlo s názvem přiřazené.  
  
     **Vyberte podmínku** otevře se dialogové okno.  
  
     Informace o tom, jak používat **vyberte podmínku** dialogové okno, najdete v části [vyberte podmínku dialogové okno (zastaralé)](../workflow-designer/select-condition-dialog-box-legacy.md).  
  
## <a name="see-also"></a>Viz také  
 [Aktivity pracovního postupu starší verze](../workflow-designer/legacy-workflow-activities.md)   
 [Pomocí skupiny ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65066)   
 [Pomocí aktivity IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65075)   
 [Pomocí aktivity replikátoru](http://go.microsoft.com/fwlink?LinkID=65080)   
 [Pomocí když aktivita](http://go.microsoft.com/fwlink?LinkID=65091)   
 [Editor podmínek pravidla dialogové okno (zastaralé)](../workflow-designer/rule-condition-editor-dialog-box-legacy.md)   
 [Dialogové okno Vyberte podmínku (zastaralé)](../workflow-designer/select-condition-dialog-box-legacy.md)   
 [Pomocí podmínek v pracovních postupech](http://go.microsoft.com/fwlink?LinkID=65009)