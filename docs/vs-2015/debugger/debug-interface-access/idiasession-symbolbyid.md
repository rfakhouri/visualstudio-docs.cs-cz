---
title: Idiasession::symbolbyid – | Dokumentace Microsoftu
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
- IDiaSession::symbolById method
ms.assetid: 062e4b5a-9c4d-4703-88da-ec13102c2b66
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 60b7495abd70eb7e02408cfe711701ec15f5ac4b
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49272711"
---
# <a name="idiasessionsymbolbyid"></a>IDiaSession::symbolById
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Načte symbol podle jejího jedinečného identifikátoru.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT symbolById (   
   DWORD        id,  
   IDiaSymbol** ppSymbol  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `id`  
 [in] Jedinečný identifikátor.  
  
 `ppSymbol`  
 [out] Vrátí [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) načíst objekt představující symbol.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Zadaný identifikátor je jedinečná hodnota používaná interně pomocí sady DIA SDK jedinečných aby všechny symboly.  
  
 Tuto metodu lze použít například k načtení symbol představující typ jiného symbolu (podívejte se na příklad).  
  
## <a name="example"></a>Příklad  
 Tento příklad načte [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) představující typ jiného symbolu. Tento příklad ukazuje způsob použití `symbolById` metoda v relaci. Je jednodušší přístup k volání [idiasymbol::get_type –](../../debugger/debug-interface-access/idiasymbol-get-type.md) metody k získání typu symbol přímo.  
  
```cpp#  
IDiaSymbol *GetSymbolType(IDiaSymbol *pSymbol, IDiaSession *pSession)  
{  
    IDiaSymbol *pTypeSymbol = NULL;  
    if (pSymbol != NULL && pSession != NULL)  
    {  
        DWORD symbolTypeId;  
        pSymbol->get_typeId(&symbolTypeId);  
        pSession->symbolById(symbolTypeId, &pTypeSymbol);  
    }  
    return(pTypeSymbol);  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSymbol::get_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)



