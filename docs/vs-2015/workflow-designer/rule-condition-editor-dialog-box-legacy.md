---
title: Editor podmínek pravidla dialogové okno (starší verze) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
f1_keywords:
- System.Workflow.Activities.Rules.Design.RuleConditionDialog.UI
helpviewer_keywords:
- Rule Condition dialog box
ms.assetid: c7ca8be9-de31-4a64-939c-4d53a50d5e29
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8237c8e29007d010cd99e4323bf8e88a23b7e9fb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63006824"
---
# <a name="rule-condition-editor-dialog-box-legacy"></a>Dialogové okno Editor podmínek pravidla (starší verze)
Toto téma popisuje, jak používat **Editor podmínek pravidla** dialogové okno v starší [!INCLUDE[wfd1](../includes/wfd1-md.md)]. Použijte starší [!INCLUDE[wfd2](../includes/wfd2-md.md)] potřeba cílit na platformu [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] nebo [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
 Vytvoření a úprava podmínky deklarativního pravidla pomocí **Editor podmínek pravidla** dialogové okno. Tyto podmínky pravidla jsou vystaveny jako vlastnosti na těchto aktivitách out-of-box Windows Workflow Foundation:  
  
- [ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)  
  
- [IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65034)  
  
- [Aktivitou typu ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)  
  
- [Aktivita typu WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)  
  
- [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040)  
  
- [StateMachineWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65045)  
  
  Přístup **Editor podmínek pravidla** dialogové okno s použitím [vyberte podmínku dialogové okno (starší verze)](../workflow-designer/select-condition-dialog-box-legacy.md).  
  
  Následující tabulka popisuje prvky uživatelského rozhraní (UI) **Editor podmínek pravidla** dialogové okno.  
  
|Prvek uživatelského rozhraní (UI)|Popis|  
|----------------|-----------------|  
|**Podmínka:**|Zadejte výraz pro podmínku pravidla.|  
|**OK**|Klikněte na tlačítko Uložit podmínka pro pravidlo.|  
  
## <a name="entering-condition-expressions"></a>Zadávání výrazů podmínku  
 Podmínka výrazy se zadávají jako text. Můžete zadat **to.** v editoru odkazovat na pole, vlastnosti a metody použité v pracovním postupu pomocí technologie IntelliSense jako nabídky. Můžete taky zadat název člena pracovního postupu přímo. Logické operátory můžete přidat do podmínky, jako je například AND, OR a NOT. Můžete také přidat predikáty. Predikát je binárním operátorem a dva operandy. Binární operátory jsou podporované jsou **==** , **>** , **\<** , **>=** , a **<=** . Konstantní hodnota, aritmetické funkce a oboru veřejné členy jsou podporované operandy.  
  
 Můžete určit typ pro porovnání, a můžete porovnat s **null** nebo prázdný řetězec. Vnořená volání do členů provést na proměnnou, která obsahuje komplexní typ, třeba `this.Address.State == "WA"`.  
  
 Editor podmínek pravidla podporuje následující operátory:  
  
- Relační operátory: ==, =,! =  
  
- Relační operátory: <, \<=, >, > =  
  
- Aritmetické operátory: +, -, *, /, MOD  
  
- Logické operátory: A &AMP; &AMP;, OR, &AMP;#124; &AMP;#124;, NE,!  
  
- Bitové operátory: &&#124;  
  
  Priorita operátorů výraz následuje pravidla priorit operátor C#.  
  
  Editor podmínek pravidla podporuje následující numerických výrazů:  
  
  this.i == 1D (vyřešené 1.0)  
  
  this.i == 1E1 (překládá na 10.0)  
  
  this.i == 1L (vyřešené jako typu long)  
  
  this.i == 1 milion (vyřešené jako desítkové číslo)  
  
  this.i == 1F (přeloží jako jeden)  
  
  this.i == 1U (přeloží jako celé číslo bez znaménka)  
  
  Další informace o podmínkách najdete v tématu [podmínky použití v pracovních postupech](http://go.microsoft.com/fwlink?LinkID=65009).  
  
## <a name="see-also"></a>Viz také  
 [Aktivita typu IfElseActivity](http://go.microsoft.com/fwlink?LinkID=65033)   
 [ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)   
 [Aktivitou typu ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)   
 [Aktivita typu WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)   
 [Dialogové okno Vybrat podmínku (starší verze)](../workflow-designer/select-condition-dialog-box-legacy.md)   
 [Pomocí podmínek v pracovních postupech](http://go.microsoft.com/fwlink?LinkID=65009)   
 [Nápověda k uživatelskému rozhraní návrháře pro programovací model Windows Workflow Foundation](../workflow-designer/legacy-designer-for-windows-workflow-foundation-ui-help.md)