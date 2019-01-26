---
title: IDebugPointerObject::Dereference | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugPointerObject::Dereference
helpviewer_keywords:
- IDebugPointerObject::Dereference method
ms.assetid: 196ec2cc-8569-4780-b217-23b24e7f50ca
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e74273d25e121ec769207d429a622eed19654a92
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54922883"
---
# <a name="idebugpointerobjectdereference"></a>IDebugPointerObject::Dereference
Získá odkazovaný objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT DeReference(   
   DWORD          dwIndex,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int Dereference(  
   uint             dwIndex,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwIndex`  
 [in] Ukazuje jednoduchý bajtovým posunem od začátku objektu.  
  
 `ppObject`  
 [out] Vrátí [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekt reprezentující objekt odkazovala na plus odsazení, pokud existuje.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK; v opačném případě vrátí kód chyby. Pokud tento objekt neodkazuje na jiný objekt, vrátí E_FAIL.  
  
## <a name="remarks"></a>Poznámky  
 Odkazovaný objekt může být jednoduchého typu nebo typu složitější například třídy nebo struktury.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)