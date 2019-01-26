---
title: IDebugArrayObject::GetRank | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugArrayObject::GetRank
helpviewer_keywords:
- IDebugArrayObject::GetRank method
ms.assetid: 9948551a-e334-4ff6-979c-08dab633b9b6
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 333dca88fae59d4407e6be813b2241d070648648
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54923039"
---
# <a name="idebugarrayobjectgetrank"></a>IDebugArrayObject::GetRank
Zjistí řád objektu array, to znamená, počet rozměrů.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT GetRank(   
   DWORD* pdwRank  
);  
```  
  
```csharp  
int GetRank(  
   out uint pdwRank  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pdwRank`  
 [out] Vrátí počet rozměrů.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Použití [getdimensions –](../../../extensibility/debugger/reference/idebugarrayobject-getdimensions.md) metody k získání velikosti jednotlivých rozměrů objektu array.  
  
## <a name="see-also"></a>Viz také  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)