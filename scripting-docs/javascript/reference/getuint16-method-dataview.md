---
title: "getuint16 – metoda (DataView) | Microsoft Docs"
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
ms.assetid: 3c0d9ad8-30b0-42a3-b0fe-aa805398c396
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2da1ea7bdbbbc1d99f9b7b6c33e4b3d83e0ba84f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="getuint16-method-dataview"></a>getUint16 – metoda (DataView)
Získá hodnotu Uint16 v zadané odsazení bajtu od začátku zobrazení. Neexistuje žádné omezení zarovnání; vícebajtové hodnoty může být získána z jakékoli posun.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
var testInt = dataView.getUint16(byteOffset, littleEndian);   
```  
  
## <a name="parameters"></a>Parametry  
 `testInt`  
 Požadováno. Uint16 hodnota, která je vrátila z metody.  
  
 `byteOffset`  
 Místo ve vyrovnávací paměti, kdy mají být načtena hodnota.  
  
 `littleEndian`  
 Volitelné. Pokud hodnotu false nebo nedefinované hodnotu big endian byste si měli přečíst, v opačném případě byste si měli přečíst hodnotu little endian.  
  
## <a name="remarks"></a>Poznámky  
 Tyto metody vyvolat výjimku, pokud by pro čtení i po skončení zobrazení.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak získat první Uint16 v zobrazení DataView.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            alert(dataView.getUint16(0));  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]