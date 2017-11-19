---
title: "Idiasymbol::get_isaggregated – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSymbol::get_isAggregated method
ms.assetid: 24d280ef-6ea3-4958-9418-4ad3ca7c67c1
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0da925fa76eb477a5995815f74a664899e721640
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolgetisaggregated"></a>IDiaSymbol::get_isAggregated
Načte příznak určující, zda je symbol dat je součástí agregace nebo kolekce symbolů; Kompilátor bude považovat za agregované symboly samostatné entity, ale jsou ve skutečnosti součástí jeden větší symbol.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_isAggregated(  
   BOOL *pFlag  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pFlag`  
 [out] Vrátí `TRUE` Pokud data je součástí agregaci symboly rozdělení z nadřazené symbol; jinak vrátí `FALSE`.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
> [!NOTE]
>  Vrácená hodnota `S_FALSE` znamená vlastnost není k dispozici pro symbol.  
  
## <a name="remarks"></a>Poznámky  
 [Idiasymbol::get_issplitted –](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md) je metoda `TRUE` pro symbol, který je nadřazená agregované symbolů.  
  
## <a name="requirements"></a>Požadavky  
  
|Požadavek|Popis|  
|-----------------|-----------------|  
|Hlavičky:|dia2.h|  
|Verze:|V8.0 DIA SDK|  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)   
 [Idiasymbol::get_issplitted –](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md)