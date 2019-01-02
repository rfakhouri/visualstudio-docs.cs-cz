---
title: IDebugProgramEx2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgramEx2
helpviewer_keywords:
- IDebugProgramEx2 interface
ms.assetid: 663359ed-635a-4539-addb-0cc52f19d1bd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3131dae9d9bf715d3927f9654224cab3d6a36d53
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53907876"
---
# <a name="idebugprogramex2"></a>IDebugProgramEx2
Toto rozhraní umožňuje relace ladění správci připojit k programu a získat uzel program přidružený k programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugProgramEx2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Dodavatel port. Tento vlastní port implementuje toto rozhraní na stejný objekt jako [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) rozhraní, aby bylo možné nechat SDM, zatímco ve stejnou dobu umožní dodavatele portu můžete sledovat všechny relace připojen k připojení k programu program. Pokud zvolí dodavatele port. Tento vlastní port toto rozhraní implementovat.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání SDM [QueryInterface](/cpp/atl/queryinterface) na `IDebugProgram2` rozhraní k získání tohoto rozhraní ke sledování relací, které jste připojili k programy.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugProgramEx2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Attach](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)|Program připojí k relaci.|  
|[GetProgramNode](../../../extensibility/debugger/reference/idebugprogramex2-getprogramnode.md)|Získá uzel program přidružený k programu.|  
  
## <a name="remarks"></a>Poznámky  
 Toto rozhraní je privátní mezi SDM a program.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Portpriv.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)