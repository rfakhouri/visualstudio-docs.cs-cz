---
title: IEnumDebugFields::GetCount | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumDebugFields::GetCount
helpviewer_keywords:
- IEnumDebugFields::GetCount method
ms.assetid: 3f471b40-4db3-49f7-b504-58b2476eef74
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8cabcbd6d56540c7c8014b439fd5c395e615131e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53877186"
---
# <a name="ienumdebugfieldsgetcount"></a>IEnumDebugFields::GetCount
Tato metoda vrátí počet prvků ve výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetCount(  
   [out] ULONG* pcelt  
);  
```  
  
```csharp  
int GetCount(  
   out uint pcelt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pcelt`  
 [out] Vrátí počet prvků ve výčtu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda není součástí obvyklé výčet rozhraní modelu COM, která určuje, že je potřeba je implementovat pouze další, klonování, přeskočit a obnovení.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)