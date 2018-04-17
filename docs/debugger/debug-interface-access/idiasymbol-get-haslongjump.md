---
title: Idiasymbol::get_haslongjump – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_hasLongJump method
ms.assetid: 14484cb1-43b0-47a1-a9a8-081b55566886
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 252533e126075a3acee3ff4e4a6d47f7df68e079
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolgethaslongjump"></a>IDiaSymbol::get_hasLongJump
Načte příznak, který určuje, zda obsahuje funkce použití [longjmp](/cpp/c-runtime-library/reference/longjmp) příkazu (spárované s [setjmp](/cpp/c-runtime-library/reference/setjmp) příkaz, tyto formuláři metodu stylu jazyka C zpracování výjimek).  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_hasLongJump  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pFlag`  
 [out] Vrátí `TRUE` pokud obsahuje funkce `longjmp` příkaz; jinak vrátí `FALSE`.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="requirements"></a>Požadavky  
  
|Požadavek|Popis|  
|-----------------|-----------------|  
|Hlavičky:|dia2.h|  
|Verze:|V8.0 DIA SDK|  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [Idiasymbol::get_hassetjump –](../../debugger/debug-interface-access/idiasymbol-get-hassetjump.md)   
 [longjmp](/cpp/c-runtime-library/reference/longjmp)   
 [setjmp](/cpp/c-runtime-library/reference/setjmp)