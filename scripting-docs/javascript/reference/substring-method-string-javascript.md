---
title: "substring – metoda (String) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: substring
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- substrings
- substring method
ms.assetid: 9cf9a005-cbe3-42fd-828b-57a39f54224c
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 15ebaadc7b24fa97f531a22f6deb1453ff52b3e7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="substring-method-string-javascript"></a>substring – metoda (String) (JavaScript)
Vrátí dílčí řetězec v zadaném umístění v rámci `String` objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      strVariable. substring(start [, end])  
"String Literal".substring(start [, end])   
```  
  
## <a name="parameters"></a>Parametry  
 `start`  
 Požadováno. Index o základu 0 celé číslo označující začátek dílčí řetězec.  
  
 `end`  
 Volitelné. Index o základu 0 celé číslo označující konec dílčí řetězec. Dílčí řetězec až obsahuje znaky, ale ne včetně znak označená `end`.  
  
 Pokud `end` je vynechán, znaky z `start` až do konce původního řetězce jsou vráceny.  
  
## <a name="remarks"></a>Poznámky  
 `substring` Metoda vrátí řetězec obsahující dílčí řetězec z `start` až do, nikoli však `end`.  
  
 **Substring** metoda používá nižší hodnotu `start` a `end` jako počáteční bod dílčí řetězec. Například strvar.substring (0, 3**)** a strvar.substring (3, 0) vrátí stejné dílčí řetězec.  
  
 Pokud má jedna `start` nebo `end` je `NaN` nebo záporná, je nahrazen nula.  
  
 Délka dílčí řetězec je stejná jako absolutní hodnota rozdílu mezi `start` a `end`. Například délka dílčí řetězec, vrátí se v strvar.substring (0, 3) a strvar.substring (3, 0) je tři.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **substring** metoda.  
  
```JavaScript  
var s = "The quick brown fox jumps over the lazy dog.";  
var ss = s.substring(10, 15);  
document.write(ss);  
  
// Output:  
// brown  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [substr – metoda (String)](../../javascript/reference/substr-method-string-javascript.md)