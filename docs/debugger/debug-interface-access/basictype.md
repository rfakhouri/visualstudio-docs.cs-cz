---
title: BasicType | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
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
ms.openlocfilehash: cfccb444eab802f7caa5cf83faff0ddc7a51c389
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="basictype"></a>BasicType
Určuje základní typ symbolu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
enum BasicType {   
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
   btHresult  = 31  
};  
```  
  
## <a name="elements"></a>Elementy  
 btNoType  
 Není zadán žádný základní typ.  
  
 btVoid  
 Základní typ `void`.  
  
 btChar  
 Základní typ `char` (C/C++ typ).  
  
 btWChar  
 Základní typ je široká znaková (Unicode) (`WCHAR`).  
  
 btInt  
 Základní typ je `signed int` (C/C++ typ).  
  
 btUInt  
 Základní typ je `unsigned int` (C/C++ typ).  
  
 btFloat  
 Základní typ je číslo s plovoucí desetinnou čárkou (`FLOAT`).  
  
 btBCD  
 Základní typ je zakódovaný binární datový typ decimal (`BCD`).  
  
 btBool  
 Základní typ je logická hodnota (`BOOL`).  
  
 btLong  
 Základní typ `long int` (C/C++ typ).  
  
 btULong  
 Základní typ je `unsigned long int` (C/C++ typ).  
  
 btCurrency  
 Základní typ je currency.  
  
 btDate  
 Základní typ je datum a čas (`DATE`).  
  
 btVariant  
 Základní typ je typ proměnné struktury (`VARIANT`).  
  
 btComplex  
 Základní typ je komplexní číslo.  
  
 btBit  
 Základní typ je chvíli.  
  
 btBSTR  
 Základní typ je základním nebo binární řetězec (`BSTR`).  
  
 btHresult  
 Základní typ je `HRESULT`.  
  
## <a name="remarks"></a>Poznámky  
 Jsou vrácené hodnoty v tento výčet [idiasymbol::get_basetype –](../../debugger/debug-interface-access/idiasymbol-get-basetype.md) metoda.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: cvconst.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Idiasymbol::get_basetype –](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)   
 [IDiaSymbol::get_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)