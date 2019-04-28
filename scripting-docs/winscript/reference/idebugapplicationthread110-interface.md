---
title: Idebugapplicationthread110 – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
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
ms.openlocfilehash: 44df7168c241c9a750354e1a603d6c5ba96dabd2
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63440535"
---
# <a name="idebugapplicationthread110-interface"></a>IDebugApplicationThread110 – rozhraní
Poskytuje další funkce pro [idebugapplicationthread – rozhraní](../../winscript/reference/idebugapplicationthread-interface.md) rozhraní.  
  
> [!IMPORTANT]
> Toto rozhraní je implementováno komponentou PDM verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="methods"></a>Metody  
 `IDebugApplicationThread110` Rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugApplicationThread110::AsynchronousCallIntoThread](../../winscript/reference/idebugapplicationthread110-asynchronouscallintothread.md)|Provede asynchronní volání v hlavním vlákně.|  
|[IDebugApplicationThread110::GetActiveThreadRequestCount](../../winscript/reference/idebugapplicationthread110-getactivethreadrequestcount.md)|Počet kolik požadavků vlákno z vlákna PDM přepínání mechanismy se právě zpracovává. Obvykle 0 nebo 1, ale je možné, že to být vyšší, pokud se jedno volání vlákna spustí zpracování, ale aktivuje synchronní volání mimo vlákno nebo jinak pozastaví vlákno (například, že se budou spouštět IDebugApplicationEvents událost, která je vydané pro ladicí program vlákno)|  
|[IDebugApplicationThread110::IsSuspendedForBreakPoint](../../winscript/reference/idebugapplicationthread110-issuspendedforbreakpoint.md)|[IDebugApplicationThreadEvents110::OnSuspendForBreakPoint](../../winscript/reference/idebugapplicationthreadevents110-onsuspendforbreakpoint.md) volal v tomto vláknu a zatím není dokončený.|  
|[IDebugApplicationThread110::IsThreadCallable](../../winscript/reference/idebugapplicationthread110-isthreadcallable.md)|Toto vlákno je ve stavu, která dokáže zpracovávat volání bylo vytvořeno s použitím vlákno PDM přepínání mechanismy (například SynchronousCallInThread).|