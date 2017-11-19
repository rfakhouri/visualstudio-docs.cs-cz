---
title: "getfloat32 – metoda (DataView) | Microsoft Docs"
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
ms.assetid: adecf671-bde4-46be-a875-33b6d6e970b1
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 75fc5be6d8563a44504ae2d1c7ddd9429eccb390
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="getfloat32-method-dataview"></a>getFloat32 – metoda (DataView)
Získá hodnotu Float32 v zadané odsazení bajtu od začátku zobrazení. Neexistuje žádné omezení zarovnání; vícebajtové hodnoty může být získána z jakékoli posun.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
var testFloat = dataView.getFloat32(byteOffset, littleEndian);   
```  
  
## <a name="parameters"></a>Parametry  
 `testFloat`  
 Požadováno. Float32 hodnota, která je vrátila z metody.  
  
 `byteOffset`  
 Místo ve vyrovnávací paměti, kdy mají být načtena hodnota.  
  
 `littleEndian`  
 Volitelné. Pokud hodnotu false nebo nedefinované hodnotu big endian byste si měli přečíst, v opačném případě byste si měli přečíst hodnotu little endian.  
  
## <a name="remarks"></a>Poznámky  
 Tyto metody vyvolat výjimku, pokud by pro čtení i po skončení zobrazení.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak získat první Float32 v zobrazení DataView.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            alert(dataView.getFloat32(0));  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]