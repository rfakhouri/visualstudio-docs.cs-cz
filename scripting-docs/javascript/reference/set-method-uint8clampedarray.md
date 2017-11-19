---
title: "set – metoda (Uint8ClampedArray) | Microsoft Docs"
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
ms.assetid: 1298443d-5c4c-4329-9ad2-35e213dca157
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ed7635559e615746c577560f1a9266b26acd959d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="set-method-uint8clampedarray"></a>set – metoda (Uint8ClampedArray)
Nastaví hodnotu nebo pole hodnot.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
uint8ClampedArray.set(index, value);  
uint8ClampedArray.set(array, offset);  
  
```  
  
## <a name="parameters"></a>Parametry  
 `index`  
 Index umístění, které chcete nastavit.  
  
 `value`  
 Hodnota k nastavení.  
  
 `array`  
 Pole hodnot k nastavení s typem nebo bez typu.  
  
 `offset`  
 Index v aktuálním poli, do kterého se mají hodnoty zapsat.  
  
## <a name="remarks"></a>Poznámky  
 Pokud je vstupní pole typu pole, dvěma poli mohou používat stejné základní [ArrayBuffer](../../javascript/reference/arraybuffer-object.md). V takovém případě nastavení hodnoty probíhá, jako kdyby všechna data se zkopíruje do dočasné vyrovnávací paměť, která se nepřekrývá s některou z pole a pak kopírování dat z dočasné vyrovnávací paměti do aktuální pole.  
  
 Pokud posunutí plus délka dané pole je mimo rozsah pro aktuální typované pole, je vyvolána výjimka.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak nastavit první prvek pole.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var intArr = new Uint8ClampedArray(buffer.byteLength);  
            intArr.set(0, 9);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Arraybuffer – objekt](../../javascript/reference/arraybuffer-object.md)   
 [Objekt Uint8ClampedArray](../../javascript/reference/uint8clampedarray-object-javascript.md)