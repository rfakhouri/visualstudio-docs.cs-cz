---
title: Zobrazení aktivit (starší verze) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- activities, activity views
- views, activity
- activity views
ms.assetid: 83dc68cd-2cb2-45c2-9a6e-10d82053171a
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 62b3c9185226512ff28c8d028cd0ba7d33b0f12f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62977451"
---
# <a name="activity-views-legacy"></a>Zobrazení aktivit (starší verze)
Řada aktivit poskytované [!INCLUDE[wf](../includes/wf-md.md)], ze které pracovní postupy se skládají, mají několik zobrazení návrhu k dispozici ve starší [!INCLUDE[wfd1](../includes/wfd1-md.md)]. Při přetažení Návrhář aktivity z **nástrojů** na návrhovou plochu a po tomto datu pokaždé, když vyberete aktivitu, můžete přepínat mezi zobrazeními návrhů pomocí **pracovního postupu**nabídek nebo kliknutím pravým tlačítkem myši vybranou aktivitou. Navíc při přesunutí ukazatele myši název vybrané aktivity rozevírací seznam karet se zobrazí sada můžete přepínat mezi různá zobrazení.  
  
 Každá aktivita má alespoň jedno zobrazení; Toto je výchozí zobrazení zobrazí při přetažení Návrhář aktivity z **nástrojů** na návrhovou plochu. Tato aktivita výchozí zobrazení je k dispozici jako **zobrazení [typ aktivity]** možnost nabídkách a na kartě, například **zobrazení paralelní**. Většina aktivit má další zobrazení a různé aktivity mohou mít různá zobrazení. Například [aktivity typu TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093) kompenzace zobrazení má aktivita a [EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030) události má aktivita zobrazení. Řada aktivit, které jsou součástí Windows Workflow Foundation má **obslužná rutina zrušení zobrazení** a **zobrazení chyb** návrh zobrazení zobrazení [CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050) a [typu FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) k nim má přiřazené.  
  
 Následující tabulka uvádí název a popis jednotlivých zobrazení.  
  
|Možnost nabídky nebo karty|Popis|  
|----------------------|-----------------|  
|**Zobrazení [typ aktivity]**|Tato možnost nabídky nebo karta zobrazit výchozí grafická reprezentace vybranou aktivitou.|  
|**Zobrazit obslužný podproces příkazu Storno**|Tuto možnost nabídky nebo kartu pro zobrazení [CancellationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65050) spojené s vybranou aktivitou.|  
|**Obslužná rutina chyb zobrazení**|Tuto možnost nabídky nebo kartu pro zobrazení [typu FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) spojené s vybranou aktivitou.|  
|**Zobrazit obslužný podproces kompenzace**|Tuto možnost nabídky nebo kartu pro zobrazení [CompensationHandlerActivity](http://go.microsoft.com/fwlink?LinkID=65053) spojené s vybranou [aktivity typu TransactionScopeActivity](http://go.microsoft.com/fwlink?LinkID=65093).|  
|**Obslužnou rutinu události zobrazení**|Tuto možnost nabídky nebo kartu pro zobrazení [aktivitu typu EventHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65018) spojené s vybranou [EventHandlingScopeActivity](http://go.microsoft.com/fwlink?LinkID=65030).|  
  
 Informace o podobné zobrazení najdete v tématu [zobrazení sekvenčního pracovního postupu (starší verze)](../workflow-designer/sequential-workflow-views-legacy.md).  
  
## <a name="see-also"></a>Viz také  
 [Aktivity starších verzí pracovních postupů](../workflow-designer/legacy-workflow-activities.md)   
 [Zobrazení sekvenčního pracovního postupu (starší verze)](../workflow-designer/sequential-workflow-views-legacy.md)