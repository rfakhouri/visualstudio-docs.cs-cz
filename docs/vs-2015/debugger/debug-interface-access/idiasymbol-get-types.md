---
title: Idiasymbol::get_types – | Dokumentace Microsoftu
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
- IDiaSymbol::get_types method
ms.assetid: 5f056e0c-e15b-4e00-8f78-aadc8574f7ea
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 78be235d82e0bf9113bcfdcef0bf85575e5f5d35
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42672619"
---
# <a name="idiasymbolgettypes"></a>IDiaSymbol::get_types
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiasymbol::get_types –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-types).  
  
Načte pole typů kompilátoru specifické pro tento symbol.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_types (   
   DWORD       cTypes,  
   DWORD*      pcTypes,  
   IDiaSymbol* types[]  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cTypes`  
 [in] Velikost vyrovnávací paměti pro data.  
  
 `pcTypes`  
 [out] Vrátí počet typů napsaných, nebo pokud `types` parametr je `NULL`, pak celkový počet typů, které jsou k dispozici.  
  
 `types[]`  
 [out] Pole, které je v tankujeme [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekty, které představují všechny typy pro tento symbol.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



