---
title: IDebugPortEx2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPortEx2
helpviewer_keywords:
- IDebugPortEx2 interface
ms.assetid: 144724d0-38ee-4c9b-87ca-8a504371182b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fafa6b5197413d196d080b33b2b2646ed09966b1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54972167"
---
# <a name="idebugportex2"></a>IDebugPortEx2
Toto rozhraní umožňuje relace ladění správci řízení aplikací a procesů spuštěných na portu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugPortEx2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Dodavatel port. Tento vlastní port implementuje toto rozhraní na stejný objekt, který implementuje [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md).  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání SDM [QueryInterface](/cpp/atl/queryinterface) na `IDebugPort2` rozhraní k získání tohoto rozhraní.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugPortEx2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)|Spustí spustitelný soubor.|  
|[ResumeProcess](../../../extensibility/debugger/reference/idebugportex2-resumeprocess.md)|Pokračuje v provádění procesu.|  
|[CanTerminateProcess](../../../extensibility/debugger/reference/idebugportex2-canterminateprocess.md)|Určuje, zda lze ukončit proces.|  
|[TerminateProcess](../../../extensibility/debugger/reference/idebugportex2-terminateprocess.md)|Ukončení procesu.|  
|[GetPortProcessId](../../../extensibility/debugger/reference/idebugportex2-getportprocessid.md)|Získá ID procesu portu samotný.|  
|[GetProgram](../../../extensibility/debugger/reference/idebugportex2-getprogram.md)|Získá program přidružený k uzlu programu.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní je obvykle privátní mezi SDM a port. Tento vlastní port dodavatelem.  
  
 V případě potřeby ladicího stroje (DE) můžete vyhledat tato rozhraní [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) předán rozhraní [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) a používat [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md) ke spuštění programu. Toto není povinné však a Zavedenými můžete dělat cokoli, co je potřeba udělat pro spuštění programu požadavku.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: portpriv.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)