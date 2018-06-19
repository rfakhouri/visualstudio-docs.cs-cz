---
title: subarray – metoda (Uint8ClampedArray) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 309ed9e8-5805-47ab-b3ed-501cae1323dd
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 76cda8b123b02b4c19a7fd162f3bfbce4540d149
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791673"
---
# <a name="subarray-method-uint8clampedarray"></a>subarray – metoda (Uint8ClampedArray)
Získá nový [Uint8ClampedArray](../../javascript/reference/uint8array-object.md) zobrazení [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) uložení pro toto pole zadání první a poslední členů subarray.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
var newUint8ClampedArray = uint8ClampedArray.subarray(begin, end);  
```  
  
## <a name="parameters"></a>Parametry  
 `newUint8ClampedArray`  
 Požadováno. Podpole vrácené touto metodou.  
  
 `begin`  
 Volitelné. Index začátku pole.  
  
 `end`  
 Volitelné. Index konce pole. To není inkluzivní.  
  
## <a name="remarks"></a>Poznámky  
 Pokud má jedna `begin` nebo `end` je záporná, odkazuje na index od konce pole, naproti tomu od začátku. Pokud `end` je tento parametr zadán, subarray obsahuje všechny elementy z `begin` na konec typované pole. Rozsah určený `begin` a `end` hodnoty se do něj rozsahu platný index pro aktuální pole. Pokud by vypočtená délka nového pole TypedArray byla záporná, bude omezena na nulu. Pole vrácené má stejný typ jako pole, na kterém je tato metoda volána.  
  
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
            var intArr = new Uint8ClampedArray(buffer.byteLength);  
            var subArr = intArr.subarray(0, 2);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Uint8array – objekt](../../javascript/reference/uint8array-object.md)   
 [Arraybuffer – objekt](../../javascript/reference/arraybuffer-object.md)   
 [Objekt Uint8ClampedArray](../../javascript/reference/uint8clampedarray-object-javascript.md)