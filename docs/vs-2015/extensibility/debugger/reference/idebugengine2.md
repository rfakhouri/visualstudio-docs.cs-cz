---
title: IDebugEngine2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugEngine2
helpviewer_keywords:
- IDebugEngine2 interface
ms.assetid: 1f0e9ac0-6dfb-461a-976c-888d82144cdb
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0c011a530bbd4323546257a40334a4b8a0f57bdb
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54790724"
---
# <a name="idebugengine2"></a>IDebugEngine2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní představuje ladicího stroje (DE). Používá se ke správě různých aspektů ladicí relace, od vytváření zarážek pro nastavení a vymazání výjimky.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugEngine2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Toto rozhraní implementují vlastní DE ke správě ladění programů. Pomocí DE musí implementovat toto rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Toto rozhraní je volán Správce ladění relace (SDM) ke správě relaci ladění, včetně správy výjimky, vytvořením zarážky a reagovat na synchronní události odeslané DE.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugEngine2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md)|Vytvoří čítač pro všechny programy, které jsou právě laděny ve Zavedenými.|  
|[Attach](../../../extensibility/debugger/reference/idebugengine2-attach.md)|Zavedenými připojí k programu.|  
|[CreatePendingBreakpoint](../../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md)|Vytvoří v DE čekající zarážkou.|  
|[SetException](../../../extensibility/debugger/reference/idebugengine2-setexception.md)|Určuje, jak DE pracovat s danou výjimku.|  
|[RemoveSetException](../../../extensibility/debugger/reference/idebugengine2-removesetexception.md)|Odebere Zadaná výjimka, takže už je zpracována ladicího stroje.|  
|[RemoveAllSetExceptions](../../../extensibility/debugger/reference/idebugengine2-removeallsetexceptions.md)|Odebere seznam výjimek, integrovaném vývojovém prostředí má nastavit pro konkrétní architekturu za běhu nebo jazyk.|  
|[GetEngineID](../../../extensibility/debugger/reference/idebugengine2-getengineid.md)|Získá identifikátor GUID je DE.|  
|[DestroyProgram](../../../extensibility/debugger/reference/idebugengine2-destroyprogram.md)|Informuje, DE, který byl zadaný program atypicky ukončen a, DE byste měli odstranit všechny odkazy na program a odeslat program zrušení události.|  
|[ContinueFromSynchronousEvent](../../../extensibility/debugger/reference/idebugengine2-continuefromsynchronousevent.md)|Je voláno SDM k označení, že synchronní ladění události, DE dříve odeslaných do SDM, přijala a zpracovala.|  
|[SetLocale](../../../extensibility/debugger/reference/idebugengine2-setlocale.md)|Nastaví národní prostředí DE.|  
|[SetRegistryRoot](../../../extensibility/debugger/reference/idebugengine2-setregistryroot.md)|Nastaví kořenový klíč registru aktuálně používán DE.|  
|[SetMetric](../../../extensibility/debugger/reference/idebugengine2-setmetric.md)|Nastaví metriku.|  
|[CauseBreak](../../../extensibility/debugger/reference/idebugengine2-causebreak.md)|Požadavky, že všechny programy, které jsou právě laděny ve tomto DE zastavit provádění, které se jeden z jejich vláken pokusí o spuštění.|  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Události](../../../extensibility/debugger/reference/idebugeventcallback2-event.md)   
 [GetEngine](../../../extensibility/debugger/reference/idebugenginecreateevent2-getengine.md)
