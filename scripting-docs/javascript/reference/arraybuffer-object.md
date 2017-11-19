---
title: "Arraybuffer – objekt | Microsoft Docs"
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
ms.assetid: 9fda1261-f450-493b-b3db-ecfa9ca93cd7
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c253d63d12a4a5e71d1661aae560b74debecdd62
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="arraybuffer-object"></a>ArrayBuffer – objekt
Představuje vyrovnávací paměti Nezpracovaná binární data, která se používá k ukládání dat pro různé typovaná pole. `ArrayBuffers`Nelze číst nebo zapisovat do přímo, ale mohou být předána do typu pole nebo [DataView – objekt](../../javascript/reference/dataview-object.md) interpretovat nezpracovaná vyrovnávací paměti, podle potřeby.  
  
 Další informace o typovaná pole najdete v tématu [zadali pole](../../javascript/advanced/typed-arrays-javascript.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
  
arrayBuffer = new ArrayBuffer(length);  
```  
  
## <a name="parameters"></a>Parametry  
 `arrayBuffer`  
 Požadováno. Název proměnné, do kterého `ArrayBuffer` objekt je přiřazen.  
  
 `length`  
 Délka vyrovnávací paměti. Obsah ArrayBuffer jsou inicializovány na hodnotu 0. Nebylo-li možné přidělit požadovaný počet bajtů, je vyvolána výjimka.  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí vlastnosti `ArrayBuffer` objektu.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[bytelength – vlastnost](../../javascript/reference/bytelength-property-arraybuffer.md)|Jen pro čtení. Délka ArrayBuffer (v bajtech).|  
  
## <a name="functions"></a>Funkce  
 Následující tabulka uvádí funkce `ArrayBuffer` objektu.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[Funkce ArrayBuffer.isView](../../javascript/reference/arraybuffer-isview-function-arraybuffer.md)|Určuje, zda objekt obsahuje zobrazení vyrovnávací paměti.|  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `ArrayBuffer` objektu.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[Slice – metoda](../../javascript/reference/slice-method-arraybuffer.md)|Vrátí část `ArrayBuffer`.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak používat ke zpracování binární data získat z objektu ArrayBuffer [XMLHttpRequest](http://msdn.microsoft.com/library/ie/ms535874\(v=vs.85\).aspx). Můžete použít [DataView – objekt](../../javascript/reference/dataview-object.md) získání jednotlivých hodnot.  
  
```JavaScript  
var req = new XMLHttpRequest();  
    req.open('GET', "http://www.example.com");  
    req.responseType = "arraybuffer";  
    req.send();  
  
    req.onreadystatechange = function () {  
        if (req.readyState === 4) {  
            var buffer = req.response;  
            var dataview = new DataView(buffer);  
            var ints = new Int32Array(buffer.byteLength / 4);  
            for (var i = 0; i < ints.length; i++) {  
                ints[i] = dataview.getInt32(i * 4);  
            }  
        alert(ints[10]);  
        }  
    }  
  
```  
  
## <a name="remarks"></a>Poznámky  
 Další informace o používání `XmlHttpRequest`, najdete v části [XMLHttpRequest vylepšení](http://msdn.microsoft.com/en-us/be09137c-6546-441b-b953-dcbf72b77069).  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv10](../../javascript/reference/includes/jsv10-md.md)]