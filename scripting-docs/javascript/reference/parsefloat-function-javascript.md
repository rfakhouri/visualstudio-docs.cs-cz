---
title: parseFloat – funkce (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- parseFloat
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- parseFloat method
ms.assetid: a7d87a69-1919-4623-be85-972e6376dd2d
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eb8f6d179abba887542e59d083141534732ed42a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791205"
---
# <a name="parsefloat-function-javascript"></a>parseFloat – funkce (JavaScript)
Převede řetězec na číslo s plovoucí desetinnou čárkou.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
parseFloat(numString)   
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `numString` argument je řetězec, který obsahuje číslo s plovoucí desetinnou čárkou.  
  
 `parseFloat` Funkce vrátí číselnou hodnotu rovná počtu obsažené v `numString`. Pokud žádná předpona `numString` možné úspěšně analyzovat do číslem s plovoucí desetinnou čárkou `NaN` je vrácen (není číslo).  
  
```JavaScript  
parseFloat("abc")      // Returns NaN.  
parseFloat("1.2abc")   // Returns 1.2.  
```  
  
 Můžete otestovat pro `NaN` pomocí `isNaN` funkce.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [Global – objekt](../../javascript/reference/global-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [isNaN – funkce](../../javascript/reference/isnan-function-javascript.md)   
 [parseInt – funkce](../../javascript/reference/parseint-function-javascript.md)   
 [String – objekt](../../javascript/reference/string-object-javascript.md)