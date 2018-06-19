---
title: Uint8ClampedArray – objekt (JavaScript) | Microsoft Docs
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
ms.assetid: 0c5537f7-00b4-487a-8fba-ef032e67e7bd
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 51673eadc8eb905355bf136dc82b2f240462180a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792165"
---
# <a name="uint8clampedarray-object-javascript"></a>Uint8ClampedArray – objekt (JavaScript)
Typovaná pole 8bitové nepodepsané celých čísel s hodnotami těsně rozsahu 0 až 255. Obsah je inicializován s hodnotou 0. Pokud požadovaný počet bajtů nelze přidělit, je vyvolána výjimka.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      uint8ClampedArray = new Uint8ClampedArray( length );  
uint8ClampedArray = new Uint8ClampedArray( array );  
uint8ClampedArray = new Uint8ClampedArray( buffer, byteOffset, length);  
```  
  
## <a name="parameters"></a>Parametry  
 `uint8ClampedArray`  
 Požadováno. Název proměnné, do kterého `Uint8ClampedArray` objekt je přiřazen.  
  
 `length`  
 Volitelné. Počet prvků v poli.  
  
 `array`  
 Volitelné. Pole (nebo typovaná pole) obsahující toto pole. Obsah se inicializována tak, aby obsah daného pole nebo typované pole s každý prvek převést na `Uint8` typu.  
  
 `buffer`  
 Volitelné. [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) , `Uint8ClampedArray` představuje.  
  
 `byteOffset`  
 Volitelné. Posun v bajtech, od začátku vyrovnávací paměti, kdy `Uint8ClampedArray` by měl začínat.  
  
 `length`  
 Volitelné. Počet prvků v poli.  
  
## <a name="remarks"></a>Poznámky  
 Hodnotami uloženými v `Uint8ClampedArray` objektu jsou v rozmezí od 0 do 255. Pokud nastavíte zápornou hodnotu člena pole, 0 nastavená pro hodnotu. Pokud nastavíte hodnotu, která je větší než 255, 255 je nastavená jako hodnota.  
  
 Hodnoty v `Uint8ClampedArray` objekt jsou zaokrouhleny nejbližší i hodnotu, která je volána bankovní zaokrouhlení.  
  
## <a name="constants"></a>Konstanty  
 Následující tabulka uvádí konstanty `Uint8ClampedArray` objektu.  
  
|Konstanta|Popis|  
|--------------|-----------------|  
|[Bytes_per_element – konstanta](../../javascript/reference/bytes-per-element-constant-uint8clampedarray.md)|Velikost v bajtech, každý prvek v poli.|  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí konstanty `Uint8ClampedArray` objektu.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[Buffer – vlastnost](../../javascript/reference/buffer-property-uint8clampedarray.md)|Jen pro čtení. Získá [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) odkazuje toto pole.|  
|[bytelength – vlastnost](../../javascript/reference/bytelength-property-uint8clampedarray.md)|Jen pro čtení. Délka tohoto pole od začátku jeho [ArrayBuffer](../../javascript/reference/arraybuffer-object.md), v bajtech, jako pevný v době konstrukce.|  
|[byteoffset – vlastnost](../../javascript/reference/byteoffset-property-uint8clampedarray.md)|Jen pro čtení. Posun toto pole od začátku jeho [ArrayBuffer](../../javascript/reference/arraybuffer-object.md), v bajtech, jako pevný v době konstrukce.|  
|[Length – vlastnost](../../javascript/reference/length-property-uint8clampedarray.md)|Délka pole.|  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `Uint8ClampedArray` objektu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[set – metoda](../../javascript/reference/set-method-uint8clampedarray.md)|Nastaví hodnotu nebo pole hodnot.|  
|[subarray – metoda](../../javascript/reference/subarray-method-uint8clampedarray.md)|Získá nový `Uint8ClampedArray` zobrazení [ArrayBuffer](../../javascript/reference/arraybuffer-object.md) uložení pro toto pole, zadávání první a poslední prvků subarray.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak používat `Uint8ClampedArray` objekt binární data získat z `XmlHttpRequest`:  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataview = new DataView(buffer);  
            var ints = new Uint8ClampedArray(buffer.byteLength);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getUint8(i);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak jsou hodnoty v omezení `Uint8ClampedArray`.  
  
```JavaScript  
var ints = new Uint8ClampedArray(2);  
ints[0] = -1;  // 0 will be assigned.  
ints[1] = 256; // 255 will be assigned.  
  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak hodnoty jsou zaokrouhleny v `Uint8ClampedArray`.  
  
```  
var ints = new Uint8ClampedArray(4);  
ints[0] = 11.3; // 11 will be assigned (same as Int8Array).  
ints[1] = 11.8; // 12 will be assigned (same as Int8Array).  
ints[2] = 10.5; // 10 will be assigned (rounded to the nearest   
                // even value).  
ints[3] = 11.5; // 12 will be assigned (rounded to the nearest   
                // even value).  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11_winonly](../../javascript/reference/includes/jsv11-winonly-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Uint8array – objekt](../../javascript/reference/uint8array-object.md)   
 [Arraybuffer – objekt](../../javascript/reference/arraybuffer-object.md)
