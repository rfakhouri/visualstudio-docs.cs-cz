---
title: "String.fromCharCode – funkce (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: fromCharCode
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- fromCharCodeAt method
- characters, from Unicode
ms.assetid: f64120c1-23a7-48ca-8d1c-db3e8856cab4
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dbcd9062d7da0b73647c1d9eb6cc207af23c3532
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="stringfromcharcode-function-javascript"></a>String.fromCharCode – funkce (JavaScript)
Vrátí hodnotu typu string z několika hodnot znaků Unicode.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
String.fromCharCode([code1[, code2[, ...[, codeN]]]])   
```  
  
## <a name="parameters"></a>Parametry  
 `String`  
 Požadováno. `String` Objektu.  
  
 `code1`, . . . , `codeN`  
 Volitelné. Řada hodnot znaků Unicode převést na řetězec. Pokud jsou zadány žádné argumenty, výsledkem je prázdný řetězec.  
  
## <a name="remarks"></a>Poznámky  
 Volání této funkce na `String` objektu a nikoli na instanci řetězec.  
  
 Následující příklad ukazuje, jak lze pomocí této metody:  
  
```JavaScript  
var test = String.fromCharCode(112, 108, 97, 105, 110);  
document.write(test);  
  
// Output: plain  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [charCodeAt – metoda (String)](../../javascript/reference/charcodeat-method-string-javascript.md)