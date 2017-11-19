---
title: "setuint16 – metoda (DataView) | Microsoft Docs"
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
ms.assetid: bdf47cda-7fa5-4aaa-8aa2-8cf9a8d56cb3
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 935c117995e00284a0083a6bdf7aedfc8c51d15c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="setuint16-method-dataview"></a>setUint16 – metoda (DataView)
Nastaví hodnotu Uint16 v zadané odsazení bajtu od začátku zobrazení. Neexistuje žádné omezení zarovnání; vícebajtové hodnoty může být nastaven na všechny posunu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
dataView.setUint16(byteOffset, value, littleEndian);   
```  
  
## <a name="parameters"></a>Parametry  
 `testInt`  
 Požadováno. Uint16 hodnota, která je vrátila z metody.  
  
 `value`  
 Hodnota k nastavení.  
  
 `byteOffset`  
 Místo ve vyrovnávací paměti, kdy mají být načtena hodnota.  
  
 `littleEndian`  
 Volitelné. Pokud hodnotu false nebo nedefinované zasílány big endian hodnotu, jinak by měly být zapsány hodnotu little endian.  
  
## <a name="remarks"></a>Poznámky  
 Tyto metody vyvolána výjimka, pokud by zápisu přesahuje za konec zobrazení.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak nastavit první Uint16 v zobrazení DataView.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            dataView.setUint16(0, 9);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]