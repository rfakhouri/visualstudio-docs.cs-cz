---
title: Zobrazení sekvenčního pracovního postupu (starší verze) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- sequential workflow views
- sequential workflows, views
ms.assetid: 135f24b9-1b37-442b-9ef8-f0f2108a3212
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 97d13a86e8bade0855c60326996a192a0d0331b3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62938540"
---
# <a name="sequential-workflow-views-legacy"></a>Zobrazení sekvenčního pracovního postupu (starší verze)
[!INCLUDE[vs2010](../includes/vs2010-md.md)] poskytuje starší verze [!INCLUDE[wfd1](../includes/wfd1-md.md)] , který lze použít k cíli [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] nebo [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)].  
  
 [!INCLUDE[wfd2](../includes/wfd2-md.md)] Poskytuje způsob, jak vytvořit graficky [!INCLUDE[wf](../includes/wf-md.md)] aplikací pomocí známé [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] uživatelské rozhraní. [!INCLUDE[wf](../includes/wf-md.md)] aplikace se skládají z kroků procesu pracovního postupu nazývají aktivity. Vytvoření pracovního postupu, tvoří aktivity na návrhové ploše přetažením návrháři jejich odpovídajících aktivit z **nástrojů** na návrhovou plochu.  
  
 Při vytváření sekvenčního pracovního postupu, který je [SequentialWorkflowActivity](http://go.microsoft.com/fwlink?LinkID=65040), jsou k dispozici tři zobrazení pracovního postupu. Tato zobrazení jsou přístupné **pracovního postupu** nabídky a v místní nabídce na návrhové ploše.  
  
 Následující tabulka uvádí název a popis jednotlivých zobrazení.  
  
|Možnost nabídky nebo karty|Popis|  
|----------------------|-----------------|  
|**Zobrazení sekvenčního pracovního postupu**|Klikněte pravým tlačítkem na návrhové ploše a vyberte **zobrazení sekvenčního pracovního postupu** možnosti v místní nabídce se zobrazí **sekvenčního pracovního postupu** zobrazení, které ukazuje závislosti aktivit grafické reprezentace sekvenčního pracovního postupu. Nebo vyberte **zobrazení sekvenčního pracovního postupu** z **pracovního postupu** nabídky.|  
|**Zobrazit obslužný podproces příkazu Storno**|Klikněte pravým tlačítkem na návrhové ploše a vyberte **obslužná rutina zrušení zobrazení** možnosti v místní nabídce se zobrazí **sekvenčního pracovního postupu** zobrazení, která ukazuje [CancellationHandlerActivity ](http://go.microsoft.com/fwlink?LinkID=65050) aktivity související s pracovním postupem. Nebo vyberte **obslužná rutina zrušení zobrazení** z **pracovního postupu** nabídky.|  
|**Obslužná rutina chyb zobrazení**|Klikněte pravým tlačítkem na návrhové ploše a vyberte **obslužná rutina chyb zobrazení** možnosti v místní nabídce se zobrazí **chyby** zobrazení, která ukazuje [typu FaultHandlersActivity](http://go.microsoft.com/fwlink?LinkID=65055) aktivity související s pracovním postupem. Nebo vyberte **obslužná rutina chyb zobrazení** z **pracovního postupu** nabídky.|  
  
 Další informace o podobné zobrazení najdete v tématu [zobrazení aktivit (starší verze)](../workflow-designer/activity-views-legacy.md).  
  
## <a name="see-also"></a>Viz také  
 [Zobrazení aktivit (starší verze)](../workflow-designer/activity-views-legacy.md)   
 [Vytváření projektů pracovních postupů starších verzí](../workflow-designer/creating-legacy-workflow-projects.md)   
 [Režimy pro tvorbu pracovního postupu](http://go.microsoft.com/fwlink?LinkID=65014)