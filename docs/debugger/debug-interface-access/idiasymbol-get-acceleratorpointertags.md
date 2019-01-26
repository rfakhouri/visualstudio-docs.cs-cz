---
title: IDiaSymbol::get_acceleratorPointerTags | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 30e13cee-e511-49ec-affd-99b0097071b2
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4f94ea23c1a6afd16f57a2ffb9944cf8a7ded5c9
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55019538"
---
# <a name="idiasymbolgetacceleratorpointertags"></a>IDiaSymbol::get_acceleratorPointerTags
Vrátí všechny akcelerátoru hodnoty značky ukazatele, které odpovídají funkci jazyka C++ AMP akcelerátor zástupné procedury.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_acceleratorPointerTags(   
   DWORD          cnt,  
   DWORD*         pcnt,  
   DWORD*         pPointerTags);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cnt`  
 [in] Velikost pole výstup `pPointerTags`.  
  
 `pcnt`  
 [out] Počet značek akcelerátoru ukazatel ve funkci jazyka C++ AMP akcelerátor zástupné procedury.  
  
 `pPointerTags`  
 [out] A `DWORD` pole ukazatel, který je vyplněna hodnoty značek akcelerátoru ukazatel ve funkci jazyka C++ AMP akcelerátor zástupné procedury.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána na `IDiaSymbol` rozhraní, který odpovídá zástupné procedury funkce C++ AMP akcelerátor.  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)