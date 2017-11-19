---
title: "Uint16array – objekt | Microsoft Docs"
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
ms.assetid: e684647d-04d0-41a9-9089-16612e18ec7d
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 447c0509a29f1696e0204d6f37ff88d3c0bdecae
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="uint16array-object"></a>Uint16Array – objekt
Typované pole 16bitových celočíselných hodnot bez znaménka (typ unsigned integer). Obsah je inicializován s hodnotou 0. Nebylo-li možné přidělit požadovaný počet bajtů, je vyvolána výjimka.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      uint16Array = new Uint16Array( length );  
uint16Array = new Uint16Array( array );  
uint16Array = new Uint16Array( buffer, byteOffset, length );  
```  
  
## <a name="parameters"></a>Parametry  
 `uint16Array`  
 Požadováno. Název proměnné, do kterého **Uint16Array** objekt je přiřazen.  
  
 `length`  
 Určuje počet prvků v poli.  
  
 `array`  
 Pole (nebo typované pole) obsažené v tomto poli. Obsah je inicializován do obsahu daného pole nebo typovaného pole a každý element je převeden na typ Uint16.  
  
 `buffer`  
 ArrayBuffer, který je reprezentován objektem Uint16Array.  
  
 `byteOffset`  
 Volitelné. Určuje posun v bajtech od začátku vyrovnávací paměti, s jakým chcete spustit objekt Uint16Array.  
  
 `length`  
 Počet prvků v poli.  
  
## <a name="constants"></a>Konstanty  
 Následující tabulka uvádí konstanty `Uint16Array`objektu.  
  
|Konstanta|Popis|  
|--------------|-----------------|  
|[Bytes_per_element – konstanta](../../javascript/reference/bytes-per-element-constant-uint16array.md)|Velikost v bajtech každého prvku v poli.|  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí konstanty `Uint16Array`objektu.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[Buffer – vlastnost](../../javascript/reference/buffer-property-uint16array.md)|Jen pro čtení. Získá ArrayBuffer, na který se odkazuje v tomto poli.|  
|[bytelength – vlastnost](../../javascript/reference/bytelength-property-uint16array.md)|Jen pro čtení. Délka tohoto pole od začátku jeho ArrayBuffer v bajtech, jak je stanoveno v době konstrukce.|  
|[byteoffset – vlastnost](../../javascript/reference/byteoffset-property-uint16array.md)|Jen pro čtení. Posun tohoto pole od začátku jeho ArrayBuffer v bajtech, jak je stanoveno v době konstrukce.|  
|[Length – vlastnost](../../javascript/reference/length-property-uint16array.md)|Délka pole.|  
|||  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `Uint16Array`objektu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[set – metoda (Uint16Array)](../../javascript/reference/set-method-uint16array.md)|Nastaví hodnotu nebo pole hodnot.|  
|[subarray – metoda (Uint16Array)](../../javascript/reference/subarray-method-uint16array.md)|Získá nové zobrazení objektu Uint16Array úložiště ArrayBuffer pro toto pole.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití objektu Uint16Array ke zpracování binárních dat získaných z objektu XmlHttpRequest:  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataview = new DataView(buffer);  
            var ints = new Uint16Array(buffer.byteLength / 2);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getUint16(i * 2);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]