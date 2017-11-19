---
title: "set – metoda (Uint16Array) | Microsoft Docs"
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
ms.assetid: 5bfbc50b-d786-4c0d-918a-ae1241a32626
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 74d8e521bc6af4e2994ba1fc81de82c0e3eb1721
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="set-method-uint16array"></a>set – metoda (Uint16Array)
Nastaví hodnotu nebo pole hodnot.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
uint16Array.set(index, value);  
uint16Array.set(array, offset);  
  
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
 Pokud je vstupní pole TypedArray, dvě pole mohou používat stejný podkladový ArrayBuffer. V tomto případě k nastavení hodnot dochází stejně, jako by všechna data byla nejprve zkopírována do dočasné vyrovnávací paměti, která nepřekrývá žádné z polí, a poté zkopírována z dočasné vyrovnávací paměti do aktuálního pole.  
  
 Je-li součet posunu a délky mimo rozsah aktuálního pole TypedArray, je vyvolána výjimka.  
  
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
            var intArr = new Uint16Array(buffer.byteLength / 2);  
            intArr.set(0, 9);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]