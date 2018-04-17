---
title: IDebugMethodField::EnumLocals | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugMethodField::EnumLocals
helpviewer_keywords:
- IDebugMethodField::EnumLocals method
ms.assetid: b0456a6d-2b96-49e2-a871-516571b4f6a5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 8379407a275fa4b89b4107037b2a39691d062dd9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idebugmethodfieldenumlocals"></a>IDebugMethodField::EnumLocals
Vytvoří enumerátor pro vybrané lokální proměnné metody.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT EnumLocals(   
   IDebugAddress*     pAddress,  
   IEnumDebugFields** ppLocals  
);  
```  
  
```csharp  
int EnumLocals(  
   IDebugAddress        pAddress,   
   out IEnumDebugFields ppLocals  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pAddress`  
 [v] [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) objektu, který představuje adresu ladění, která vybere položku kontext nebo oboru, ze kterého chcete-li získat lokální.  
  
 `ppLocals`  
 [out] Vrátí [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md) objekt reprezentující seznam lokální; jinak vrátí hodnotu null, pokud nejsou žádné místní hodnoty.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí S_OK nebo vrátí S_FALSE, pokud nejsou žádné místní hodnoty. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Uvedené jsou pouze proměnné definované v bloku, která obsahuje daný ladění adresu. V případě potřeby se všechny místní hodnoty – včetně žádné místní hodnoty generované kompilátorem volání [EnumAllLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumalllocals.md) metoda.  
  
 Metoda může obsahovat několik bloků nebo kontextu oboru. Například následující contrived metodu obsahuje tři obory, dva vnitřní bloky a metoda text sám sebe.  
  
```csharp  
public void func(int index)  
{  
    // Method body scope  
    int a = 0;  
    if (index == 1)  
    {  
        // Inner scope 1  
        int temp1 = a;  
    }  
    else  
    {  
        // Inner scope 2  
        int temp2 = a;  
    }  
}  
```  
  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md) objektu představuje `func` metoda sama. Volání `EnumLocals` metoda s [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) nastavena na `Inner Scope 1` adresy vrátí výčtu obsahující `temp1` proměnných, například.  
  
## <a name="see-also"></a>Viz také  
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)   
 [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)   
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [EnumAllLocals](../../../extensibility/debugger/reference/idebugmethodfield-enumalllocals.md)