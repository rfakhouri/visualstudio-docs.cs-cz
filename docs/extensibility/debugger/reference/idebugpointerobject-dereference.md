---
title: IDebugPointerObject::Dereference | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugPointerObject::Dereference
helpviewer_keywords:
- IDebugPointerObject::Dereference method
ms.assetid: 196ec2cc-8569-4780-b217-23b24e7f50ca
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4cc287887baf2530786b03b591d6c03592055e55
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugpointerobjectdereference"></a>IDebugPointerObject::Dereference
Získá objekt ukazuje.  
  
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
 [v] Ukazuje jednoduchý bajtů posun od začátku objektu.  
  
 `ppObject`  
 [out] Vrátí [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) objekt reprezentující objekt ukazuje plus posun, pokud existuje.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK; jinak vrátí kód chyby. Vrátí E_FAIL, pokud tento objekt neodkazuje na jiný objekt.  
  
## <a name="remarks"></a>Poznámky  
 Objekt, který ukazuje může být jednoduchého typu nebo typu složitější například třídu nebo strukturu.  
  
## <a name="see-also"></a>Viz také  
 [IDebugPointerObject](../../../extensibility/debugger/reference/idebugpointerobject.md)