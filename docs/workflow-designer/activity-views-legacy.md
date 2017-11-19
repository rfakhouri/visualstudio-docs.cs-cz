---
title: "Zobrazení aktivity (zastaralé) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- activities, activity views
- views, activity
- activity views
ms.assetid: 83dc68cd-2cb2-45c2-9a6e-10d82053171a
caps.latest.revision: "5"
author: ErikRe
ms.author: erikre
manager: erikre
ms.openlocfilehash: 50f57684db32f601bd4cbf870456da458aa5ce7c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="activity-views-legacy"></a>Zobrazení aktivity (zastaralé)
Řada aktivit poskytované [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)], ze které pracovní postupy se skládá, máte několik zobrazení návrhu k dispozici v starší verze [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]. Při přetažení Návrhář aktivity z **sada nástrojů** na návrhovou plochu a následně vždy, když vyberete aktivitu, můžete přepínat mezi různých zobrazení pomocí **pracovního postupu**nabídky nebo kliknutím pravým tlačítkem na vybrané aktivity. Navíc při přesunutí ukazatele nad název vybranou aktivitou, rozevírací seznam sadu karet se zobrazí, můžete přepínat mezi různá zobrazení.  
  
 Každá aktivita má alespoň jedno zobrazení; Toto je výchozí zobrazení zobrazí při přetažení Návrhář aktivity z **sada nástrojů** na návrhovou plochu. Toto zobrazení výchozí aktivity je k dispozici jako **zobrazení [typ aktivity]** možnost nabídkách a na kartě, například **zobrazení paralelní**. Většina aktivity má další zobrazení a různé aktivity může mít různá zobrazení. Například [aktivity typu TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093) aktivita má kompenzace zobrazení a [EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030) aktivita má události zobrazení. Řada aktivit, které jsou součástí Windows Workflow Foundation mít **obslužná rutina zrušit zobrazení** a **zobrazení chyb** navrhování pohledů pro zobrazení [CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050) a [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) s nimi spojených.  
  
 Následující tabulka uvádí název a popis jednotlivých zobrazení.  
  
|Možnost nabídky nebo karty|Popis|  
|----------------------|-----------------|  
|**Zobrazení [typ aktivity]**|Vyberte tuto možnost nabídky nebo kartě Zobrazit výchozí grafické znázornění vybranou aktivitou.|  
|**Obslužná rutina zrušit zobrazení**|Tuto možnost vyberte, nabídky nebo kartě zobrazení pro zobrazení [CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050) spojené s vybranou aktivitou.|  
|**Obslužná rutina chyb zobrazení**|Tuto možnost vyberte, nabídky nebo kartě zobrazení pro zobrazení [FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) spojené s vybranou aktivitou.|  
|**Obslužná rutina kompenzace zobrazení**|Tuto možnost vyberte, nabídky nebo kartě zobrazení pro zobrazení [CompensationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65053) spojené s vybranou [aktivity typu TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093).|  
|**Obslužnou rutinu události zobrazení**|Tuto možnost vyberte, nabídky nebo kartě zobrazení pro zobrazení [aktivitu typu EventHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65018) spojené s vybranou [EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030).|  
  
 Informace o podobné zobrazení najdete v tématu [sekvenční pracovní postup zobrazení (zastaralé)](../workflow-designer/sequential-workflow-views-legacy.md).  
  
## <a name="see-also"></a>Viz také  
 [Aktivity pracovního postupu starší verze](../workflow-designer/legacy-workflow-activities.md)   
 [Sekvenční pracovní postup zobrazení (zastaralé)](../workflow-designer/sequential-workflow-views-legacy.md)