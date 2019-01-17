---
title: Idebugapplicationthreadevents110 – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: db20440d4dc797ce9a0f21c3ac0c6c89c5d4e036
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348240"
---
# <a name="idebugapplicationthreadevents110-interface"></a>IDebugApplicationThreadEvents110 – rozhraní
Přidá další vlákno události. Tyto události jsou jenom místní. To znamená, že k odběru je pouze v procesu se ladit, používá [IConnectionPoint](http://go.microsoft.com/fwlink/?LinkId=232738) dokáží a zrušíte avízo o metod na objekty vlákna aplikace PDM (objekty, které implementují [idebugapplicationthread – Rozhraní](../../winscript/reference/idebugapplicationthread-interface.md)). K nim dojde ve vlákně, které pocházejí z.  
  
> [!IMPORTANT]
>  Toto rozhraní je implementováno komponentou PDM verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="methods"></a>Metody  
 `IDebugActivationThreadEvents110` Rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugApplicationThreadEvents110 ::OnBeginThreadRequest](../../winscript/reference/idebugapplicationthreadevents110-onbeginthreadrequest.md)|Volání do vlákna použití vlákna PDM byl zahájen přechod.|  
|[IDebugApplicationThreadEvents110::OnResumeFromBreakPoint](../../winscript/reference/idebugapplicationthreadevents110-onresumefrombreakpoint.md)|Vlákno obnovuje od bodu přerušení a bude aktivováno jednou znovu.|  
|[IDebugApplicationThreadEvents110::OnSuspendForBreakPoint](../../winscript/reference/idebugapplicationthreadevents110-onsuspendforbreakpoint.md)|Vlákno je pozastavení pro zarážku a dokáže zpracovat volání, které vyžadují plně pozastavit vlákna.|  
|[IDebugApplicationThreadEvents110::OnThreadRequestComplete](../../winscript/reference/idebugapplicationthreadevents110-onthreadrequestcomplete.md)|Volání do vlákna použití vlákna PDM přepínání byla dokončena.|