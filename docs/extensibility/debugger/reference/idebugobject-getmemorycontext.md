---
title: IDebugObject::GetMemoryContext | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugObject::GetMemoryContext
helpviewer_keywords: IDebugObject::GetMemoryContext method
ms.assetid: 6760a0d3-a898-4e81-b68f-c45c584b225b
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 93f6d82b88be23b160effe1c8162648132f461c5
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugobjectgetmemorycontext"></a>IDebugObject::GetMemoryContext
Získá kontext paměti, který představuje adresu hodnoty objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetMemoryContext(   
   IDebugMemoryContext2** pContext  
);  
```  
  
```csharp  
int GetMemoryContext(  
   ref IDebugMemoryContext2 pContext  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pContext`  
 [out] Vrátí [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objektu, který představuje adresu hodnoty objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Kontext vrácený paměti určuje adresu Hodnota reprezentovaná to [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objektu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)