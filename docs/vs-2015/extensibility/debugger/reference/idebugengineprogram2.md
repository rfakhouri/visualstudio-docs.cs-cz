---
title: IDebugEngineProgram2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugEngineProgram2
helpviewer_keywords:
- IDebugEngineProgram2 interface
ms.assetid: 151003a9-2e4d-4acf-9f4d-365dfa6b9596
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 2c265cbfc89d0b637b1d2f37a3e3b9e948a8dd8f
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65687791"
---
# <a name="idebugengineprogram2"></a>IDebugEngineProgram2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní poskytuje podporu pro vícevláknové ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugEngineProgram2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj implementuje toto rozhraní v zájmu podpory ladění současně z více vláken. Toto rozhraní je implementováno na stejný objekt, který implementuje [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) rozhraní.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Použití [QueryInterface](https://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) získat z tohoto rozhraní `IDebugProgram2` rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugEngineProgram2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Stop](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md)|Zastaví všechna vlákna spuštěná v rámci tohoto programu.|  
|[WatchForThreadStep](../../../extensibility/debugger/reference/idebugengineprogram2-watchforthreadstep.md)|Sleduje spuštění (nebo zastavení sledování provádění) v dané vlákno.|  
|[WatchForExpressionEvaluationOnThread](../../../extensibility/debugger/reference/idebugengineprogram2-watchforexpressionevaluationonthread.md)|Umožňuje nebo zakazuje vyhodnocení výrazu, ke kterým došlo u dané vlákno, i v případě, že program je zastaven.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní v reakci na volání sady Visual Studio [IDebugProgramCreateEvent2](../../../extensibility/debugger/reference/idebugprogramcreateevent2.md) událostí a nastavení stavů "Watch pro vlákno Step" a "Watch pro výraz vyhodnocení na vlákna" programu. [Zastavit](../../../extensibility/debugger/reference/idebugengineprogram2-stop.md) se volá vždy, když program je zastavení, tato metoda dává programu příležitost dobře se ukončí všechna vlákna.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
