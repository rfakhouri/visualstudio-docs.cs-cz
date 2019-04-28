---
title: Idebugapplicationthreadevents110 – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThreadEvents110 Interface
ms.assetid: 91a98b0e-7c81-4118-af75-82f75fd4f25a
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b2cdde46484f95aa57404ebe6b6cb4c86ef458c9
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63440508"
---
# <a name="idebugapplicationthreadevents110-interface"></a>IDebugApplicationThreadEvents110 – rozhraní
Přidá další vlákno události. Tyto události jsou jenom místní. To znamená, že k odběru je pouze v procesu se ladit, používá [IConnectionPoint](http://go.microsoft.com/fwlink/?LinkId=232738) dokáží a zrušíte avízo o metod na objekty vlákna aplikace PDM (objekty, které implementují [idebugapplicationthread – Rozhraní](../../winscript/reference/idebugapplicationthread-interface.md)). K nim dojde ve vlákně, které pocházejí z.  
  
> [!IMPORTANT]
> Toto rozhraní je implementováno komponentou PDM verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="methods"></a>Metody  
 `IDebugActivationThreadEvents110` Rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugApplicationThreadEvents110 ::OnBeginThreadRequest](../../winscript/reference/idebugapplicationthreadevents110-onbeginthreadrequest.md)|Volání do vlákna použití vlákna PDM byl zahájen přechod.|  
|[IDebugApplicationThreadEvents110::OnResumeFromBreakPoint](../../winscript/reference/idebugapplicationthreadevents110-onresumefrombreakpoint.md)|Vlákno obnovuje od bodu přerušení a bude aktivováno jednou znovu.|  
|[IDebugApplicationThreadEvents110::OnSuspendForBreakPoint](../../winscript/reference/idebugapplicationthreadevents110-onsuspendforbreakpoint.md)|Vlákno je pozastavení pro zarážku a dokáže zpracovat volání, které vyžadují plně pozastavit vlákna.|  
|[IDebugApplicationThreadEvents110::OnThreadRequestComplete](../../winscript/reference/idebugapplicationthreadevents110-onthreadrequestcomplete.md)|Volání do vlákna použití vlákna PDM přepínání byla dokončena.|