---
title: IDiaSymbol::get_acceleratorPointerTags | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
ms.assetid: 30e13cee-e511-49ec-affd-99b0097071b2
caps.latest.revision: 6
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 829c7a0193ce2742959f677e95dd4a499997cf5b
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54763873"
---
# <a name="idiasymbolgetacceleratorpointertags"></a>IDiaSymbol::get_acceleratorPointerTags
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vrátí všechny akcelerátoru hodnoty značky ukazatele, které odpovídají funkci jazyka C++ AMP akcelerátor zástupné procedury.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
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
