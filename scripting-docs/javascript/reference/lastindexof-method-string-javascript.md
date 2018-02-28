---
title: "lastIndexOf – metoda (String) (JavaScript) | Microsoft Docs"
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
- lastIndexOf
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- lastIndexOf method, string
- string, lastIndexOf method
ms.assetid: 1ed36ccd-0f0b-4f16-be45-0567207670af
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0fa0f35e970435a4d0296493c20afdeaac128cae
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="lastindexof-method-string-javascript"></a>lastIndexOf – metoda (String) (JavaScript)
Vrátí poslední výskyt podřetězce v řetězci.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
strObj.lastIndexOf(substring[, startindex])  
```  
  
## <a name="parameters"></a>Parametry  
 `strObj`  
 Požadováno. A `String` objekt nebo řetězcový literál.  
  
 `substring`  
 Požadováno. Dílčí řetězec pro vyhledávání.  
  
 `startindex`  
 Volitelné. Index, kdy má začít prohledávat. Pokud tento parametr vynechán, hledání se zahájí na konci řetězce.  
  
## <a name="remarks"></a>Poznámky  
 **LastIndexOf** metoda vrací celočíselnou hodnotu označující začátek podřetězce v rámci `String` objektu. Pokud není nalezen dílčí řetězec, se vrátí -1.  
  
 Pokud `startindex` záporné, `startindex` je považován za nula. Pokud je větší než největší znakový index pozice, se zpracovává jako největší možné index.  
  
 Od poslední znak v řetězci se provádí vyhledávání. Jinak tato metoda je stejný jako **indexOf**.  
  
 Následující příklad ukazuje použití **lastIndexOf** metoda.  
  
```JavaScript  
var str = "time, time";  
  
var s = "";  
s += "time is at position " + str.lastIndexOf("time");  
s += "<br />";  
s += "abc is at position " + str.lastIndexOf("abc");  
  
document.write(s);  
  
// Output:  
// time is at position 6  
// abc is at position -1  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [řetězce objektu](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Metoda indexOf (řetězec)](../../javascript/reference/indexof-method-string-javascript.md)