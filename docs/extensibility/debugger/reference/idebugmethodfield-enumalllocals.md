---
title: IDebugMethodField::EnumAllLocals | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugMethodField::EnumAllLocals
helpviewer_keywords:
- IDebugMethodField::EnumAllLocals method
ms.assetid: 0bc7cc13-2628-4bd8-8c06-4d2aa6755ea8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5f03a285a390e244babe99b2cc0ae2db5bf9e67f
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53846279"
---
# <a name="idebugmethodfieldenumalllocals"></a>IDebugMethodField::EnumAllLocals
Vytvoří čítač pro všechny místní proměnné metody, včetně těch kompilátorem generované interně.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumAllLocals(   
   IDebugAddress*     pAddress,  
   IEnumDebugFields** ppLocals  
);  
```  
  
```csharp  
int EnumAllLocals(  
   IDebugAddress        pAddress,   
   out IEnumDebugFields ppLocals  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pAddress`  
 [in] [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) objekt představující adresu ladění v rámci metody, přejdete na konkrétním oboru nebo kontextu.  
  
 `ppLocals`  
 [out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objekt představující seznam všech místních hodnot v zadaném oboru; v opačném případě vrátí hodnotu null označující žádné místní hodnoty.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí hodnotu S_OK nebo vrátí S_FALSE v případě, že neexistují žádné místní hodnoty. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Jsou uvedené pouze proměnné definované v rámci bloku, který obsahuje adresu daného ladění. Tato metoda zahrnuje všechny místní hodnoty generovaný kompilátorem. Pokud jsou všechny, které je potřeba lokální explicitně definovaný ve zdroji, volání [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md) metody.  
  
 Metoda může obsahovat více bloků nebo kontextu oboru.  
  
## <a name="see-also"></a>Viz také  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)