---
title: IDiaSymbol::get_isReturnValue | Dokumentace Microsoftu
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
ms.assetid: 37aaf48a-65cb-4ec2-823e-1c637a9f939c
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 23c4a0fe580df7fc2d07b023c825428693e73e2d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669959"
---
# <a name="idiasymbolgetisreturnvalue"></a>IDiaSymbol::get_isReturnValue
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDiaSymbol::get_isReturnValue](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-isreturnvalue).  
  
Určuje, zda proměnná nese návratovou hodnotu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT get_isReturnValue(   
   BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Ukazatel `BOOL` , která určuje, zda proměnná nese návratovou hodnotu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



