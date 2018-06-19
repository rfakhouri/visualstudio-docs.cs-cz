---
title: subarray – metoda (Int8Array) | Microsoft Docs
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
ms.assetid: 46271ed6-a3c3-41fb-bd6f-81efa9e8dedc
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e32c3a0da7e3173273eb40bf52bb6583bd77df51
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791511"
---
# <a name="subarray-method-int8array"></a>subarray – metoda (Int8Array)
Získá nové zobrazení Int8Array úložiště ArrayBuffer pro toto pole odkazující na prvky od begin (včetně) až po end (nikoli včetně).  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
var newInt8Array = int8Array.subset(begin, end);  
```  
  
## <a name="parameters"></a>Parametry  
 `newInt8Array`  
 Podpole vrácené touto metodou.  
  
 `begin`  
 Index začátku pole.  
  
 `end`  
 Index konce pole. To není inkluzivní.  
  
## <a name="remarks"></a>Poznámky  
 Je-li parametr begin nebo end záporný, odkazuje na index z konce pole, nikoli ze začátku. Není-li parametr end zadán, obsahuje podpole všechny prvky typovaného pole od parametru begin po konec. Rozsah určený hodnotami begin a end je omezen na platný rozsah indexů daného pole. Pokud by vypočtená délka nového pole TypedArray byla záporná, bude omezena na nulu. Vrácené pole TypedArray je stejného typu jako pole, na kterém byla tato metoda vyvolána.  
  
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
            var dataView = new DataView(buffer);  
            var intArr = new Int8Array(buffer.byteLength);  
            var subArr = intArr.subarray(0, 2);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]