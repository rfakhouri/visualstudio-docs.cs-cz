---
title: "Ladění pracovních ze vzdáleného počítače (zastaralé) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- workflows, debugging remotely
- debugging workflows, remotely
- remote debugging, workflows
- debugging, remote
ms.assetid: 44eaec8f-9959-4ae7-a374-670946f933c1
caps.latest.revision: "6"
author: ErikRe
ms.author: erikre
manager: erikre
ms.workload: multiple
ms.openlocfilehash: b4b9207702e6b4c3b93838eccfe1da15c42b5baa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="debugging-workflows-from-a-remote-computer-legacy"></a>Ladění pracovních ze vzdáleného počítače (zastaralé)
Toto téma popisuje postup ladění vzdáleného starší [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikace, které jsou vytvořeny pomocí starší verze [!INCLUDE[wfd1](../workflow-designer/includes/wfd1_md.md)]. Pomocí starší verze [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] když aplikace potřebuje cílit buď [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].  
  
 Při instalaci [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)], jednu z možností instalace součásti je k instalaci [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)] ladicího programu pro [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)]. Tím se nainstaluje komponenty vzdáleného ladění. Tyto komponenty vzdáleného ladění musí být nainstalován v počítači, který cílení pro vzdálené pracovní postup ladění.  
  
 Kromě toho je sestavení obsahující definice pracovního postupu starší verze pracovního postupu, který ladíte ve vzdáleném počítači musí být nainstalován v globální mezipaměti sestavení (GAC) z místního počítače, který se ladění z. Například pokud je starší verze pracovní postup spuštěný ve vzdáleném počítači A a ladíte z místního počítače B, definice pracovního postupu musí existovat v mezipaměti GAC počítače B. To umožňuje návrháře k deserializaci a zobrazení v počítači B značka pracovního postupu pracovního postupu, který běží na počítači A. vzdáleně Další informace o globální mezipaměti sestavení najdete v knihovně MSDN.  
  
 [!INCLUDE[wf2](../workflow-designer/includes/wf2_md.md)]vzdálené ladění funguje stejně jako vzdálené ladění pro ostatní [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] součásti. Další informace najdete v tématu [!INCLUDE[vs_current_long](../misc/includes/vs_current_long_md.md)] vzdálené ladění v knihovně MSDN.  
  
## <a name="see-also"></a>Viz také  
 [Ladění starších verzí pracovních postupů](../workflow-designer/debugging-legacy-workflows.md)