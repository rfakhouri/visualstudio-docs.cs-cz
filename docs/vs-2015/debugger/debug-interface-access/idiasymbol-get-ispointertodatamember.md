---
title: IDiaSymbol::get_isPointerToDataMember | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
ms.assetid: ef17c737-242e-43e8-b7e1-2c3bc58cfcef
caps.latest.revision: 6
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: ca44d11dfcec717e37a9bc13a2d87f9f5a94ede3
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/12/2019
ms.locfileid: "68155883"
---
# <a name="idiasymbolgetispointertodatamember"></a>IDiaSymbol::get_isPointerToDataMember
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Určuje, zda tento symbol je ukazatel na datový člen.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
HRESULT get_isPointerToDataMember(   
   BOOL* pRetVal);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Ukazatel `BOOL` , která určuje, zda tento symbol je ukazatel na datový člen.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
