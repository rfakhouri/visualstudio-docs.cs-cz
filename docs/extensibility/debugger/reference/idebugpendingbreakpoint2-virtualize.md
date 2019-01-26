---
title: IDebugPendingBreakpoint2::Virtualize | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPendingBreakpoint2::Virtualize
helpviewer_keywords:
- Virtualize method
- IDebugPendingBreakpoint2::Virtualize method
ms.assetid: 58c8e9a5-4494-47c2-bddb-56f628da6a2d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: d06c712e72af0cdab61370df8537f7c9aaeff75b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55028476"
---
# <a name="idebugpendingbreakpoint2virtualize"></a>IDebugPendingBreakpoint2::Virtualize
Přepíná virtualizované stavu tohoto objektu čekajících zarážek. Když je virtualizované čekající zarážkou, ladicí stroj se pokusí vytvořit vazbu pokaždé, když se nový kód načte do programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Virtualize(   
   BOOL fVirtualize  
);  
```  
  
```cpp  
int Virtualize(   
   int fVirtualize  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `fVirtualize`  
 [in] Nastavit na nenulovou hodnotu (`TRUE`) pro virtualizaci čekající zarážka nebo na hodnotu nula (`FALSE`) Chcete-li vypnout virtualizace.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `E_BP_DELETED` Pokud zarážka byla odstraněna.  
  
## <a name="remarks"></a>Poznámky  
 Virtualizované zarážku je vázán pokaždé, když je načten kódu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak implementovat tuto metodu pro jednoduchý `CPendingBreakpoint` objekt, který zveřejňuje [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) rozhraní.  
  
```cpp  
HRESULT CPendingBreakpoint::Virtualize(BOOL fVirtualize)    
{    
   HRESULT hr;    
  
   // Verify that the pending breakpoint has not been deleted. If deleted,   
   // then return hr = E_BP_DELETED.    
   if (m_state.state != PBPS_DELETED)    
   {    
      if (fVirtualize)    
      {    
         // Set the PBPSF_VIRTUALIZED flag in the PENDING_BP_STATE_FLAGS   
         // structure.    
         SetFlag(m_state.flags, PBPSF_VIRTUALIZED);    
      }    
      else    
      {    
         // Clear the PBPSF_VIRTUALIZED flag in the PENDING_BP_STATE_FLAGS   
         // structure.    
         ClearFlag(m_state.flags, PBPSF_VIRTUALIZED);    
      }    
      hr = S_OK;    
   }    
   else    
   {    
      hr = E_BP_DELETED;    
   }    
  
   return hr;    
}    
```  
  
## <a name="see-also"></a>Viz také  
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)