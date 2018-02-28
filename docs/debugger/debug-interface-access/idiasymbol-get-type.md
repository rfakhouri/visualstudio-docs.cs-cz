---
title: "Idiasymbol::get_type – | Microsoft Docs"
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
- IDiaSymbol::get_type method
ms.assetid: 1c6a4176-dd4e-4c22-8b8f-0e559fc078ba
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 8c5d890674f8430bcb48771bfc13dc44be6025be
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgettype"></a>IDiaSymbol::get_type
Načte symbol, který představuje typ pro tento symbol.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_type (   
   IDiaSymbol** pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt, který představuje typ tento symbol.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 K určení typu symbol má, musí volat tuto metodu a zkontrolujte výsledné [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objektu. Všimněte si, že je možné pro symbol k nejsou typu. Například název strukturou nemá žádný typ, ale může mít podřízené objekty symboly (použít [idiasymbol::findchildren –](../../debugger/debug-interface-access/idiasymbol-findchildren.md) metoda pro zjištění těchto podřízených objektů).  
  
## <a name="example"></a>Příklad  
  
```C++  
IDiaSymbol*         pType;  
CComPtr<IDiaSymbol> pBaseType;  
if (SUCCEEDED(pType->get_type( &pBaseType ))) {  
    BasicType btBaseType;  
    if (SUCCEEDED(pBaseType->get_baseType((DWORD *)&btBaseType))) {  
        // Do something with basic type.  
    }  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [Idiasymbol::get_basetype –](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)   
 [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)