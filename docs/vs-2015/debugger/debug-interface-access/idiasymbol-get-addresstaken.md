---
title: Idiasymbol::get_addresstaken – | Dokumentace Microsoftu
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
- IDiaSymbol::get_addressTaken method
ms.assetid: 0d366188-f5e1-4226-b392-58c09539d097
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3c4fa9a1da807e4975a2c733966c3f68fce50b24
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674170"
---
# <a name="idiasymbolgetaddresstaken"></a>IDiaSymbol::get_addressTaken
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiasymbol::get_addresstaken –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiasymbol-get-addresstaken).  
  
Získá příznak, který označuje, zda jiný symbol odkazuje na tento symbol adresu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_addressTaken (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí `TRUE` Pokud další symbol odkazuje na tuto adresu; v opačném případě vrátí `FALSE`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu `B` odkazy `A`. Proto symbol `A`společnosti `get_addressTaken` vrátí metoda `TRUE`.  
  
```cpp#  
int A  = 0;  
int* B = &A;  
```  
  
## <a name="requirements"></a>Požadavky  
  
|Požadavek|Popis|  
|-----------------|-----------------|  
|Záhlaví:|dia2.h|  
|Verze:|V7.0 DIA SDK|  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



