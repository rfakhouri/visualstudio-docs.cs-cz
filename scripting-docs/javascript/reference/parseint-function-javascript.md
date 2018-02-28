---
title: "parseInt – funkce (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- parseInt
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- parseInt method
ms.assetid: e86471af-2a0e-4359-83af-f1ac81e51421
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 54ee77470d32410ae46a628d54fc3bda97fecc51
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="parseint-function-javascript"></a>parseInt – funkce (JavaScript)
Převede řetězec na celé číslo.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
parseInt(numString, [radix])   
```  
  
## <a name="parameters"></a>Parametry  
 `numString`  
 Požadováno. Řetězec převést na číslo.  
  
 `radix`  
 Volitelné. Hodnotu v rozmezí 2 až 36, která určuje základ číslo v `numString`. Pokud je tento argument není zadaný, řetězce s předponou '0 x, jsou považovány za hexadecimální. Všechny ostatní řetězce jsou považovány za decimal.  
  
## <a name="remarks"></a>Poznámky  
 `parseInt` Funkce vrací celočíselnou hodnotu rovná počtu obsažené v `numString`. Pokud žádná předpona `numString` možné úspěšně analyzovat do celé číslo, `NaN` je vrácen (není číslo).  
  
```JavaScript  
parseInt("abc");     // Returns NaN.  
parseInt("12abc");   // Returns 12.  
```  
  
 Můžete otestovat pro `NaN` pomocí `isNaN` funkce.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [Global – objekt](../../javascript/reference/global-object-javascript.md)  
  
> [!NOTE]
>  Počínaje [!INCLUDE[jsv9textspecific](../../javascript/reference/includes/jsv9textspecific-md.md)], `parseInt` funkce nebude pracovat s řetězec, který má předponou '0' jako osmičkové. Pokud nepoužíváte `parseInt` fungovat, ale řetězce s předponou '0' interpretaci jako octals. V tématu [datové typy](../../javascript/data-types-javascript.md) informace o osmičková celých čísel.  
  
## <a name="see-also"></a>Viz také  
 [isNaN – funkce](../../javascript/reference/isnan-function-javascript.md)   
 [parseFloat – funkce](../../javascript/reference/parsefloat-function-javascript.md)   
 [String – objekt](../../javascript/reference/string-object-javascript.md)   
 [valueOf – metoda (Object)](../../javascript/reference/valueof-method-object-javascript.md)