---
title: Int8array – objekt | Microsoft Docs
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
ms.assetid: 0e3bdbc5-8d85-4c0d-b399-693b01674803
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7e3f85a505f41f2909330e938f4978433fc823f9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790845"
---
# <a name="int8array-object"></a>Int8Array – objekt
Typované pole 8bitových celočíselných hodnot. Obsah je inicializován s hodnotou 0. Nebylo-li možné přidělit požadovaný počet bajtů, je vyvolána výjimka.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      int8Array = new Int8Array( length );  
intArray = new Int8Array( array );  
intArray = new Int8Array( buffer, byteOffset, length);  
```  
  
## <a name="parameters"></a>Parametry  
 `int8Array`  
 Požadováno. Název proměnné, do kterého `Int8Array` objekt je přiřazen.  
  
 `length`  
 Určuje počet prvků v poli.  
  
 `array`  
 Pole (nebo typované pole) obsažené v tomto poli. Obsah je inicializován do obsahu daného pole nebo typovaného pole a každý element je převeden na typ Int8.  
  
 `buffer`  
 ArrayBuffer, který je reprezentován Int8Array.  
  
 `byteOffset`  
 Volitelné. Určuje posun v bajtech od začátku vyrovnávací paměti, s jakým chcete spustit Int8Array.  
  
 `length`  
 Počet prvků v poli.  
  
## <a name="constants"></a>Konstanty  
 Následující tabulka uvádí konstanty `Int8Array`objektu.  
  
|Konstanta|Popis|  
|--------------|-----------------|  
|[Bytes_per_element – konstanta](../../javascript/reference/bytes-per-element-constant-int8array.md)|Velikost v bajtech každého prvku v poli.|  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí konstanty `Int8Array`objektu.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[Buffer – vlastnost](../../javascript/reference/buffer-property-int8array.md)|Jen pro čtení. Získá ArrayBuffer, na který se odkazuje v tomto poli.|  
|[bytelength – vlastnost](../../javascript/reference/bytelength-property-int8array.md)|Jen pro čtení. Délka tohoto pole od začátku jeho ArrayBuffer v bajtech, jak je stanoveno v době konstrukce.|  
|[byteoffset – vlastnost](../../javascript/reference/byteoffset-property-int8array.md)|Jen pro čtení. Posun tohoto pole od začátku jeho ArrayBuffer v bajtech, jak je stanoveno v době konstrukce.|  
|[Length – vlastnost](../../javascript/reference/length-property-int8array.md)|Délka pole.|  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `Int8Array`objektu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[set – metoda (Int8Array)](../../javascript/reference/set-method-int8array.md)|Nastaví hodnotu nebo pole hodnot.|  
|[subarray – metoda (Int8Array)](../../javascript/reference/subarray-method-int8array.md)|Získá nové zobrazení Int8Array úložiště ArrayBuffer pro toto pole.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití objektu Int8Array ke zpracování binárních dat získaných z objektu XmlHttpRequest:  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataview = new DataView(buffer);  
            var ints = new Int8Array(buffer.byteLength);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getInt8(i);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]