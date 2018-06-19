---
title: Metoda slice (ArrayBuffer) | Microsoft Docs
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
ms.assetid: 2dcc51ff-f444-4d51-80ba-3bcd845ba0ae
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 25fc10a02b4a3422a6720ad91c8bba29906da0e5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791655"
---
# <a name="slice-method-arraybuffer"></a>Metoda slice (ArrayBuffer)
Vrátí část [ArrayBuffer](../../javascript/reference/arraybuffer-object.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
arrayBufferObj.slice(start, [end])   
```  
  
## <a name="parameters"></a>Parametry  
 `arrayBufferObj`  
 Požadováno. [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) části budou zkopírovány z objektu.  
  
 `start`  
 Požadováno. Index bajtů začátku oddílu, který má být zkopírovány.  
  
 `end`  
 Volitelné. Index bajtů konci části, které se mají zkopírovat.  
  
## <a name="remarks"></a>Poznámky  
 `slice` Metoda vrátí [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) objekt, který obsahuje zadaný část `arrayBufferObj`.  
  
 `slice` Metoda zkopíruje do, s výjimkou, bajtů indikován `end`. Pokud `start` nebo `end` je záporná, zadaný index je považován za `length`  +  `start` nebo `end`, kde `length` je délka [ArrayBuffer](../../javascript/reference/arraybuffer-object.md). Pokud `end` je vynechán, extrakce pokračuje na konec `arrayBufferObj`. Pokud `end` dojde před `start`, žádné bajtů se zkopírují do nových [ArrayBuffer](../../javascript/reference/arraybuffer-object.md).  
  
## <a name="example"></a>Příklad  
 Následující příklady ukazují, jak používat `slice` metoda.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer1 = req.response;  
            var buffer2 = buffer1.slice(40, 48);  
            var dataview = new DataView(buffer2);  
            var ints = new Int32Array(buffer2.byteLength / 4);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getInt32(i * 4);  
            }  
        alert(ints[1]);  
        }  
    }  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Arraybuffer – objekt](../../javascript/reference/arraybuffer-object.md)