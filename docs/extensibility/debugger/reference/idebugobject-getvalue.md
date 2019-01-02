---
title: IDebugObject::GetValue | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugObject::GetValue
helpviewer_keywords:
- IDebugObject::GetValue method
ms.assetid: eec6051e-8ecb-49fa-bdd4-dd786f211692
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 98dd9208fe28fd433a201e4d59f8dcc0af694b08
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53914154"
---
# <a name="idebugobjectgetvalue"></a>IDebugObject::GetValue
Získá hodnotu objektu ve formě po sobě jdoucích řady bajtů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetValue(   
   BYTE* pValue,  
   UINT  nSize  
);  
```  
  
```csharp  
int GetValue(  
   ref byte[] pValue,   
   uint nSize  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pValue`  
 [out v] Pole, které se vyplní sérii po sobě jdoucích bajtů představující hodnotu objektu.  
  
 `nSize`  
 [in] Maximální počet bajtů k načtení.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Získat celkový počet bajtů hodnoty, které můžete načíst pomocí volání [getsize –](../../../extensibility/debugger/reference/idebugobject-getsize.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)