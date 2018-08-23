---
title: IDebugThread2 | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugThread2
helpviewer_keywords:
- IDebugThread2 interface
ms.assetid: 221b4b1b-4a26-466e-bc29-5eff800fab13
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d5a19e207e0c5f23c8f757e428789dfc265bb19b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696125"
---
# <a name="idebugthread2"></a>IDebugThread2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugThread2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugthread2).  
  
Toto rozhraní představuje vlákno spuštěné v programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugThread2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) implementuje toto rozhraní k reprezentaci vlákno provádění v jediném programu.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [getthread –](../../../extensibility/debugger/reference/idebugstackframe2-getthread.md) získat toto rozhraní představující aktivní vlákno.  
  
 Toto rozhraní se také používá při vytvoření žádosti zarážky (viz [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)).  
  
 Toto rozhraní je také vrácen při překladu mez nebo Chyba zarážky (viz [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md) a [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)).  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugThread2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)|Načte seznam rámce zásobníku pro toto vlákno.|  
|[GetName –](../../../extensibility/debugger/reference/idebugthread2-getname.md)|Získá název vlákna.|  
|[Setthreadname –](../../../extensibility/debugger/reference/idebugthread2-setthreadname.md)|Nastaví název vlákna.|  
|[GetProgram](../../../extensibility/debugger/reference/idebugthread2-getprogram.md)|Získá program, ve kterém je spuštěn podproces.|  
|[CanSetNextStatement](../../../extensibility/debugger/reference/idebugthread2-cansetnextstatement.md)|Určuje, zda lze nastavit další příkaz ke kontextu daného zásobník snímků a kód.|  
|[SetNextStatement](../../../extensibility/debugger/reference/idebugthread2-setnextstatement.md)|Nastaví další příkaz na daném zásobníku rámce a kód kontextu.|  
|[GetThreadId](../../../extensibility/debugger/reference/idebugthread2-getthreadid.md)|Získá identifikátor systému.|  
|[Pozastavit](../../../extensibility/debugger/reference/idebugthread2-suspend.md)|Pozastaví vlákno.|  
|[Obnovení](../../../extensibility/debugger/reference/idebugthread2-resume.md)|Obnoví vlákno.|  
|[GetThreadProperties](../../../extensibility/debugger/reference/idebugthread2-getthreadproperties.md)|Získá vlastnosti, které popisují vlákno.|  
|[GetLogicalThread](../../../extensibility/debugger/reference/idebugthread2-getlogicalthread.md)|Získá logické vlákno přidružené k této fyzické vlákno.|  
  
## <a name="remarks"></a>Poznámky  
 Vzhledem k tomu, že jedno fyzické vlákno lze spustit ve více programech, více než jedna `IDebugThread2` z více než jeden program může představovat stejné fyzické vlákno.  
  
 Pokud dojde k zarážky nebo výjimky, události odesílají volání [události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md). Jeden z argumentů této metodě je `IDebugThread2` rozhraní představující aktuální vlákno. [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md) slouží k získání [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) rozhraní pro aktuální rámec zásobníku.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [Události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [Getthread –](../../../extensibility/debugger/reference/idebugstackframe2-getthread.md)   
 [BP_REQUEST_INFO](../../../extensibility/debugger/reference/bp-request-info.md)   
 [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)

