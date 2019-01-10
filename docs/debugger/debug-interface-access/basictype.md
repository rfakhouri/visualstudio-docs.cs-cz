---
title: Basictype – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- BasicType enumeration
ms.assetid: 19ae53ba-cd6e-47b6-9f94-27ae663ce955
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 891b83d6a43cb73fe8f38bb8b20201cbcfa230f6
ms.sourcegitcommit: 73861cd0ea92e50a3be1ad2a0ff0a7b07b057a1c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2019
ms.locfileid: "54154079"
---
# <a name="basictype"></a>BasicType
Určuje základní typ symbolu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
enum BasicType {   
   btNoType   = 0,  
   btVoid     = 1,  
   btChar     = 2,  
   btWChar    = 3,  
   btInt      = 6,  
   btUInt     = 7,  
   btFloat    = 8,  
   btBCD      = 9,  
   btBool     = 10,  
   btLong     = 13,  
   btULong    = 14,  
   btCurrency = 25,  
   btDate     = 26,  
   btVariant  = 27,  
   btComplex  = 28,  
   btBit      = 29,  
   btBSTR     = 30,  
   btHresult  = 31,  
   btChar16   = 32,  // char16_t
   btChar32   = 33,  // char32_t
};  
```  
  
## <a name="elements"></a>Elementy  
 btNoType  
 Není zadán žádný základní typ.  
  
 btVoid  
 Základní typ je `void`.  
  
 btChar  
 Základní typ je `char` (C/C++ typ).  
  
 btWChar  
 Základní typ je širokého znaku (Unicode) (`WCHAR`).  
  
 btInt  
 Základní typ je `signed int` (C/C++ typ).  
  
 btUInt  
 Základní typ je `unsigned int` (C/C++ typ).  
  
 btFloat  
 Základní typ je číslo s plovoucí desetinnou čárkou (`FLOAT`).  
  
 btBCD  
 Základní typ je binární soubor pevně zakódované desetinné číslo (`BCD`).  
  
 btBool  
 Základní typ je logická hodnota (`BOOL`).  
  
 btLong  
 Základní typ je `long int` (C/C++ typ).  
  
 btULong  
 Základní typ je `unsigned long int` (C/C++ typ).  
  
 btCurrency  
 Základní typ je měna.  
  
 btDate  
 Základní typ je datum a čas (`DATE`).  
  
 btVariant  
 Základní typ je typ proměnné struktury (`VARIANT`).  
  
 btComplex  
 Základní typ je komplexní čísla.  
  
 btBit  
 Základní typ je tento bit.  
  
 btBSTR  
 Základní typ je řetězec základní nebo binární (`BSTR`).  
  
 btHresult  
 Základní typ je `HRESULT`.  
  
## <a name="remarks"></a>Poznámky  
 Jsou vrácené hodnoty v tento výčet [idiasymbol::get_basetype –](../../debugger/debug-interface-access/idiasymbol-get-basetype.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: cvconst.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Idiasymbol::get_basetype –](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)   
 [IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)
