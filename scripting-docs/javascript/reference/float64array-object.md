---
title: "Float64array – objekt | Microsoft Docs"
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
ms.assetid: 74c945dc-56ae-458c-b0aa-782f240e9b6c
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 20544812d94c1234d85d714f6e469d0de4f4c5ab
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="float64array-object"></a>Float64Array – objekt
Typované pole 64bitových plovoucích hodnot (typ float). Obsah je inicializován s hodnotou 0. Nebylo-li možné přidělit požadovaný počet bajtů, je vyvolána výjimka.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      float64Array = new Float64Array( length );  
float64Array = new Float64Array( array );  
float64Array = new Float64Array( buffer, byteOffset, length);  
```  
  
## <a name="parameters"></a>Parametry  
 `float64Array`  
 Požadováno. Název proměnné, do kterého **Float64Array** objekt je přiřazen.  
  
 `length`  
 Určuje počet prvků v poli.  
  
 `array`  
 Pole (nebo typované pole) obsažené v tomto poli. Obsah je inicializován do obsahu daného pole nebo typovaného pole a každý prvek je převeden na typ Float64.  
  
 `buffer`  
 ArrayBuffer, který představuje Float64Array.  
  
 `byteOffset`  
 Volitelné. Určuje posun v bajtech od začátku vyrovnávací paměti, s jakým má začínat Float64Array.  
  
 `length`  
 Počet prvků v poli.  
  
## <a name="constants"></a>Konstanty  
 Následující tabulka uvádí konstanty `Float64Array`objektu.  
  
|Konstanta|Popis|  
|--------------|-----------------|  
|[Bytes_per_element – konstanta](../../javascript/reference/bytes-per-element-constant-float64array.md)|Velikost v bajtech každého prvku v poli.|  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí konstanty `Float64Array`objektu.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[Buffer – vlastnost](../../javascript/reference/bytelength-property-float64array.md)|Jen pro čtení. Získá ArrayBuffer, na který se odkazuje v tomto poli.|  
|[bytelength – vlastnost](../../javascript/reference/bytelength-property-float64array.md)|Jen pro čtení. Délka tohoto pole od začátku jeho ArrayBuffer v bajtech, jak je stanoveno v době konstrukce.|  
|[byteoffset – vlastnost](../../javascript/reference/length-property-float64array.md)|Jen pro čtení. Posun tohoto pole od začátku jeho ArrayBuffer v bajtech, jak je stanoveno v době konstrukce.|  
|[Length – vlastnost](../../javascript/reference/length-property-float64array.md)|Délka pole.|  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `Float64Array`objektu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Get – metoda](../../javascript/reference/get-method-float64array.md)|Lze vynechat. Získá prvek na pozici zadaného indexu.|  
|[set – metoda (Float64Array)](../../javascript/reference/set-method-float64array.md)|Nastaví hodnotu nebo pole hodnot.|  
|[subarray – metoda (Float64Array)](../../javascript/reference/subarray-method-float64array.md)|Získá nové zobrazení Float64Array úložiště ArrayBuffer pro toto pole.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití objektu Float64Array ke zpracování binárních dat získaných z objektu XmlHttpRequest:  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataview = new DataView(buffer);  
            var ints = new Float64Array(buffer.byteLength / 8);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getFloat64(i * 8);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]