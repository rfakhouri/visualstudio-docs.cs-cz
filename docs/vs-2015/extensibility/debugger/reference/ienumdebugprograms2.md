---
title: IEnumDebugPrograms2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IEnumDebugPrograms2
helpviewer_keywords:
- IEnumDebugPrograms2
ms.assetid: 7fbb8fb7-db64-4546-a364-dc668430c8af
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 8d9d1030616fa8d7f3a1bfc6b533c4ed8433ea89
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65703905"
---
# <a name="ienumdebugprograms2"></a>IEnumDebugPrograms2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Toto rozhraní vytvoří výčet programy spuštěné v aktuální relaci ladění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IEnumDebugPrograms2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) implementuje toto rozhraní uvést seznam programů, které jsou právě laděny ve DE.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Visual Studio volání [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md) získat toto rozhraní. [EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md) se používá sada Visual Studio.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IEnumDebugPrograms2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugprograms2-next.md)|Načte zadaný počet programy v sekvenci výčtu.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugprograms2-skip.md)|Vynechá zadaný počet programy v sekvenci výčtu.|  
|[Reset](../../../extensibility/debugger/reference/ienumdebugprograms2-reset.md)|Návrat na začátek sekvence výčtu.|  
|[Clone](../../../extensibility/debugger/reference/ienumdebugprograms2-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor výčtu.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugprograms2-getcount.md)|Získá počet programů v enumerátor.|  
  
## <a name="remarks"></a>Poznámky  
 Visual Studio používá toto rozhraní:  
  
- Naplnění **moduly** okno (voláním [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md) a následným voláním [enummodules –](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) v každém programu).  
  
- Naplnění **připojit k procesu** seznamu (voláním `IDebugProcess2::EnumPrograms` a následným voláním [QueryInterface](https://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) na každém [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) rozhraní získat [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md) rozhraní).  
  
- Vygeneruje seznam DEs, který lze ladit každém programu v procesu (pomocí [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogram2-getengineinfo.md)).  
  
- Použití aktualizací upravit a pokračovat (ENC) pro každý program (voláním IDebugProcess2::EnumPrograms a následným voláním [GetENCUpdate](../../../extensibility/debugger/reference/idebugprogram2-getencupdate.md)).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumPrograms](../../../extensibility/debugger/reference/idebugengine2-enumprograms.md)   
 [EnumPrograms](../../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)
