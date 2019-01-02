---
title: Idiasymbol::get_targetvirtualaddress – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_targetVirtualAddress method
ms.assetid: a0a5ce72-95f8-443e-bb4b-8c21194faad0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9f5aa712aed39ecebdb664cf4f8e0dcefa5efae3
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53867550"
---
# <a name="idiasymbolgettargetvirtualaddress"></a>IDiaSymbol::get_targetVirtualAddress
Načte virtuální adresy (VA) cíle.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_targetVirtualAddress (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí VA cíle.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Tato vlastnost je platná pouze tehdy, pokud symbol jako [symtagenum – výčet](../../debugger/debug-interface-access/symtagenum.md) hodnotu `SymTagThunk`.  
  
 "Převodní rutina" je část kódu, který převede mezi 32-bit paměti adresní prostor (označované také jako plochý adresní prostor) a 16bitových adresní prostor, (označované jako segmentovaným adresní prostor).  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum – výčet](../../debugger/debug-interface-access/symtagenum.md)