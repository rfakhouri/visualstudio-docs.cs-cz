---
title: "setint32 – metoda (DataView) | Microsoft Docs"
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
ms.assetid: 07e5f068-0e3f-4c23-84b3-c72658d7f194
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 00f3f6b03cdd3a8d5d7b95184f1c0ff5c356592a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="setint32-method-dataview"></a>setInt32 – metoda (DataView)
Nastaví hodnotu Int32 v zadané odsazení bajtu od začátku zobrazení. Neexistuje žádné omezení zarovnání; vícebajtové hodnoty může být nastaven na všechny posunu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
dataView.setInt32 (byteOffset, value, littleEndian);   
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
 Následující příklad ukazuje, jak nastavit první Int32 v zobrazení DataView.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            dataView.setInt32(0, 9);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]