---
title: IDebugMemoryBytes2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMemoryBytes2
helpviewer_keywords: IDebugMemoryBytes2 interface
ms.assetid: d7647575-0e06-4190-88f5-ca40b82209a4
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 9a6377ff5ba61427269df683b34a20292c441632
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmemorybytes2"></a>IDebugMemoryBytes2
Toto rozhraní představuje bajtů paměti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugMemoryBytes2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Modul ladění (DE) implementuje toto rozhraní představují bajtů v paměti.  
  
## <a name="notes-for-callers"></a>Poznámky pro volající  
 [GetMemoryBytes](../../../extensibility/debugger/reference/idebugprogram2-getmemorybytes.md) vrátí toto rozhraní pro poskytování přístupu k paměti systému. [GetMemoryBytes](../../../extensibility/debugger/reference/idebugproperty2-getmemorybytes.md) a [GetMemoryBytes](../../../extensibility/debugger/reference/idebugreference2-getmemorybytes.md) vrátit toto rozhraní pro poskytování přístupu k objektu bajtů.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
 Následující tabulka uvádí metody `IDebugMemoryBytes2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md)|Načte sekvenci bajtů, počínaje daného umístění.|  
|[WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md)|Zapíše `dwCount` bajtů, počínaje `pStartContext`.|  
|[Getsize –](../../../extensibility/debugger/reference/idebugmemorybytes2-getsize.md)|Získá velikost v bajtech, paměti, která je reprezentována toto rozhraní.|  
  
## <a name="remarks"></a>Poznámky  
 Pro vlastnosti [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) poskytuje rozhraní představující pole `IDebugMemoryBytes2` rozhraní pro přístup k hodnotám v tomto poli.  
  
 Visual Studio **zobrazení paměti** volání [GetMemoryBytes](../../../extensibility/debugger/reference/idebugprogram2-getmemorybytes.md) načíst `IDebugMemoryBytes2` rozhraní pro přístup k systémové paměti. Adresa přístup k získá analýzou výraz zadaný jako adresu do zobrazení paměti a vyhodnotíte Analyzovaná výraz pomocí [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) získat `IDebugProperty2` rozhraní. Volání [GetMemoryContext](../../../extensibility/debugger/reference/idebugproperty2-getmemorycontext.md) vrátí [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) adresa paměti, který popisuje. Tento kontext paměti je předána do [ReadAt](../../../extensibility/debugger/reference/idebugmemorybytes2-readat.md) a [WriteAt](../../../extensibility/debugger/reference/idebugmemorybytes2-writeat.md).  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [Základní rozhraní](../../../extensibility/debugger/reference/core-interfaces.md)   
 [GetMemoryBytes](../../../extensibility/debugger/reference/idebugprogram2-getmemorybytes.md)   
 [GetMemoryBytes](../../../extensibility/debugger/reference/idebugproperty2-getmemorybytes.md)   
 [GetMemoryBytes](../../../extensibility/debugger/reference/idebugreference2-getmemorybytes.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)