---
title: Idiasymbol::get_hasseh – | Dokumentace Microsoftu
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
helpviewer_keywords:
- IDiaSymbol::get_hasSEH method
ms.assetid: 1a709ded-22c8-464c-97be-eba5e464210c
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f8dd3eda1eaf992de0b38e26bde93ae3f4c1de05
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672437"
---
# <a name="idiasymbolgethasseh"></a>IDiaSymbol::get_hasSEH
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiasymbol::get_hasseh –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-hasseh).  
  
Získá příznak, který určuje, zda funkce obsahuje některý [strukturovaného zpracování výjimek (C/C++)](http://msdn.microsoft.com/library/dd3b647d-c269-43a8-aab9-ad1458712976) (například __try /\__except bloků).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_hasSEH(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pFlag`  
 [out] Vrátí `TRUE` Pokud funkce má všechny bloky; zpracování strukturovaných výjimek v opačném případě vrátí `FALSE`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="requirements"></a>Požadavky  
  
|Požadavek|Popis|  
|-----------------|-----------------|  
|Záhlaví:|dia2.h|  
|Verze:|Ve verzi 8.0 DIA SDK|  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [Strukturované zpracování výjimek (C/C++)](http://msdn.microsoft.com/library/dd3b647d-c269-43a8-aab9-ad1458712976)



