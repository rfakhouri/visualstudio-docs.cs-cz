---
title: Cv_call_e – | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- CV_call_e enumeration
ms.assetid: f230560b-4243-432d-8f19-46df112043b9
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: cd1ee4c024894e5752277a5000d37745c88c4ac6
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63442116"
---
# <a name="cvcalle"></a>CV_call_e
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Určuje konvenci volání funkce.  
  
> [!NOTE]
> Většina běžných hodnot výčtu jsou zdokumentované tady. V souboru hlaviček cvconst.h je k dispozici úplný výčet.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
 Určuje konvence volání funkce, pomocí operace push blízké zprava doleva. Volání funkce vymaže zásobníku.  
  
 CV_CALL_NEAR_FAST  
 Určuje konvence volání funkce, pomocí registrů téměř nabízených zleva doprava. Volaná funkce používá součtem bajtů parametrů k vymazání zásobníku.  
  
 CV_CALL_NEAR_STD  
 Určuje konvence volání funkce, pomocí téměř standardní volání (nabízených zprava doleva).  
  
 CV_CALL_NEAR_SYS  
 Určuje konvence volání funkce použitím téměř volání systému.  
  
 CV_CALL_THISCALL  
 Určuje konvenci volání funkce použitím `this` volání (`this` předán ukazatel v registru).  
  
 CV_CALL_CLRCALL  
 Určuje volání funkce konvence podle CLR Common Language Runtime () (označované také jako spravovaný kód konvence volání).  
  
## <a name="remarks"></a>Poznámky  
 Hodnoty v tomto výčtu jsou vráceny prostřednictvím volání [idiasymbol::get_callingconvention –](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md) metody.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: cvconst.h  
  
## <a name="see-also"></a>Viz také  
 [Výčty a struktury](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get_callingConvention](../../debugger/debug-interface-access/idiasymbol-get-callingconvention.md)
