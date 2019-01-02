---
title: Idialinenumber::get_length – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLineNumber::get_length method
ms.assetid: 2c55a6f7-4ef5-45fb-9fd1-d72deaaa2829
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 34e36486f95964169200cee7c41ac8eaebc27960
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53916410"
---
# <a name="idialinenumbergetlength"></a>IDiaLineNumber::get_length
Získá počet bajtů v bloku.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_length (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí počet bajtů v bloku.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Blok je délka zdrojový kód na řádku reprezentovaná [idialinenumber –](../../debugger/debug-interface-access/idialinenumber.md) objektu.  
  
## <a name="see-also"></a>Viz také  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)