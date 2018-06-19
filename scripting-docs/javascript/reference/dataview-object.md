---
title: DataView – objekt | Microsoft Docs
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
ms.assetid: 250ec067-7505-4ee0-82ab-bfd3c2820afa
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 370ee1afbdf7fe1d87843c4979833d54a575a4fd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790689"
---
# <a name="dataview-object"></a>DataView – objekt
Objekt zobrazení dat můžete použít ke čtení a zápisu různých druhů binárních dat na libovolné místo v ArrayBuffer.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dataView = new DataView(buffer, byteOffset, byteLength);  
```  
  
## <a name="parameters"></a>Parametry  
 `dataView`  
 Požadováno. Název proměnné, do kterého **DataView** objekt je přiřazen.  
  
 `buffer`  
 ArrayBuffer, který představuje zobrazení DataView.  
  
 `byteOffset`  
 Volitelné. Určuje posun v bajtech od začátku, kdy by měl začínat zobrazení DataView vyrovnávací paměti.  
  
 `byteLength`  
 Volitelné. Určuje dobu (v bajtech) v části vyrovnávací paměti, kterou by měl představovat zobrazení DataView.  
  
## <a name="remarks"></a>Poznámky  
 Pokud byteoffset – a bytelength – vynechány, rozdělena na celý rozsah ArrayBuffer zobrazení DataView. Pokud bytelength – je vynechán, zobrazení DataView rozšiřuje z daného byteoffset – až do konce ArrayBuffer. Pokud daný byteoffset – a bytelength – odkazuje oblast přesahuje za konec ArrayBuffer, je vyvolána výjimka.  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí vlastnosti `DataView` objektu.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[Buffer – vlastnost](../../javascript/reference/buffer-property-dataview.md)|Jen pro čtení. Získá ArrayBuffer, který se odkazuje v tomto zobrazení.|  
|[bytelength – vlastnost](../../javascript/reference/bytelength-property-dataview.md)|Jen pro čtení. Délka tohoto zobrazení od začátku jeho ArrayBuffer v bajtech, jak je stanoveno v době konstrukce.|  
|[byteoffset – vlastnost](../../javascript/reference/byteoffset-property-dataview.md)|Jen pro čtení. Posun od začátku jeho ArrayBuffer v bajtech, jako pevný během vytváření tohoto zobrazení.|  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `DataView`objektu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[getint8 – metoda](../../javascript/reference/getint8-method-dataview.md)|Získá hodnotu Int8 v zadané odsazení bajtu od začátku zobrazení.|  
|[getuint8 – metoda (DataView)](../../javascript/reference/getuint8-method-dataview.md)|Získá hodnotu Uint8 v zadané odsazení bajtu od začátku zobrazení.|  
|[getint16 – metoda (DataView)](../../javascript/reference/getint16-method-dataview.md)|Získá hodnotu Int16 v zadané odsazení bajtu od začátku zobrazení.|  
|[getuint16 – metoda (DataView)](../../javascript/reference/getuint16-method-dataview.md)|Získá hodnotu Uint16 v zadané odsazení bajtu od začátku zobrazení.|  
|[getInt32 – metoda (DataView)](../../javascript/reference/getint32-method-dataview.md)|Získá hodnotu Int32 v zadané odsazení bajtu od začátku zobrazení.|  
|[GetUINT32 – metoda (DataView)](../../javascript/reference/getuint32-method-dataview.md)|Získá hodnotu Uint32 v zadané odsazení bajtu od začátku zobrazení.|  
|[getfloat32 – metoda (DataView)](../../javascript/reference/getfloat32-method-dataview.md)|Získá hodnotu Float32 v zadané odsazení bajtu od začátku zobrazení.|  
|[getfloat64 – metoda (DataView)](../../javascript/reference/getfloat64-method-dataview.md)|Získá hodnotu Float64 v zadané odsazení bajtu od začátku zobrazení.|  
|[setint8 – metoda (DataView)](../../javascript/reference/setint8-method-dataview.md)|Ukládá hodnotu Int8 v zadané odsazení bajtu od začátku zobrazení.|  
|[setuint8 – metoda (DataView)](../../javascript/reference/setuint8-method-dataview.md)|Ukládá hodnotu Uint8 v zadané odsazení bajtu od začátku zobrazení.|  
|[setint16 – metoda (DataView)](../../javascript/reference/setint16-method-dataview.md)|Ukládá hodnotu Int16 v zadané odsazení bajtu od začátku zobrazení.|  
|[setuint16 – metoda (DataView)](../../javascript/reference/setuint16-method-dataview.md)|Ukládá hodnotu Uint16 v zadané odsazení bajtu od začátku zobrazení.|  
|[setint32 – metoda (DataView)](../../javascript/reference/setint32-method-dataview.md)|Ukládá hodnotu Int32 v zadané odsazení bajtu od začátku zobrazení.|  
|[setuint32 – metoda (DataView)](../../javascript/reference/setuint32-method-dataview.md)|Ukládá hodnotu Uint32 v zadané odsazení bajtu od začátku zobrazení.|  
|[setfloat32 – metoda (DataView)](../../javascript/reference/setfloat32-method-dataview.md)|Ukládá hodnotu Float32 v zadané odsazení bajtu od začátku zobrazení.|  
|[setfloat64 – metoda (DataView)](../../javascript/reference/setfloat64-method-dataview.md)|Ukládá hodnotu Float64 v zadané odsazení bajtu od začátku zobrazení.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak používat objekt DataView zpracovat binární data získat z XmlHttpRequest:  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataView = new DataView(buffer);  
            var ints = new Int32Array(dataView.byteLength / 4);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getInt32(i * 4);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]