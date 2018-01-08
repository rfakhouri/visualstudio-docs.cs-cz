---
title: CV_call_e | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: CV_call_e enumeration
ms.assetid: f230560b-4243-432d-8f19-46df112043b9
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 54447dac0f070ae97cf5b4c6b421c8d6a0e2d44a
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="cvcalle"></a>CV_call_e
Určuje konvence volání pro funkci.  
  
> [!NOTE]
>  Nejběžnější hodnoty výčtu jsou popsané v tomto poli. Úplný výčet je k dispozici v záhlaví souboru cvconst.h.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
typedef enum CV_call_e {   
   CV_CALL_NEAR_C    = 0x00,  
   CV_CALL_NEAR_FAST = 0x04,  
   CV_CALL_NEAR_STD  = 0x07,  
   CV_CALL_NEAR_SYS  = 0x09,  
   CV_CALL_THISCALL  = 0x0b,  
   CV_CALL_CLRCALL   = 0x16  
} CV_call_e;  
```  
  
## <a name="elements"></a>Elementy  
 CV_CALL_NEAR_C  
 Určuje použití near nabízené zprava doleva konvence volání funkce. Volání funkce vymaže zásobníku.  
  
 CV_CALL_NEAR_FAST  
 Určuje konvence volání funkce pomocí registry near push zleva doprava. Volaná funkce používá součtem bajtů parametr zrušte zásobníku.  
  
 CV_CALL_NEAR_STD  
 Určuje konvence volání funkce pomocí near standardní volání (nabídka zprava doleva).  
  
 CV_CALL_NEAR_SYS  
 Určuje konvence volání funkce pomocí near systémového volání.  
  
 CV_CALL_THISCALL  
 Konvence volání funkce pomocí Určuje `this` volání (`this` ukazatel předaná registrace).  
  
 CV_CALL_CLRCALL  
 Určuje konvence volání funkce používá podle CLR Common Language Runtime () (také označované jako spravovaný kód konvence volání).  
  
## <a name="remarks"></a>Poznámky  
 Hodnoty v tento výčet jsou vráceny prostřednictvím volání [idiasymbol::get_callingconvention –](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md) metoda.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: cvconst.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_callingConvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)