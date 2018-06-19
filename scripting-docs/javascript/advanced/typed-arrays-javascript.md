---
title: Zadané pole (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: fa82c562-0ebf-4559-aecc-166e59f7fb64
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5fc3b29a4593e7c627a6e606242229e87fa5be54
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789138"
---
# <a name="typed-arrays-javascript"></a>Typovaná pole (JavaScript)
Typovaná pole můžete použít pro zpracování binární data ze zdrojů, například síťové protokoly, binární formáty souborů a raw grafiky vyrovnávací paměti. Typovaná pole můžete použít také ke správě binární data v paměti s dobře známé bajtů rozložení.  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje, jak používat [arraybuffer – objekt](../../javascript/reference/arraybuffer-object.md) jako odpověď [XMLHttpRequest](http://msdn.microsoft.com/library/ie/ms535874\(v=vs.85\).aspx). Počet bajtů v odpovědi můžete upravit pomocí různých metod [DataView – objekt](../../javascript/reference/dataview-object.md), nebo tak, že zkopírujete do příslušné typované pole bajtů.  
  
> [!TIP]
>  Další informace o použití různých odpovědi typů s `XmlHttpRequest`, najdete v části [XMLHttpRequest.responseType](http://msdn.microsoft.com/en-us/8d7738d1-4bfd-4cf1-8015-174def089556), [XMLHttpRequest vylepšení](http://msdn.microsoft.com/en-us/be09137c-6546-441b-b953-dcbf72b77069), a [stahování jiný typy obsahu (aplikace pro Windows Store)](http://msdn.microsoft.com/en-us/c0006bbd-17f9-4c6a-af81-2acaf109111d).  
  
```JavaScript  
...  
<div id="xhrDiv"></div>  
...  
var name = "http://www.microsoft.com";  
var xhrDiv = document.getElementById("xhrDiv");  
  
var req = new XMLHttpRequest();  
req.open("GET", name, true);  
req.responseType = "arraybuffer";  
req.onreadystatechange = function () {  
if (req.readyState == req.DONE) {  
    var arrayResponse = req.response;  
    var dataView = new DataView(arrayResponse);  
    var ints = new Uint32Array(dataView.byteLength / 4);  
  
    xhrDiv.style.backgroundColor = "#00FF00";  
    xhrDiv.innerText = "Array is " + ints.length + "uints long";  
    }  
}  
req.send();  
```  
  
## <a name="arraybuffer"></a>ArrayBuffer  
 [Arraybuffer – objekt](../../javascript/reference/arraybuffer-object.md) představuje vyrovnávací paměti nezpracovaná data, která se používá k ukládání dat pro různé typovaná pole. Nelze číst nebo zapisovat do `ArrayBuffer`, ale můžete jej předat do typované pole nebo [DataView – objekt](../../javascript/reference/dataview-object.md) interpretovat nezpracovaná vyrovnávací paměti. Můžete použít `ArrayBuffer` ukládat jakýkoli druh data (nebo smíšené typy dat).  
  
## <a name="dataview"></a>DataView  
 Můžete použít [DataView – objekt](../../javascript/reference/dataview-object.md) číst a zapisovat do libovolného umístění v různých druhů binárních dat `ArrayBuffer`.  
  
## <a name="typed-arrays"></a>Typovaná pole  
 Typy typované pole představují zobrazení [arraybuffer – objekt](../../javascript/reference/arraybuffer-object.md) který indexované a s nimi manipulovat. Všechny typy pole mají pevnou délkou.  
  
||||  
|-|-|-|  
|Název|Velikost (v bajtech)|Popis|  
|[Int8array – objekt](../../javascript/reference/int8array-object.md)|1|Osm bitů na dva doplňují číslo se znaménkem|  
|[Uint8array – objekt](../../javascript/reference/uint8array-object.md)|1|Celé číslo bez znaménka osm bitů|  
|[Int16array – objekt](../../javascript/reference/int16array-object.md)|2|16 bitů na dva doplňují číslo se znaménkem|  
|[Uint16array – objekt](../../javascript/reference/uint16array-object.md)|2|Celé číslo bez znaménka šestnáct bitů|  
|[Int32array – objekt](../../javascript/reference/int32array-object.md)|4|Třicet two-bit dva na doplňují číslo se znaménkem|  
|[Uint32array – objekt](../../javascript/reference/uint32array-object.md)|4|Celé číslo bez znaménka třicet two-bit|  
|[Float32array – objekt](../../javascript/reference/float32array-object.md)|4|IEEE třicet two-bit plovoucí desetinnou čárkou|  
|[Float64array – objekt](../../javascript/reference/float64array-object.md)|8|IEEE šedesáti čtyřmi bit plovoucí desetinnou čárkou|