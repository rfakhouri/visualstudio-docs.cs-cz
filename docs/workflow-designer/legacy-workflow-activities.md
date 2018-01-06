---
title: "Aktivity pracovního postupu starší verze | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- workflows, activities
- activities
- workflow activities
ms.assetid: 4af7a06b-1e82-43c8-aec8-0dc5fb63d08a
caps.latest.revision: "8"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: 756fa86cf892120b0062e2816f146425ac1b4fa3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="legacy-workflow-activities"></a>Aktivity pracovního postupu starší verze
[!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]zahrnuje výchozí sadu aktivit, které poskytují funkce pro tok řízení, podmínek, zpracování událostí, správu stavu a komunikaci s aplikacemi a službami. Při návrhu pracovních postupů, můžete použít poskytované systémem aktivity, které jsou poskytovány [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)], nebo můžete vytvořit vlastní aktivitu.  
  
 Následující tabulka uvádí [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)] sadu aktivity out-of-box framework. Mnoho, ale ne všechny tyto aktivity jsou reprezentované pomocí návrháře aktivit, které lze přistupovat z **sada nástrojů** z [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)]. Chcete-li vytvořit aktivitu, přetáhněte jeho designer z **sada nástrojů** na návrhovou plochu.  
  
|Aktivita|Popis|  
|--------------|-----------------|  
|[CallExternalMethodActivity](http://go.microsoft.com/fwlink?LinkID=65025)|Používá se **aktivita typu HandleExternalEventActivity** aktivity pro vstupní a výstupní komunikaci s místní službou. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity CallExternalMethodActivity](http://go.microsoft.com/fwlink?LinkID=65060).|  
|[CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050)|Použít tak, aby obsahovala čištění logiku pro aktivitu složené zrušena dříve, než všechny složené aktivity podřízené objekty jsou dokončení provádění. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65061).|  
|[CodeActivity](http://go.microsoft.com/fwlink?LinkID=65026)|Umožňuje přidat kód jazyka Visual Basic nebo C# do pracovního postupu. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity CodeActivity](http://go.microsoft.com/fwlink?LinkID=65062).|  
|[CompensatableSequenceActivity](http://go.microsoft.com/fwlink?LinkID=65027)|Aktivita verze [SequenceActivity](http://go.microsoft.com/fwlink?LinkID=65020). [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity CompensatableSequenceActivity](http://go.microsoft.com/fwlink?LinkID=65002).|  
|[CompensatableTransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65051)|Aktivita verze **aktivity typu TransactionScopeActivity**. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity CompensatableTransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65063).|  
|[Aktivita typu CompensateActivity](http://go.microsoft.com/fwlink?LinkID=65052)|Umožňuje volat kód vrátit zpět nebo kompenzovat operace již prováděné v tomto pracovním postupu, když dojde k chybě. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity aktivita typu CompensateActivity](http://go.microsoft.com/fwlink?LinkID=65064).|  
|[CompensationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65053)|Obálka pro jeden nebo více aktivit, které provádějí náhradu za dokončené aktivity typu TransactionScopeActivity [!INCLUDE[crdefault](../test/includes/crdefault_md.md)] [pomocí aktivity CompensationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65065).|  
|[Skupina ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017)|Provede podřízené aktivity na podmínku, která se vztahuje na základě [skupiny ConditionedActivityGroup](http://go.microsoft.com/fwlink?LinkID=65017) aktivity sám a na základě podmínek, které platí pro všechny podřízené samostatně. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí skupiny ConditionedActivityGroup aktivity](http://go.microsoft.com/fwlink?LinkID=65066).|  
|[Typu DelayActivity](http://go.microsoft.com/fwlink?LinkID=65028)|Umožňuje vytvořit zpoždění v pracovním postupu, které jsou založeny na interval časového limitu. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity typu DelayActivity](http://go.microsoft.com/fwlink?LinkID=65067).|  
|[EventDrivenActivity](http://go.microsoft.com/fwlink?LinkID=65029)|Zabalí jeden nebo více aktivit, které jsou spouštěny, když dojde k zadané události. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity EventDrivenActivity](http://go.microsoft.com/fwlink?LinkID=65068).|  
|[Aktivitu typu EventHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65018)|Poskytuje rozhraní pro přidružení událostí k aktivitě. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity aktivitu typu EventHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65069).|  
|[EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030)|Provede jeho hlavní podřízené aktivity současně se [aktivitu typu EventHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65018). [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65070).|  
|[FaultHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65054)|Používá ke zpracování výjimky typu, který určíte. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity FaultHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65071).|  
|[FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055)|Představuje složený aktivity, která má seřazený seznam podřízené aktivity typu [FaultHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65054). [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65072).|  
|[Aktivita typu HandleExternalEventActivity](http://go.microsoft.com/fwlink?LinkID=65031)|Používá ve spojení s [CallExternalMethodActivity](http://go.microsoft.com/fwlink?LinkID=65025) aktivity pro vstupní a výstupní komunikaci s místní službou. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity aktivita typu HandleExternalEventActivity](http://go.microsoft.com/fwlink?LinkID=65073).|  
|[IfElseActivity](http://go.microsoft.com/fwlink?LinkID=65033)|Testuje podmínku na každé větve a provádí aktivity na první větve, pro který se rovná podmínku **true**. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity IfElseActivity](http://go.microsoft.com/fwlink?LinkID=65074).|  
|[IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65034)|Představuje větvi [IfElseActivity](http://go.microsoft.com/fwlink?LinkID=65033). [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity IfElseBranchActivity](http://go.microsoft.com/fwlink?LinkID=65075).|  
|[Typu InvokeWebServiceActivity](http://go.microsoft.com/fwlink?LinkID=65035)|Umožňuje pracovní postup k vyvolání webové služby. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity typu InvokeWebServiceActivity](http://go.microsoft.com/fwlink?LinkID=65076).|  
|[InvokeWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65036)|Umožňuje pracovní postup k vyvolání jiného pracovního postupu. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity InvokeWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65077).|  
|[Aktivita typu ListenActivity](http://go.microsoft.com/fwlink?LinkID=65037)|Složené aktivity, který obsahuje pouze [EventDrivenActivity](http://go.microsoft.com/fwlink?LinkID=65029) podřízené aktivity. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity aktivita typu ListenActivity](http://go.microsoft.com/fwlink?LinkID=65078).|  
|[Aktivity ParallelActivity](http://go.microsoft.com/fwlink?LinkID=65038)|Poskytuje způsob, jak naplánovat dvou nebo více podřízených **SequenceActivity** větví aktivity pro zpracování ve stejnou dobu. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity aktivity ParallelActivity](http://go.microsoft.com/fwlink?LinkID=65079).|  
|[Aktivitě PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65019)|Použijte představují kolekci pravidel. Pravidlo obsahuje podmínky a výsledné akce. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity aktivitě PolicyActivity](http://go.microsoft.com/fwlink?LinkID=65004).|  
|[ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65039)|Vytvoří více instancí jedné podřízené aktivity. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity ReplicatorActivity](http://go.microsoft.com/fwlink?LinkID=65080).|  
|[SequenceActivity](http://go.microsoft.com/fwlink?LinkID=65020)|Poskytuje jednoduchý způsob, jak propojit více aktivit společně pro sekvenční provádění. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity SequenceActivity](http://go.microsoft.com/fwlink?LinkID=65081).|  
|[SetStateActivity](http://go.microsoft.com/fwlink?LinkID=65041)|Určuje přechod na nový stav. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity SetStateActivity](http://go.microsoft.com/fwlink?LinkID=65082).|  
|[StateActivity](http://go.microsoft.com/fwlink?LinkID=65042)|Představuje stav v pracovním postupu stav počítače. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity StateActivity](http://go.microsoft.com/fwlink?LinkID=65083).|  
|[StateFinalizationActivity](http://go.microsoft.com/fwlink?LinkID=65043)|Použít v [StateActivity](http://go.microsoft.com/fwlink?LinkID=65042) aktivitu jako kontejner pro podřízené aktivity, které jsou spouštěné při opuštění **StateActivity** aktivity. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity StateFinalizationActivity](http://go.microsoft.com/fwlink?LinkID=65008).|  
|[StateInitializationActivity](http://go.microsoft.com/fwlink?LinkID=65044)|Použít v [StateActivity](http://go.microsoft.com/fwlink?LinkID=65042) aktivitu jako kontejner pro podřízené aktivity, které jsou spouštěny při zadávání **StateActivity** aktivity. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity StateInitializationActivity](http://go.microsoft.com/fwlink?LinkID=65006).|  
|[SuspendActivity](http://go.microsoft.com/fwlink?LinkID=65056)|Pozastaví operaci pracovní postup, chcete-li povolit zásahu v případě nějaké chyby, které vyžadují zvláštní pozornost. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity SuspendActivity](http://go.microsoft.com/fwlink?LinkID=65084).|  
|[SynchronizationScopeActivity](http://go.microsoft.com/fwlink?LinkID=65057)|Provádí obsažené aktivity postupně v synchronizované doméně. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity SynchronizationScopeActivity](http://go.microsoft.com/fwlink?LinkID=65085).|  
|[TerminateActivity](http://go.microsoft.com/fwlink?LinkID=65058)|Umožňuje okamžitě ukončení operace pracovního postupu v případě chybový stav. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity TerminateActivity](http://go.microsoft.com/fwlink?LinkID=65086).|  
|[ThrowActivity](http://go.microsoft.com/fwlink?LinkID=65059)|Umožňuje zachytit obchodní výjimky vydané jako součást procesu metadata pro pracovní postup. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity ThrowActivity](http://go.microsoft.com/fwlink?LinkID=65087).|  
|[Aktivita typu TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093)|Poskytuje rozhraní pro transakce a výjimek. Další informace najdete v tématu [pomocí aktivity typu TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65088).|  
|[Aktivita WebServiceFaultActivity](http://go.microsoft.com/fwlink?LinkID=65046)|Umožňuje modelu výskytem chybu webové služby. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity Aktivita WebServiceFaultActivity](http://go.microsoft.com/fwlink?LinkID=65089).|  
|[Aktivita WebServiceInputActivity](http://go.microsoft.com/fwlink?LinkID=65047)|Přijímá data z webové služby. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity aktivitu WebServiceInputActivity](http://go.microsoft.com/fwlink?LinkID=65090).|  
|[Aktivita WebServiceOutputActivity](http://go.microsoft.com/fwlink?LinkID=65048)|Odpoví na žádost o službu webové provedené v pracovním postupu. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity aktivita WebServiceOutputActivity](http://go.microsoft.com/fwlink?LinkID=65092).|  
|[Aktivita typu WhileActivity](http://go.microsoft.com/fwlink?LinkID=65049)|Umožňuje pracovní postup opakovat až do splnění podmínky. [!INCLUDE[crdefault](../test/includes/crdefault_md.md)][Pomocí aktivity aktivita typu WhileActivity](http://go.microsoft.com/fwlink?LinkID=65091).|  
  
 [!INCLUDE[crabout](../test/includes/crabout_md.md)]vytváření vlastních aktivit, najdete v části [vývoj vlastních aktivit](http://go.microsoft.com/fwlink?LinkID=65023) a [pomocí návrháře starší aktivity](../workflow-designer/using-the-legacy-activity-designer.md).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Zobrazení aktivit (starší verze)](../workflow-designer/activity-views-legacy.md)  
 Popisuje zobrazení různých aktivit.  
  
 [Postupy: Přidání aktivit do panelu nástrojů (starší verze)](../workflow-designer/how-to-add-activities-to-the-toolbox-legacy.md)  
 Ukazuje, jak přidat aktivity do sady nástrojů.  
  
 [Postupy: Vytvoření podmínky deklarativního pravidla (starší verze)](../workflow-designer/how-to-create-a-declarative-rule-condition-legacy.md)  
 Ukazuje postup vytvoření podmínku deklarativní pravidla.  
  
 [Postupy: Vytvoření sady pravidel aktivit zásad (starší verze)](../workflow-designer/how-to-create-a-policyactivity-rule-set-legacy.md)  
 Ukazuje postup vytvoření sady pravidel aktivitě PolicyActivity.  
  
 [Postupy: implementace kontraktu operace s WCF (zastaralé)](../workflow-designer/how-to-implement-a-windows-communication-foundation-contract-operation-legacy.md)  
 Zobrazuje kroky pro implementaci [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] smlouvy operaci.  
  
 [Postupy: volání operaci kontraktu WCF (zastaralé)](../workflow-designer/how-to-invoke-a-windows-communication-foundation-contract-operation-legacy.md)  
 Ukazuje postup vyvolání [!INCLUDE[indigo2](../workflow-designer/includes/indigo2_md.md)] smlouvy operaci.  
  
## <a name="see-also"></a>Viz také  
 [Aktivity Windows Workflow Foundation](http://go.microsoft.com/fwlink?LinkID=65005)   
 [Vývoj pracovních postupů](http://go.microsoft.com/fwlink?LinkID=65010)   
 [Vývoj aktivit pracovního postupu](http://go.microsoft.com/fwlink?LinkID=65023)