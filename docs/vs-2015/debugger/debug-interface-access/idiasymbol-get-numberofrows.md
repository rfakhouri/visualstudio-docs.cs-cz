---
title: IDiaSymbol::get_numberOfRows | Dokumentace Microsoftu
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
ms.assetid: cf3eb110-d07f-4995-b68b-08290aa67d6f
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bd0e41adcafa17b4040113c6c3382e3392ea905c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676925"
---
# <a name="idiasymbolgetnumberofrows"></a>IDiaSymbol::get_numberOfRows
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDiaSymbol::get_numberOfRows](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-numberofrows).  
  
Získá počet řádků v matici.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT get_numberOfRows(   
   DWORD* pRetVal);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Ukazatel `DWORD` , který obsahuje počet řádků v matici.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



