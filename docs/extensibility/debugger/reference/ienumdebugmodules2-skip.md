---
title: IEnumDebugModules2::Skip | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumDebugModules2::Skip
helpviewer_keywords:
- IEnumDebugModules2::Skip
ms.assetid: 61dc42f4-8544-45bb-8da0-fb22cccec7da
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c0c3b73ad7caf66ea43f14d83b4fe5647b49baf3
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53917040"
---
# <a name="ienumdebugmodules2skip"></a>IEnumDebugModules2::Skip
Přeskočí za zadaný počet prvků.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Skip(  
   ULONG celt  
);  
```  
  
```csharp  
int Skip(  
   uint celt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `celt`  
 [in] Počet prvků, které mají přeskočit.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` Pokud `celt` je větší než počet zbývajících prvků; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Pokud `celt` Určuje hodnotu větší než počet zbývajících prvků výčtu je nastavena na konci a `S_FALSE` je vrácena.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)