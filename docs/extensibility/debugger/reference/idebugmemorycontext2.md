---
title: IDebugMemoryContext2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMemoryContext2
helpviewer_keywords: IDebugMemoryContext2 interface
ms.assetid: 3a544c8b-11dc-46bb-8549-261e4ac5bbc4
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d3219c5618fbb59438ec6d7ad0aa54e2fbbb1213
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmemorycontext2"></a>IDebugMemoryContext2
Toto rozhraní představuje pozici v adresním prostoru počítače spuštěného programu laděné.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugMemoryContext2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Modul ladění (DE) implementuje toto rozhraní představující adresu v paměti.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 Volání [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) nebo [GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md) vrátí toto rozhraní. Navíc volání [přidat](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md) a [Subtract](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md) vrátit nové kopie tohoto rozhraní po použití odpovídající aritmetické operace.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugMemoryContext2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[GetName –](../../../extensibility/debugger/reference/idebugmemorycontext2-getname.md)|Získá uživatele zobrazitelné název pro tento kontext.|  
|[GetInfo](../../../extensibility/debugger/reference/idebugmemorycontext2-getinfo.md)|Získá informace, které popisují tohoto kontextu.|  
|[Přidat](../../../extensibility/debugger/reference/idebugmemorycontext2-add.md)|Přičte zadanou hodnotu na aktuální kontext adresu vytvořit nový kontext.|  
|[Odečtena](../../../extensibility/debugger/reference/idebugmemorycontext2-subtract.md)|Odečte zadanou hodnotu z aktuálního kontextu adresy vytvořit nový kontext.|  
|[Porovnání](../../../extensibility/debugger/reference/idebugmemorycontext2-compare.md)|Porovná dva kontexty způsobem indikován porovnat příznaky.|  
  
## <a name="remarks"></a>Poznámky  
 Visual Studio **paměti** okno volání [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) získat `IDebugMemoryContext2` rozhraní, které obsahuje vyhodnocený výraz použitý pro adresu paměti. Tento kontext se pak předá do [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md) a [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md) zadáním adresy pro čtení nebo zápis.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md)   
 [GetMemoryContext](../../../extensibility/debugger/reference/idebugreference2-getmemorycontext.md)   
 [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md)   
 [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md)