---
title: "Idiasession::symbolbyid – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSession::symbolById method
ms.assetid: 062e4b5a-9c4d-4703-88da-ec13102c2b66
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 70139b7bf3286e7c4527bd71cf78b4ba86aeac1e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiasessionsymbolbyid"></a>IDiaSession::symbolById
Získá symbol svůj jedinečný identifikátor.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT symbolById (   
   DWORD        id,  
   IDiaSymbol** ppSymbol  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `id`  
 [v] Jedinečný identifikátor.  
  
 `ppSymbol`  
 [out] Vrátí [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) načíst objekt, který reprezentuje symbolu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Zadaný identifikátor je jedinečný hodnota interně používané DIA SDK, aby všechny symboly jedinečný.  
  
 Tuto metodu lze použít například k načtení symbol představující typ symbolu jiné (podívejte se na příklad).  
  
## <a name="example"></a>Příklad  
 Tento příklad načte [idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md) představující typ symbolu jiné. Tento příklad ukazuje způsob použití `symbolById` metoda v relaci. Jednodušší je volání [idiasymbol::get_type –](../../debugger/debug-interface-access/idiasymbol-get-type.md) metoda pro načtení symbol typu přímo.  
  
```C++  
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
 [Idiasymbol::get_type –](../../debugger/debug-interface-access/idiasymbol-get-type.md)