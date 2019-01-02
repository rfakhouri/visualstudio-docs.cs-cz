---
title: IEnumDebugFields::Reset | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IEnumDebugFields::Reset
helpviewer_keywords:
- IEnumDebugFields::Reset method
ms.assetid: 38ff61e4-0120-42e8-971a-16be6050b425
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8f1de86cda120d33db201907dca55c07a1c75782
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53839148"
---
# <a name="ienumdebugfieldsreset"></a>IEnumDebugFields::Reset
Tato metoda resetuje na první prvek výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT Reset(void);  
```  
  
```csharp  
int Reset();  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádná  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Až tato metoda je volána, další volání [Další](../../../extensibility/debugger/reference/ienumdebugfields-next.md) vrátí první prvek výčtu.  
  
## <a name="see-also"></a>Viz také  
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [Next](../../../extensibility/debugger/reference/ienumdebugfields-next.md)