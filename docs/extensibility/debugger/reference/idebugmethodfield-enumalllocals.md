---
title: IDebugMethodField::EnumAllLocals | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
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
ms.openlocfilehash: 8c3c13f7252e6f3b662ded697ab267419fd66450
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugmethodfieldenumalllocals"></a>IDebugMethodField::EnumAllLocals
Vytvoří enumerátor pro všechny místní proměnné metody, včetně těch, které generované interně službou kompilátor.  
  
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
 [v] [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) objekt reprezentující ladění adresu v metodě, odkazující na konkrétní oboru nebo kontextu.  
  
 `ppLocals`  
 [out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objekt reprezentující seznam všech místních proměnných v zadaném oboru; jinak vrátí hodnotu null určující žádné místní hodnoty.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK nebo vrátí S_FALSE, pokud nejsou žádné místní hodnoty. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Uvedené jsou pouze proměnné definované v bloku, která obsahuje daný ladění adresu. Tato metoda obsahuje všechny místní hodnoty generované kompilátorem. Pokud jsou všechny, které je potřeba místní hodnoty explicitně definované ve zdroji, volání [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md) metoda.  
  
 Metoda může obsahovat několik bloků nebo kontextu oboru.  
  
## <a name="see-also"></a>Viz také  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [EnumLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumlocals.md)