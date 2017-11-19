---
title: "getuint8 – metoda (DataView) | Microsoft Docs"
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
ms.assetid: 9fbf4be3-4c0b-4963-a7a1-d57f1501b4cf
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 315baa2ca5abfe006a7f8d524619479d99a11fc9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="getuint8-method-dataview"></a>getUint8 – metoda (DataView)
Získá hodnotu Uint8 v zadané odsazení bajtu od začátku zobrazení. Neexistuje žádné omezení zarovnání; vícebajtové hodnoty může být získána z jakékoli posun.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
var testInt = dataView.getUint8(byteOffset);   
```  
  
## <a name="parameters"></a>Parametry  
 `testInt`  
 Požadováno. Uint8 hodnota, která je vrátila z metody.  
  
 `byteOffset`  
 Místo ve vyrovnávací paměti, kdy mají být načtena hodnota.  
  
## <a name="remarks"></a>Poznámky  
 Tyto metody vyvolat výjimku, pokud by pro čtení i po skončení zobrazení.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak získat první Uint8 v zobrazení DataView.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            alert(dataView.getUint8(0));  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]