---
title: "Uint32array – objekt | Microsoft Docs"
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
ms.assetid: c4bf5409-2d4b-4660-9f4b-a45d7a02b47e
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 05f185e02ac117491d067ddca6605197d126620e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="uint32array-object"></a>Uint32Array – objekt
Typované pole 32bitových celočíselných hodnot bez znaménka (typ unsigned integer). Obsah je inicializován s hodnotou 0. Nebylo-li možné přidělit požadovaný počet bajtů, je vyvolána výjimka.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      uint32Array = new Uint32Array( length );  
uint32Array = new Uint32Array( array );  
uint32Array = new Uint32Array( buffer, byteOffset, length);  
```  
  
## <a name="parameters"></a>Parametry  
 `uint32Array`  
 Požadováno. Název proměnné, do kterého **Uint32Array** objekt je přiřazen.  
  
 `length`  
 Určuje počet prvků v poli.  
  
 `array`  
 Pole (nebo typované pole) obsažené v tomto poli. Obsah je inicializován do obsahu daného pole nebo typovaného pole a každý element je převeden na typ Uint32.  
  
 `buffer`  
 ArrayBuffer, který představuje objekt Uint32Array.  
  
 `byteOffset`  
 Volitelné. Určuje posun v bajtech od začátku vyrovnávací paměti, s jakým chcete spustit objekt Uint32Array.  
  
 `length`  
 Počet prvků v poli.  
  
## <a name="constants"></a>Konstanty  
 Následující tabulka uvádí konstanty `Uint32Array`objektu.  
  
|Konstanta|Popis|  
|--------------|-----------------|  
|[Bytes_per_element – konstanta](../../javascript/reference/bytes-per-element-constant-uint32array.md)|Velikost v bajtech každého prvku v poli.|  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí konstanty `Uint32Array`objektu.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[Buffer – vlastnost](../../javascript/reference/buffer-property-uint32array.md)|Jen pro čtení. Získá ArrayBuffer, na který se odkazuje v tomto poli.|  
|[bytelength – vlastnost](../../javascript/reference/bytelength-property-uint32array.md)|Jen pro čtení. Délka tohoto pole od začátku jeho ArrayBuffer v bajtech, jak je stanoveno v době konstrukce.|  
|[byteoffset – vlastnost](../../javascript/reference/byteoffset-property-uint32array.md)|Jen pro čtení. Posun tohoto pole od začátku jeho ArrayBuffer v bajtech, jak je stanoveno v době konstrukce.|  
|[Length – vlastnost](../../javascript/reference/length-property-uint32array.md)|Délka pole.|  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `Uint32Array`objektu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[set – metoda (Uint32Array)](../../javascript/reference/set-method-uint32array.md)|Nastaví hodnotu nebo pole hodnot.|  
|[subarray – metoda (Uint32Array)](../../javascript/reference/subarray-method-uint32array.md)|Získá nové zobrazení Uint32Array úložiště ArrayBuffer pro toto pole.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití objektu Uint32Array ke zpracování binárních dat získaných z objektu XMLHttpRequest:  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataview = new DataView(buffer);  
            var ints = new Uint32Array(buffer.byteLength / 4);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getUint32(i * 4);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]