---
title: Idiasymbol::get_offset – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSymbol::get_offset method
ms.assetid: 8292bb08-4dc8-4663-beb4-258f5d5a448d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b6022c24c035b59d6b73c12f7c4907bab2eb5300
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54955554"
---
# <a name="idiasymbolgetoffset"></a>IDiaSymbol::get_offset
Načte posun umístění symbolu. Použít, když [locationtype – výčet](../../debugger/debug-interface-access/locationtype.md) je `LocIsRegRel` nebo `LocIsBitField`.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_offset (   
   LONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrací posun v bajtech umístění symbolu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Posun je z některé známé bodu dříve určené. Například posun `LocIsBitField` typ umístění je obvykle od samého začátku třídu obsahující.  
  
## <a name="requirements"></a>Požadavky  
  
|Požadavek|Popis|  
|-----------------|-----------------|  
|Záhlaví:|dia2.h|  
|Verze:|V7.0 DIA SDK|  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType – výčet](../../debugger/debug-interface-access/locationtype.md)