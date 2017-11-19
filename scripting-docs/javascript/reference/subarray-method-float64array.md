---
title: "subarray – metoda (Float64Array) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f3c24e1b-5fb2-49a1-8183-0fda33dbeaba
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 08f72854b9dc87394bdce2552d5d48ff4b1270f8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="subarray-method-float64array"></a>subarray – metoda (Float64Array)
Získá nové zobrazení Float64Array [arraybuffer – objekt](../../javascript/reference/arraybuffer-object.md) uložení pro toto pole zadání první a poslední členů subarray.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
var newFloat64Array = float64Array.subarray(begin, end);  
```  
  
## <a name="parameters"></a>Parametry  
 `newFloat64Array`  
 Podpole vrácené touto metodou.  
  
 `begin`  
 Index začátku pole.  
  
 `end`  
 Index konce pole.  
  
## <a name="remarks"></a>Poznámky  
 Pokud má jedna `begin` nebo `end` je záporná, odkazuje na index od konce pole, naproti tomu od začátku. Pokud `end` je tento parametr zadán, subarray obsahuje všechny elementy z `begin` na konec typované pole. Rozsah určený `begin` a `end` hodnoty se do něj rozsahu platný index pro aktuální pole. Pokud by vypočtená délka nového pole TypedArray byla záporná, bude omezena na nulu. Vrácené pole je stejného typu jako pole, na kterém byla tato metoda vyvolána.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak získat subarray tři prvky dlouhý, počínaje první prvek pole.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var floatArr = new Float64Array(buffer.byteLength / 8);  
            var subArr = floatArr.subarray(0, 2);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]