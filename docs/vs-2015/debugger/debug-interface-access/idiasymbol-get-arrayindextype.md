---
title: Idiasymbol::get_arrayindextype – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
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
- IDiaSymbol::get_arrayIndexType method
ms.assetid: cd63b9ec-9694-406c-b37f-bde6bd5fcbf2
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 65689f52eb5d408fdc062e38c5c41f8983a3f518
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49929943"
---
# <a name="idiasymbolgetarrayindextype"></a>IDiaSymbol::get_arrayIndexType
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Načte rozhraní symbol indexu pole typu symbol.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_arrayIndexType (   
   IDiaSymbol** pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) objekt, který reprezentuje typ indexu pole symbolu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` nebo kód chyby.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená, že vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 Některé jazyky můžete zadat typ používá jako index pole. Určuje symbol, tato metoda vrátí tohoto typu.  
  
## <a name="requirements"></a>Požadavky  
  
|Požadavek|Popis|  
|-----------------|-----------------|  
|Záhlaví:|dia2.h|  
|Verze:|V7.0 DIA SDK|  
  
## <a name="see-also"></a>Viz také  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)



