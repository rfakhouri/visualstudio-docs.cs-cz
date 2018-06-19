---
title: getInt32 – metoda (DataView) | Microsoft Docs
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
ms.assetid: 7a985681-ddb1-4c2b-815c-514c17392e82
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bae788801a81265d39be5ef090e5820122cbb09b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790479"
---
# <a name="getint32-method-dataview"></a>getInt32 – metoda (DataView)
Získá hodnotu Int32 v zadané odsazení bajtu od začátku zobrazení. Neexistuje žádné omezení zarovnání; vícebajtové hodnoty může být získána z jakékoli posun.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
var testInt = dataView.getInt32(byteOffset, littleEndian);   
```  
  
## <a name="parameters"></a>Parametry  
 `testInt`  
 Požadováno. Hodnota Int32, která je vrátila z metody.  
  
 `byteOffset`  
 Místo ve vyrovnávací paměti, kdy mají být načtena hodnota.  
  
 `littleEndian`  
 Volitelné. Pokud hodnotu false nebo nedefinované hodnotu big endian byste si měli přečíst, v opačném případě byste si měli přečíst hodnotu little endian.  
  
## <a name="remarks"></a>Poznámky  
 Tyto metody vyvolat výjimku, pokud by pro čtení i po skončení zobrazení.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak získat první Int32 v zobrazení DataView.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            alert(dataView.getInt32(0));  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]