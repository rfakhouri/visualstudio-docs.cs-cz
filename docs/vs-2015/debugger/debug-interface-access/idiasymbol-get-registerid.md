---
title: Idiasymbol::get_registerid – | Dokumentace Microsoftu
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
- IDiaSymbol::get_registerId method
ms.assetid: f881e793-eb9e-48dc-a847-dd61d77174fc
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7c56467426840fe9bd9cbb62c77b6f0889126647
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666794"
---
# <a name="idiasymbolgetregisterid"></a>IDiaSymbol::get_registerId
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiasymbol::get_registerid –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-registerid).  
  
Načte register označení umístění při [locationtype – výčet](../../debugger/debug-interface-access/locationtype.md) je nastavena na `LocIsEnregistered`.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_registerId (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí hodnotu registru označení umístění.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Pokud symbol je relativní vzhledem k registru, to znamená, pokud symbolu [locationtype – výčet](../../debugger/debug-interface-access/locationtype.md) je nastavena na `LocIsRegRel`, použijte `get_registerId` metoda za nímž následuje volání [idiasymbol::get_offset –](../../debugger/debug-interface-access/idiasymbol-get-offset.md) metodu k získání posun z registru, kde se nachází symbolu.  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [Locationtype – výčet](../../debugger/debug-interface-access/locationtype.md)



