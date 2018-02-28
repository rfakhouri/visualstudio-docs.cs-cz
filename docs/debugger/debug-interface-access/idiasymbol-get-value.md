---
title: "Idiasymbol::get_value – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_value method
ms.assetid: 2e40174a-2a61-4e5f-bb32-9e0ceec2178a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 10bc33c300b9bcdea9b1c6e5784648d7ef19676e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetvalue"></a>IDiaSymbol::get_value
Načte hodnotu konstanty.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_value (   
   VARIANT* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [ve out] A `VARIANT` objekt, který obsahuje hodnotu konstanty.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Zadaný typ VARIANT se musí inicializovat před předaná této metodě. Další informace podívejte se na příklad.  
  
## <a name="example"></a>Příklad  
  
```C++  
void ProcessValue(IDiaSymbol *pSymbol)  
{  
    VARIANT value;  
    value.vt = VT_EMPTY;    // Initialize variant for use.  
    if (pSymbol->get_value(&value) == S_OK)  
    {  
        // Do something with value.  
    }  
}  
  
//----------------------------------------------------  
// Alternate approach  
void ProcessValue2(IDiaSymbol *pSymbol)  
{  
    CComVariant value;  
    if (pSymbol->get_value(&value) == S_OK)  
    {  
        // Do something with value  
    }  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)