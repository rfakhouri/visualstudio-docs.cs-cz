---
title: IDebugMemoryContext2::Add | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMemoryContext2::Add
helpviewer_keywords:
- IDebugMemoryContext2::Add method
- Add method
ms.assetid: 3c47e646-ce9e-4dd3-8f1a-6dbd3827d407
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 40ec185caf65197d46abc7def26def7929f70d74
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idebugmemorycontext2add"></a>IDebugMemoryContext2::Add
Přidá zadanou hodnotu do aktuální kontext a vrátí nový kontext.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Add(   
   UINT64                 dwCount,  
   IDebugMemoryContext2** ppMemCxt  
);  
```  
  
```csharp  
int Add(  
   ulong                    dwCount,   
   out IDebugMemoryContext2 ppMemCxt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwCount`  
 [v] Hodnota k přidání do aktuálního kontextu.  
  
 `ppMemCxt`  
 [out] Vrátí novou [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Kontextu paměti je adresu, takže přidání hodnotu na adresu vytvoří novou adresu, která vyžaduje nové rozhraní kontextu.  
  
 Tato metoda musí vždy vytvořit nový kontext, i když Výsledná adresa je mimo paměťový prostor spojený s tímto kontextem. Jedinou výjimkou je, pokud může být přidělen není dostatek paměti pro nový kontext nebo pokud `ppMemCxt` je hodnota null (což je chybu).  
  
## <a name="see-also"></a>Viz také  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)