---
title: Idiasymbol::get_age – | Dokumentace Microsoftu
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
- IDiaSymbol::get_age method
ms.assetid: 60d05654-e832-4a2e-a4a7-fe9922c459fe
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8c9a19af7ffce28cabb3d3f9ab7ae659c465f4c7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673613"
---
# <a name="idiasymbolgetage"></a>IDiaSymbol::get_age
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiasymbol::get_age –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-age).  
  
Načte hodnotu stáří souboru pdb.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_age (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí hodnotu stáří souboru pdb.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Stáří neodpovídá nutně na libovolnou hodnotu známý času; To se obvykle používá k určení, zda soubor PDB není synchronizován s odpovídající soubor .exe.  
  
## <a name="requirements"></a>Požadavky  
  
|Požadavek|Popis|  
|-----------------|-----------------|  
|Záhlaví:|dia2.h|  
|Verze:|V7.0 DIA SDK|  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



