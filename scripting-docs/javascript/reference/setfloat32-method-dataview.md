---
title: "setfloat32 – metoda (DataView) | Microsoft Docs"
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
ms.assetid: b3f68048-c817-48d2-bc17-945e3bcc94d7
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a72bf2781bfbae7c7cd301d02ad71ebfbeffa13
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="setfloat32-method-dataview"></a>setFloat32 – metoda (DataView)
Nastaví hodnotu Float32 v zadané odsazení bajtu od začátku zobrazení. Neexistuje žádné omezení zarovnání; vícebajtové hodnoty může být nastaven na všechny posunu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
dataView.setFloat32 (byteOffset, value, littleEndian);   
```  
  
## <a name="parameters"></a>Parametry  
 `byteOffset`  
 Místo ve vyrovnávací paměti, kdy mají být načtena hodnota.  
  
 `value`  
 Hodnota k nastavení.  
  
 `littleEndian`  
 Volitelné. Pokud hodnotu false nebo nedefinované zasílány big endian hodnotu, jinak by měly být zapsány hodnotu little endian.  
  
## <a name="remarks"></a>Poznámky  
 Tyto metody vyvolána výjimka, pokud by zápisu přesahuje za konec zobrazení.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak nastavit první Float32 v zobrazení DataView.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            dataView.setFloat32(0, 9.1);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]