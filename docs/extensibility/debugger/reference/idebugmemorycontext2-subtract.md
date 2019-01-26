---
title: IDebugMemoryContext2::Subtract | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugMemoryContext2::Subtract
helpviewer_keywords:
- Subtract method
- IDebugMemoryContext2::Subtract method
ms.assetid: 63df14c7-8d7e-47c1-afa7-5a1ab5d8eaba
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 53f919cb0c70d93c9888eb979846bc9b228c2e18
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55035351"
---
# <a name="idebugmemorycontext2subtract"></a>IDebugMemoryContext2::Subtract
Odečte zadanou hodnotu z aktuálního kontextu a vrátí nový kontext.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Subtract(   
   UINT64                 dwCount,  
   IDebugMemoryContext2** ppMemCxt  
);  
```  
  
```csharp  
int Subtract(  
   ulong                    dwCount,   
   out IDebugMemoryContext2 ppMemCxt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwCount`  
 [in] Počet bajtů paměti se sníží.  
  
 `ppMemCxt`  
 [out] Vrátí nový [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Kontext paměti je adresa, tak odečte hodnotu z adresy vytvoří novou adresu, která vyžaduje nové rozhraní kontextu.  
  
 Tato metoda musí vždy vytvořila nový kontext, i když Výsledná adresa je mimo paměť spojený s tímto kontextem. Jedinou výjimkou je, pokud je možné přidělit paměti pro nový kontext nebo pokud `ppMemCxt` je hodnota null (což je chybu).  
  
## <a name="see-also"></a>Viz také  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)