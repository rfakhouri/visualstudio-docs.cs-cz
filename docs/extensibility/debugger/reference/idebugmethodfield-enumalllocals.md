---
title: IDebugMethodField::EnumAllLocals | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugMethodField::EnumAllLocals
helpviewer_keywords: IDebugMethodField::EnumAllLocals method
ms.assetid: 0bc7cc13-2628-4bd8-8c06-4d2aa6755ea8
caps.latest.revision: "9"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4910f5b0daa5b474be4061d73c8600c388884451
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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