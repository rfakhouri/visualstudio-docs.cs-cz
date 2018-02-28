---
title: "Idiasymbol::get_length – | Microsoft Docs"
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
- IDiaSymbol::get_length method
ms.assetid: cc62f028-d195-4fbf-93bc-10b08bef52d2
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c2a1d879b2460b4b09ea47bcb892f760a912e7b5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiasymbolgetlength"></a>IDiaSymbol::get_length
Načte počet bitů nebo bajtů paměti, které objekt reprezentovaný rozhraním tento symbol.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_length (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí počet bajtů nebo bity paměti, které objekt reprezentovaný rozhraním tento symbol.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Pokud [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md) symbolu je `LocIsBitField`, vrátí tato metoda je v bitech,, jinak je délka v bajtech pro všechny ostatní typy umístění.  
  
## <a name="example"></a>Příklad  
  
```C++  
IDiaSymbol* pSymbol;  
ULONGLONG   length;  
pSymbol->get_length( &length );  
```  
  
## <a name="requirements"></a>Požadavky  
  
|Požadavek|Popis|  
|-----------------|-----------------|  
|Hlavičky:|dia2.h|  
|Verze:|V7.0 DIA SDK|  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md)