---
title: Byl očekáván objekt VBArray | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5013
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f2998d7d-13a4-4bbe-b872-3ff3316551e4
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a4b5416c6e37e59a60206bd21606b5214f05a269
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54347452"
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