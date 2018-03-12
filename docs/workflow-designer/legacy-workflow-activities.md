---
title: "Aktivity pracovního postupu starší verze | Microsoft Docs"
ms.date: 01/18/2017
ms.topic: reference
helpviewer_keywords:
- workflows, activities
- activities
- workflow activities
ms.assetid: 4af7a06b-1e82-43c8-aec8-0dc5fb63d08a
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 61c719725f3d4ebfffe291ff31115ddd0cc5f3d4
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="legacy-workflow-activities"></a>Aktivity pracovního postupu starší verze

[!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] zahrnuje výchozí sadu aktivit, které poskytují funkce pro tok řízení, podmínek, zpracování událostí, správu stavu a komunikaci s aplikacemi a službami. Při návrhu pracovních postupů, můžete použít poskytované systémem aktivity, které jsou poskytovány návrháře pracovních postupů Windows, nebo můžete vytvořit vlastní aktivitu.

 Následující tabulka uvádí [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] sadu aktivity out-of-box framework. Mnoho, ale ne všechny tyto aktivity jsou reprezentované pomocí návrháře aktivit, které lze přistupovat z **sada nástrojů** z [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]. Chcete-li vytvořit aktivitu, přetáhněte jeho designer z **sada nástrojů** na návrhovou plochu.

|Aktivita|Popis|
|--------------|-----------------|
|<xref:System.Workflow.Activities.CallExternalMethodActivity>|Používá se **aktivita typu HandleExternalEventActivity** aktivity pro vstupní a výstupní komunikaci s místní službou. Další informace najdete v tématu [pomocí aktivity CallExternalMethodActivity](http://go.microsoft.com/fwlink?LinkID=65060).|
|**System.Workflow.Activities.CancellationHandlerActivity**|Použít tak, aby obsahovala čištění logiku pro aktivitu složené zrušena dříve, než všechny složené aktivity podřízené objekty jsou dokončení provádění. Další informace najdete v tématu [pomocí aktivity CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65061).|
|<xref:System.Workflow.Activities.CodeActivity>|Umožňuje přidat kód jazyka Visual Basic nebo C# do pracovního postupu. Další informace najdete v tématu [pomocí aktivity CodeActivity](http://go.microsoft.com/fwlink?LinkID=65062).|
|<xref:System.Workflow.Activities.CompensatableSequenceActivity>|Aktivita verze <xref:System.Workflow.Activities.SequenceActivity>. Další informace najdete v tématu [pomocí aktivity CompensatableSequenceActivity](http://go.microsoft.com/fwlink?LinkID=65002).|
|**System.Workflow.Activities.CompensatableTransactionScopeActivity**|Aktivita verze **aktivity typu TransactionScopeActivity**. Další informace najdete v tématu [pomocí aktivity CompensatableTransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65063).|
|**System.Workflow.Activities.CompensateActivity**|Umožňuje volat kód vrátit zpět nebo kompenzovat operace již prováděné v tomto pracovním postupu, když dojde k chybě. Další informace najdete v tématu [pomocí aktivity aktivita typu CompensateActivity](http://go.microsoft.com/fwlink?LinkID=65064).|
|**System.Workflow.Activities.CompensationHandlerActivity**|Obálka pro jeden nebo více aktivit, které provádějí náhradu za dokončené aktivity typu TransactionScopeActivity Další informace najdete v tématu [pomocí aktivity CompensationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65065).|
|<xref:System.Workflow.Activities.ConditionedActivityGroup>|Provede podřízené aktivity na základě podmínky, který se vztahuje <xref:System.Workflow.Activities.ConditionedActivityGroup> aktivity sám sebe a na základě podmínek, které platí pro všechny podřízené samostatně. Další informace najdete v tématu [pomocí aktivity skupiny ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65066).|
|<xref:System.Workflow.Activities.DelayActivity>|Umožňuje vytvořit zpoždění v pracovním postupu, které jsou založeny na interval časového limitu. Další informace najdete v tématu [pomocí aktivity typu DelayActivity](http://go.microsoft.com/fwlink?LinkID=65067).|
|<xref:System.Workflow.Activities.EventDrivenActivity>|Zabalí jeden nebo více aktivit, které jsou spouštěny, když dojde k zadané události. Další informace najdete v tématu [pomocí aktivity EventDrivenActivity](http://go.microsoft.com/fwlink?LinkID=65068).|
|<xref:System.Workflow.Activities.EventHandlersActivity>|Poskytuje rozhraní pro přidružení událostí k aktivitě. Další informace najdete v tématu [pomocí aktivity aktivitu typu EventHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65069).|
|<xref:System.Workflow.Activities.EventHandlingScopeActivity>|Provede jeho hlavní podřízené aktivity současně se <xref:System.Workflow.Activities.EventHandlersActivity>. Další informace najdete v tématu [pomocí aktivity EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65070).|
|**System.Workflow.Activities.FaultHandlerActivity**|Používá ke zpracování výjimky typu, který určíte. Další informace najdete v tématu [pomocí aktivity FaultHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65071).|
|**System.Workflow.Activities.FaultHandlersActivity**|Představuje složený aktivity, která má seřazený seznam podřízené aktivity typu **System.Workflow.Activities.FaultHandlerActivity**. Další informace najdete v tématu [pomocí aktivity FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65072).|
|<xref:System.Workflow.Activities.HandleExternalEventActivity>|Používá ve spojení s <xref:System.Workflow.Activities.CallExternalMethodActivity> aktivity pro vstupní a výstupní komunikaci s místní službou. Další informace najdete v tématu [pomocí aktivity aktivita typu HandleExternalEventActivity](http://go.microsoft.com/fwlink?LinkID=65073).|
|<xref:System.Workflow.Activities.IfElseActivity>|Testuje podmínku na každé větve a provádí aktivity na první větve, pro který se rovná podmínku **true**. Další informace najdete v tématu [pomocí aktivity IfElseActivity](http://go.microsoft.com/fwlink?LinkID=65074).|
|<xref:System.Workflow.Activities.IfElseBranchActivity>|Představuje větvi <xref:System.Workflow.Activities.IfElseActivity>. Další informace najdete v tématu [pomocí aktivity IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65075).|
|<xref:System.Workflow.Activities.InvokeWebServiceActivity>|Umožňuje pracovní postup k vyvolání webové služby. Další informace najdete v tématu [pomocí aktivity typu InvokeWebServiceActivity](http://go.microsoft.com/fwlink?LinkID=65076).|
|<xref:System.Workflow.Activities.InvokeWorkflowActivity>|Umožňuje pracovní postup k vyvolání jiného pracovního postupu. Další informace najdete v tématu [pomocí aktivity InvokeWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65077).|
|<xref:System.Workflow.Activities.ListenActivity>|Složené aktivity, který obsahuje pouze <xref:System.Workflow.Activities.EventDrivenActivity> podřízené aktivity. Další informace najdete v tématu [pomocí aktivity aktivita typu ListenActivity](http://go.microsoft.com/fwlink?LinkID=65078).|
|<xref:System.Workflow.Activities.ParallelActivity>|Poskytuje způsob, jak naplánovat dvou nebo více podřízených **SequenceActivity** větví aktivity pro zpracování ve stejnou dobu. Další informace najdete v tématu [pomocí aktivity aktivity ParallelActivity](http://go.microsoft.com/fwlink?LinkID=65079).|
|<xref:System.Workflow.Activities.PolicyActivity>|Použijte představují kolekci pravidel. Pravidlo obsahuje podmínky a výsledné akce. Další informace najdete v tématu [pomocí aktivity aktivitě PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65004).|
|<xref:System.Workflow.Activities.ReplicatorActivity>|Vytvoří více instancí jedné podřízené aktivity. Další informace najdete v tématu [pomocí aktivity ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65080).|
|<xref:System.Workflow.Activities.SequenceActivity>|Poskytuje jednoduchý způsob, jak propojit více aktivit společně pro sekvenční provádění. Další informace najdete v tématu [pomocí aktivity SequenceActivity](http://go.microsoft.com/fwlink?LinkID=65081).|
|<xref:System.Workflow.Activities.SetStateActivity>|Určuje přechod na nový stav. Další informace najdete v tématu [pomocí aktivity SetStateActivity](http://go.microsoft.com/fwlink?LinkID=65082).|
|<xref:System.Workflow.Activities.StateActivity>|Představuje stav v pracovním postupu stav počítače. Další informace najdete v tématu [pomocí aktivity StateActivity](http://go.microsoft.com/fwlink?LinkID=65083).|
|<xref:System.Workflow.Activities.StateFinalizationActivity>|Použít v <xref:System.Workflow.Activities.StateActivity> aktivitu jako kontejner pro podřízené aktivity, které jsou spouštěné při opuštění **StateActivity** aktivity. Další informace najdete v tématu [pomocí aktivity StateFinalizationActivity](http://go.microsoft.com/fwlink?LinkID=65008).|
|<xref:System.Workflow.Activities.StateInitializationActivity>|Použít v <xref:System.Workflow.Activities.StateActivity> aktivitu jako kontejner pro podřízené aktivity, které jsou spouštěny při zadávání **StateActivity** aktivity. Další informace najdete v tématu [pomocí aktivity StateInitializationActivity](http://go.microsoft.com/fwlink?LinkID=65006).|
|**System.Workflow.Activities.SuspendActivity**|Pozastaví operaci pracovní postup, chcete-li povolit zásahu v případě nějaké chyby, které vyžadují zvláštní pozornost. Další informace najdete v tématu [pomocí aktivity SuspendActivity](http://go.microsoft.com/fwlink?LinkID=65084).|
|**System.Workflow.Activities.SynchronizationScopeActivity**|Provádí obsažené aktivity postupně v synchronizované doméně. Další informace najdete v tématu [pomocí aktivity SynchronizationScopeActivity](http://go.microsoft.com/fwlink?LinkID=65085).|
|**System.Workflow.Activities.TerminateActivity**|Umožňuje okamžitě ukončení operace pracovního postupu v případě chybový stav. Další informace najdete v tématu [pomocí aktivity TerminateActivity](http://go.microsoft.com/fwlink?LinkID=65086).|
|**System.Workflow.Activities.ThrowActivity**|Umožňuje zachytit obchodní výjimky vydané jako součást procesu metadata pro pracovní postup. Další informace najdete v tématu [pomocí aktivity ThrowActivity](http://go.microsoft.com/fwlink?LinkID=65087).|
|**System.Workflow.Activities.TransactionScopeActivity**|Poskytuje rozhraní pro transakce a výjimek. Další informace najdete v tématu [pomocí aktivity typu TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65088).|
|<xref:System.Workflow.Activities.WebServiceFaultActivity>|Umožňuje modelu výskytem chybu webové služby. Další informace najdete v tématu [pomocí aktivity Aktivita WebServiceFaultActivity](http://go.microsoft.com/fwlink?LinkID=65089).|
|<xref:System.Workflow.Activities.WebServiceInputActivity>|Přijímá data z webové služby. Další informace najdete v tématu [pomocí aktivity aktivitu WebServiceInputActivity](http://go.microsoft.com/fwlink?LinkID=65090).|
|<xref:System.Workflow.Activities.WebServiceOutputActivity>|Odpoví na žádost o službu webové provedené v pracovním postupu. Další informace najdete v tématu [pomocí aktivity aktivita WebServiceOutputActivity](http://go.microsoft.com/fwlink?LinkID=65092).|
|<xref:System.Workflow.Activities.WhileActivity>|Umožňuje pracovní postup opakovat až do splnění podmínky. Další informace najdete v tématu [pomocí aktivity aktivita typu WhileActivity](http://go.microsoft.com/fwlink?LinkID=65091).|

 Další informace o tom, jak vytvořit vlastní aktivity najdete v tématu [vývoj vlastních aktivit](http://go.microsoft.com/fwlink?LinkID=65023) a [pomocí návrháře starší aktivity](../workflow-designer/using-the-legacy-activity-designer.md).

## <a name="see-also"></a>Viz také

- [Aktivity Windows Workflow Foundation](http://go.microsoft.com/fwlink?LinkID=65005)
- [Vývoj pracovních postupů](http://go.microsoft.com/fwlink?LinkID=65010)
- [Vývoj aktivit pracovního postupu](http://go.microsoft.com/fwlink?LinkID=65023)