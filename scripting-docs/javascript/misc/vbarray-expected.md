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
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60064940"
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