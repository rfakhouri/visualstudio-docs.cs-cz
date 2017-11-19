---
title: IDebugEngine2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugEngine2
helpviewer_keywords: IDebugEngine2 interface
ms.assetid: 1f0e9ac0-6dfb-461a-976c-888d82144cdb
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f684a29eea526f7725e8a876f53453512f65dadc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugengine2"></a>IDebugEngine2
Toto rozhraní představuje modul ladění (DE). Slouží ke správě různých aspektů relaci ladění ve vytváření zarážky pro nastavení a vymazání výjimky.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugEngine2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní je implementováno modulem vlastní DE ke správě ladění programů. Toto rozhraní je implementováno modulem DE.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je volána službou Správce ladicí relace (SDM) ke správě relaci ladění, včetně Správa výjimek, vytváření zarážky a reagování na synchronní události poslal DE.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugEngine2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md)|Vytvoří enumerátor pro všechny programy programem Zavedenými.|  
|[Připojení](../../../extensibility/debugger/reference/idebugengine2-attach.md)|Připojí Zavedenými programu.|  
|[CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md)|Vytvoří čekající zarážek v DE.|  
|[SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)|Určuje, jak je DE pracovat s danou výjimka.|  
|[RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)|Odebere zadané výjimky, aby se již zpracovává modul ladění.|  
|[RemoveAllSetExceptions](../../../extensibility/debugger/reference/idebugengine2-removeallsetexceptions.md)|Odebere seznamu výjimek nastavený rozhraní IDE pro konkrétní architekturu běhu a jazyka.|  
|[GetEngineID](../../../extensibility/debugger/reference/idebugengine2-getengineid.md)|Získá identifikátor GUID je DE.|  
|[DestroyProgram](../../../extensibility/debugger/reference/idebugengine2-destroyprogram.md)|Informuje o Německo, který byl zadaný program atypicky ukončen a který by měl DE vyčistit všechny odkazy na program a odeslat program destroy událostí.|  
|[ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)|Voláno rozhraním SDM označíte, že synchronní ladění událostí, dříve posílá DE SDM, přijala a zpracovala.|  
|[Setlocale –](../../../extensibility/debugger/reference/idebugengine2-setlocale.md)|Nastaví národního prostředí je DE.|  
|[SetRegistryRoot](../../../extensibility/debugger/reference/idebugengine2-setregistryroot.md)|Nastaví kořenový klíč registru aktuálně používán DE.|  
|[SetMetric](../../../extensibility/debugger/reference/idebugengine2-setmetric.md)|Nastaví metriky.|  
|[CauseBreak](../../../extensibility/debugger/reference/idebugengine2-causebreak.md)|Požadavky, že všechny programy programem tento DE zastavit provádění při příštím jeden z jejich vláken pokusí o spuštění.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [GetEngine](../../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md)