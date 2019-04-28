---
title: IDiaSymbol::get_isHLSLData | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
ms.assetid: 4662058b-c505-4ccf-ae03-739a62c814ca
caps.latest.revision: 6
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 03b0bf45d4b8100f4ebfd1d6a61dc73547312fe6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62836700"
---
# <a name="idiasymbolgetishlsldata"></a>IDiaSymbol::get_isHLSLData
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Určuje, zda tento symbol představuje data High Level Shader Language (HLSL).  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT get_isHLSLData(   
   BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Ukazatel `BOOL` , která určuje, zda tento symbol představuje HLSL data.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
