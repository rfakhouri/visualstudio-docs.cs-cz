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
ms.openlocfilehash: 5d1fabd8da6f825a266614a4a5c7fabd5c307130
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63005989"
---
# <a name="vbarray-expected"></a>Byl očekáván objekt VBArray
Můžete zadat objekt, který nebyl safeArray jazyka Visual Basic, když byl očekáván jeden.  
  
```js
new VBArray(safeArray);  
```  
  
 VBArrays jsou jen pro čtení a nelze vytvořit přímo. Argument pole safeArray je hodnota VBArray a musíte již mít vyřízené VBArray hodnotu před předáním `VBArray` konstruktoru. To lze provést pouze načtením hodnoty z existující ActiveX nebo jiného objektu.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Zajistěte předání pouze **VBArray** objektů **VBArray** konstruktoru.  
  
## <a name="see-also"></a>Viz také  
 [VBArray – objekt](../../javascript/reference/vbarray-object-javascript.md)   
 [Používání polí](../../javascript/advanced/using-arrays-javascript.md)