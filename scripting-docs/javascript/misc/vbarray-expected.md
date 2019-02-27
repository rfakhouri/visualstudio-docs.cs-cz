---
title: Byl očekáván objekt VBArray | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5013
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f2998d7d-13a4-4bbe-b872-3ff3316551e4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 159a5dd0195cc0cbb244664d75e19d1ac6af3dec
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2019
ms.locfileid: "56843413"
---
# <a name="vbarray-expected"></a>Byl očekáván objekt VBArray
Můžete zadat objekt, který nebyl safeArray jazyka Visual Basic, když byl očekáván jeden.  
  
```js
new VBArray(safeArray);  
```  
  
 VBArrays jsou jen pro čtení a nelze vytvořit přímo. Argument pole safeArray je hodnota VBArray a musíte již mít vyřízené VBArray hodnotu před předáním `VBArray` konstruktoru. To lze provést pouze načtením hodnoty z existující ActiveX nebo jiného objektu.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Zajistěte předání pouze **VBArray** objektů **VBArray** konstruktoru.  
  
## <a name="see-also"></a>Viz také  
 [VBArray – objekt](../../javascript/reference/vbarray-object-javascript.md)   
 [Používání polí](../../javascript/advanced/using-arrays-javascript.md)