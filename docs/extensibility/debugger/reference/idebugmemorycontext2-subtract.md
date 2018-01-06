---
title: IDebugMemoryContext2::Subtract | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMemoryContext2::Subtract
helpviewer_keywords:
- Subtract method
- IDebugMemoryContext2::Subtract method
ms.assetid: 63df14c7-8d7e-47c1-afa7-5a1ab5d8eaba
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: ef3f851b48de363e5d63afad4d993d1e693af6fe
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugmemorycontext2subtract"></a>IDebugMemoryContext2::Subtract
Odečte zadanou hodnotu z aktuálního kontextu a vrací nový kontext.  
  
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
 [v] Počet bajtů paměti se sníží.  
  
 `ppMemCxt`  
 [out] Vrátí novou [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Kontext paměti je adresu, takže odečtením hodnotu z adresy vytvoří novou adresu, která vyžaduje nové rozhraní kontextu.  
  
 Tato metoda musí vždy vytvořit nový kontext, i když Výsledná adresa je mimo paměťový prostor spojený s tímto kontextem. Jedinou výjimkou je, pokud může být přidělen není dostatek paměti pro nový kontext nebo pokud `ppMemCxt` je hodnota null (což je chybu).  
  
## <a name="see-also"></a>Viz také  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)