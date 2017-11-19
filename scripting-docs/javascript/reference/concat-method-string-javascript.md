---
title: "concat – metoda (String) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: concat
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- concat method (String)
- Concat method
ms.assetid: 5d28ebb2-d534-4179-9297-a4c821ee9f24
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1b6419cc6404e06fc780802a30a3b4add8320881
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="concat-method-string-javascript"></a>concat – metoda (String) (JavaScript)
Vrátí řetězec, který obsahuje zřetězení minimálně dva řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
string1. concat([string2[, string3[, . . . [, stringN]]]])  
```  
  
## <a name="parameters"></a>Parametry  
 `string1`  
 Požadováno. `String` Spojení řetězců zadán objekt nebo řetězcový literál, do které všechna ostatní.  
  
 `string2,. . ., stringN`  
 Volitelné. Řetězce, který má být připojen na konec `string1`.  
  
## <a name="remarks"></a>Poznámky  
 Výsledkem `concat` metoda je ekvivalentní: `result`  =  `string1`  +  `string2`  +  `string3`  +  `stringN`. Změna hodnot v řetězci buď zdroj nebo výsledek nemá vliv na hodnotu v jiných řetězec. Pokud některý z argumentů nejsou řetězce, dříve převedena na řetězce před je zřetězen do `string1`.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `concat` metoda při použití s řetězec:  
  
```JavaScript  
var str1 = "ABCD"  
var str2 = "EFGH";  
var str3 = "1234";  
var str4 = "5678";  
document.write(str1.concat(str2, str3, str4));  
  
// Output: "ABCDEFGH12345678"  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [řetězce objektu](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Operátor sčítání (+)](../../javascript/reference/addition-operator-decrement-javascript.md)