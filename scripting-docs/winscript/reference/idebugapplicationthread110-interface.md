---
title: Idebugapplicationthread110 – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThread110 Interface
ms.assetid: 25bc351f-3451-4387-9302-078f6292ddff
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 170b345bdb4587d1fd29c1f0f906df0157abd877
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54348916"
---
# <a name="idebugapplicationthread110-interface"></a>IDebugApplicationThread110 – rozhraní
Poskytuje další funkce pro [idebugapplicationthread – rozhraní](../../winscript/reference/idebugapplicationthread-interface.md) rozhraní.  
  
> [!IMPORTANT]
>  Toto rozhraní je implementováno komponentou PDM verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="methods"></a>Metody  
 `IDebugApplicationThread110` Rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugApplicationThread110::AsynchronousCallIntoThread](../../winscript/reference/idebugapplicationthread110-asynchronouscallintothread.md)|Provede asynchronní volání v hlavním vlákně.|  
|[IDebugApplicationThread110::GetActiveThreadRequestCount](../../winscript/reference/idebugapplicationthread110-getactivethreadrequestcount.md)|Počet kolik požadavků vlákno z vlákna PDM přepínání mechanismy se právě zpracovává. Obvykle 0 nebo 1, ale je možné, že to být vyšší, pokud se jedno volání vlákna spustí zpracování, ale aktivuje synchronní volání mimo vlákno nebo jinak pozastaví vlákno (například, že se budou spouštět IDebugApplicationEvents událost, která je vydané pro ladicí program vlákno)|  
|[IDebugApplicationThread110::IsSuspendedForBreakPoint](../../winscript/reference/idebugapplicationthread110-issuspendedforbreakpoint.md)|[IDebugApplicationThreadEvents110::OnSuspendForBreakPoint](../../winscript/reference/idebugapplicationthreadevents110-onsuspendforbreakpoint.md) volal v tomto vláknu a zatím není dokončený.|  
|[IDebugApplicationThread110::IsThreadCallable](../../winscript/reference/idebugapplicationthread110-isthreadcallable.md)|Toto vlákno je ve stavu, která dokáže zpracovávat volání bylo vytvořeno s použitím vlákno PDM přepínání mechanismy (například SynchronousCallInThread).|