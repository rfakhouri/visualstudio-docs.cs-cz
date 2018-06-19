---
title: IDebugMemoryContext2::Add | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMemoryContext2::Add
helpviewer_keywords:
- IDebugMemoryContext2::Add method
- Add method
ms.assetid: 3c47e646-ce9e-4dd3-8f1a-6dbd3827d407
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ad55b81c1c4126efd69779e929521cfb94235ccc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31111931"
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