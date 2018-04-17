---
title: Idiasymbol::get_rank – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_rank method
ms.assetid: 14cc9c4b-a5ec-414a-b01f-4a142c17b7cc
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 106c2d86f5b169aec135c756542d7ac2c8fb566c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolgetrank"></a>IDiaSymbol::get_rank
Načte pořadí FORTRAN vícerozměrné (počet dimenzí).  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_rank (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí počet dimenzí v FORTRAN vícerozměrné.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Pořadí odkazuje na počet dimenzí v matici kde pole je deklarován jako `myarray[1,2,3]`. V tomto příkladu má pořadí 3 až 3 dimenzí. Pořadí se nevztahuje na C++ používaný koncept pole polí pro každou dimenzi (tedy `myarray[1][2][3]`).  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)