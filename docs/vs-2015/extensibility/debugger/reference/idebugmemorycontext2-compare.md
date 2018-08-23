---
title: IDebugMemoryContext2::Compare | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugMemoryContext2::Compare
helpviewer_keywords:
- IDebugMemoryContext2::Compare method
- Compare method
ms.assetid: c51b5128-848e-4d8e-b2e9-1161339763c3
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4219994deb0490533207907d809e970d0fb303cf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628922"
---
# <a name="idebugmemorycontext2compare"></a>IDebugMemoryContext2::Compare
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugMemoryContext2::Compare](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugmemorycontext2-compare).  
  
Porovná paměti kontext, který má každý kontext v daném poli způsobem indikován porovnání příznaky, které vrací index první kontextu, který se shoduje.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 [in] Hodnota z [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md) výčet, který určuje typ porovnání.  
  
 `rgpMemoryContextSet`  
 [in] Odkazy na pole [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objekty pro porovnání.  
  
 `dwMemoryContextSetLen`  
 [in] Počet kontextů v `rgpMemoryContextSet` pole.  
  
 `pdwMemoryContext`  
 [out] Vrátí index prvního paměti kontextu, který vyhovuje porovnání.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. Vrátí `E_COMPARE_CANNOT_COMPARE` Pokud nelze porovnat dva kontexty.  
  
## <a name="remarks"></a>Poznámky  
 Ladicí stroj (DE) nemá pro podporu všech typů porovnávání, ale musí podporovat alespoň `CONTEXT_EQUAL`, `CONTEXT_LESS_THAN`, `CONTEXT_GREATER_THAN` a `CONTEXT_SAME_SCOPE`.  
  
## <a name="see-also"></a>Viz také  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)   
 [CONTEXT_COMPARE](../../../extensibility/debugger/reference/context-compare.md)

