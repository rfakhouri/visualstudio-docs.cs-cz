---
title: IDebugMemoryContext2 | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugMemoryContext2
helpviewer_keywords:
- IDebugMemoryContext2 interface
ms.assetid: 3a544c8b-11dc-46bb-8549-261e4ac5bbc4
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 974466977995b866d70ad7e1619a6ae536886f6c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55007606"
---
# <a name="idebugmemorycontext2"></a>IDebugMemoryContext2
Toto rozhraní představuje pozici v adresním prostoru v daném počítači používají laděnému programu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugMemoryContext2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Ladicí stroj (DE) implementuje toto rozhraní představující adresu v paměti.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) nebo [GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md) vrátí toto rozhraní. Navíc volání [přidat](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md) a [odečíst](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md) vrátí nové kopie tohoto rozhraní po použití odpovídající aritmetické operace.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 V následující tabulce jsou uvedeny metody objektu `IDebugMemoryContext2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetName](../../../extensibility/debugger/reference/idebugmemorycontext2-getname.md)|Získá uživatele zobrazitelné název pro tento kontext.|  
|[GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)|Získá informace popisující kontext.|  
|[Add](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md)|Přidá zadanou hodnotu na aktuální kontext adresu a vytvoří nový kontext.|  
|[Subtract](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md)|Odečte zadanou hodnotu z aktuálního kontextu adresu, která vytvoří nový kontext.|  
|[Compare](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)|Porovná dvě kontexty způsobem indikován porovnání příznaky.|  
  
## <a name="remarks"></a>Poznámky  
 Visual Studio **paměti** volání okno [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) získat `IDebugMemoryContext2` rozhraní, které obsahuje vyhodnocený výraz použitý pro adresu paměti. Tento kontext je pak předán [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md) a [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md) zadat adresu pro čtení nebo zápis.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md)   
 [GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md)   
 [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md)   
 [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md)