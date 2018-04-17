---
title: Idiasymbol::get_typeids – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_typeIds method
ms.assetid: 5166e647-fde5-4efe-92bf-77f8ae3fbc9b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 21c0aad37f51ca388c73ada62512887ff67e3e9a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasymbolgettypeids"></a>IDiaSymbol::get_typeIds
Načte pole hodnot typu kompilátoru konkrétní identifikátor pro tento symbol.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_typeIds (   
   DWORD  cTypeIds,  
   DWORD* pcTypeIds,  
   DWORD  typeIds[]  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cTypeIds`  
 [v] Velikost vyrovnávací paměti pro všechna data.  
  
 `pcTypeIds`  
 [out] Vrátí počet `typeIds` zapsána, nebo pokud `typeIds` je `NULL`, pak celkový počet typ identifikátory, které jsou k dispozici.  
  
 `typeIds[]`  
 [out] Pole, které je pro vyplnění identifikátory typu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená vlastnost není k dispozici pro symbol.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)