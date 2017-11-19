---
title: "subarray – metoda (Uint16Array) | Microsoft Docs"
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
ms.assetid: 00b7d3d0-0b47-4da0-95fa-44c9b419d7d0
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2ae83767676538e34243096670ba5a52717ebc27
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="subarray-method-uint16array"></a>subarray – metoda (Uint16Array)
Získá nové zobrazení Uint16Array [arraybuffer – objekt](../../javascript/reference/arraybuffer-object.md) uložení pro toto pole zadání první a poslední členů subarray.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
var newUint16Array = uint16Array.subarray(begin, end);  
```  
  
## <a name="parameters"></a>Parametry  
 `newUint16Array`  
 Podpole vrácené touto metodou.  
  
 `begin`  
 Index začátku pole.  
  
 `end`  
 Index konce pole. To není inkluzivní.  
  
## <a name="remarks"></a>Poznámky  
 Pokud má jedna `begin` nebo `end` je záporná, odkazuje na index od konce pole, naproti tomu od začátku. Pokud `end` je tento parametr zadán, subarray obsahuje všechny elementy z `begin` na konec typované pole. Rozsah určený `begin` a `end` hodnoty se do něj rozsahu platný index pro aktuální pole. Pokud by vypočtená délka nového pole TypedArray byla záporná, bude omezena na nulu. Vrácené pole je stejného typu jako pole, na kterém byla tato metoda vyvolána.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak získat podpole dlouhé dva prvky počínaje prvním prvkem pole.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var intArr = new Uint16Array(buffer.byteLength / 2);  
            var subArr = intArr.subarray(0, 2);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]