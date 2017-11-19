---
title: IDebugMemoryContext2::Compare | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMemoryContext2::Compare
helpviewer_keywords:
- IDebugMemoryContext2::Compare method
- Compare method
ms.assetid: c51b5128-848e-4d8e-b2e9-1161339763c3
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: dbcb3f93a4db6a14775cfe518ed257e60282f1fb
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugmemorycontext2compare"></a>IDebugMemoryContext2::Compare
Porovná paměti kontext, který má každý kontext v daném poli způsobem indikován porovnání příznaky, vrácení indexu první kontextu, který se shoduje.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Compare(   
   CONTEXT_COMPARE        compare,  
   IDebugMemoryContext2** rgpMemoryContextSet,  
   DWORD                  dwMemoryContextSetLen,  
   DWORD*                 pdwMemoryContext  
);  
```  
  
```csharp  
int Compare(  
   enum_CONTEXT_COMPARE   compare,   
   IDebugMemoryContext2[] rgpMemoryContextSet,   
   uint                   dwMemoryContextSetLen,   
   out uint               pdwMemoryContext  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `compare`  
 [v] Hodnota z [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md) výčet, který určuje typ porovnání.  
  
 `rgpMemoryContextSet`  
 [v] Odkazy na pole [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objekty pro porovnání.  
  
 `dwMemoryContextSetLen`  
 [v] Počet kontexty v `rgpMemoryContextSet` pole.  
  
 `pdwMemoryContext`  
 [out] Vrátí index první paměti kontext, který splňuje porovnání.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. Vrátí `E_COMPARE_CANNOT_COMPARE` Pokud dvou kontextů nejde porovnat.  
  
## <a name="remarks"></a>Poznámky  
 Modul ladění (DE) nemusí podporovat všechny typy porovnání, ale musí podporovat alespoň `CONTEXT_EQUAL`, `CONTEXT_LESS_THAN`, `CONTEXT_GREATER_THAN` a `CONTEXT_SAME_SCOPE`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)   
 [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md)