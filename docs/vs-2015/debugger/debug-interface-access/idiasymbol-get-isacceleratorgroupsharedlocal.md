---
title: IDiaSymbol::get_isAcceleratorGroupSharedLocal | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 17a20542-5b45-478f-bb80-0d56031aadb5
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d8c40b0c28ce99d009a46aa02893dde2f5956c2d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42670439"
---
# <a name="idiasymbolgetisacceleratorgroupsharedlocal"></a>IDiaSymbol::get_isAcceleratorGroupSharedLocal
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDiaSymbol::get_isAcceleratorGroupSharedLocal](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-isacceleratorgroupsharedlocal).  
  
Získá příznak označující, zda symbol odpovídá skupině sdílené místní proměnné v kódu zkompilovaném pro akcelerátor AMP C++.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT get_isAcceleratorGroupSharedLocal(   
   BOOL* pFlag);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pFlag`  
 [out] Ukazatel `BOOL` , která označuje, zda symbol odpovídá skupině sdílené místní proměnné v kódu zkompilovaném pro akcelerátor AMP C++. Pokud `TRUE`, `get_baseDataSlot` a `get_baseDataOffset` metody slouží k získání informací o umístění úložiště pro proměnné.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSymbol::get_baseDataSlot](../../debugger/debug-interface-access/idiasymbol-get-basedataslot.md)   
 [IDiaSymbol::get_baseDataOffset](../../debugger/debug-interface-access/idiasymbol-get-basedataoffset.md)



