---
title: Idebugapplication110 – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplication110 Interface
ms.assetid: ae943133-eb65-4ddc-a29f-9280a82dd8d6
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3c040df103bac464e4f440f23674da966063f0ae
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58149666"
---
# <a name="idebugapplication110-interface"></a>IDebugApplication110 – rozhraní
`IDebugApplication110` Rozhraní rozšiřuje funkce [idebugapplication – rozhraní](../../winscript/reference/idebugapplication-interface.md). Instance tohoto rozhraní můžete získat pomocí volání QueryInterface u implementace [idebugapplication – rozhraní](../../winscript/reference/idebugapplication-interface.md).  
  
> [!IMPORTANT]
>  Toto rozhraní je implementováno komponentou PDM verze 11.0 nebo novější. Nachází se v souboru activdbg100.h.  
  
## <a name="methods"></a>Metody  
 `IDebugApplication110` Rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugApplication110::SynchronousCallInMainThread](../../winscript/reference/idebugapplication110-synchronouscallinmainthread.md)|Díky synchronní volání v hlavním vlákně.|  
|[IDebugApplication110::AsynchronousCallInMainThread](../../winscript/reference/idebugapplication110-asynchronouscallinmainthread.md)|Provede asynchronní volání v hlavním vlákně.|  
|[IDebugApplication110::CallableWaitForHandles](../../winscript/reference/idebugapplication110-callablewaitforhandles.md)|Čeká na kterýkoli z úchytů zadané má být signalizován zároveň umožní volání mezi vlákny který se má publikovat pro toto vlákno. Tato metoda musí volat z vlákna ladicího programu.|