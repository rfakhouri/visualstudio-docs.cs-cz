---
title: Idebugapplicationthread – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplicationThread interface
ms.assetid: f869c328-4409-4b74-a6c3-9e63fc58c63d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a464085eddbea4f5d29c684c0f1dabc6f853b6d1
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58158786"
---
# <a name="idebugapplicationthread-interface"></a>IDebugApplicationThread – rozhraní
Umožňuje jazykové moduly a hostitelům poskytují synchronizaci vláken a spravovat informace o stavu ladění specifické pro vlákno. Toto rozhraní rozšiřuje `IRemoteDebugApplicationThread` rozhraní a zajistit tak přístup bez vzdálené do vlákna.  
  
 Kromě metod zděděných z `IRemoteDebugApplicationThread`, `IDebugApplicationThread` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugApplicationThread::SynchronousCallIntoThread](../../winscript/reference/idebugapplicationthread-synchronouscallintothread.md)|Poskytuje mechanismus pro volající ke spouštění kódu v vlákna aplikace.|  
|[IDebugApplicationThread::QueryIsCurrentThread](../../winscript/reference/idebugapplicationthread-queryiscurrentthread.md)|Určuje, zda toto vlákno je aktuálně běžícímu vláknu.|  
|[IDebugApplicationThread::QueryIsDebuggerThread](../../winscript/reference/idebugapplicationthread-queryisdebuggerthread.md)|Určuje, zda toto vlákno je vlákno ladicího programu.|  
|[IDebugApplicationThread::SetDescription](../../winscript/reference/idebugapplicationthread-setdescription.md)|Nastaví popis tohoto vlákna.|  
|[IDebugApplicationThread::SetStateString](../../winscript/reference/idebugapplicationthread-setstatestring.md)|Nastaví popis stavu vlákna.|