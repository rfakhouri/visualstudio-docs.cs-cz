---
title: "Byla očekávána logická hodnota | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT5010
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 35d71b7f-53fd-44c4-a7c7-b1550c65cfd4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 600ab26f60c2196ebc682adcffcd6b24c23cd358
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="boolean-expected"></a>Byla očekávána logická hodnota
Pokoušíte se o vyvolání **Boolean.prototype.toString** nebo **Boolean.prototype.valueOf** metoda na objekt typu jinak než `Boolean`. Objekt typu volání musí být typu `Boolean`. Příklad:  
  
```JavaScript  
var o = new Object;  
o.f = Boolean.prototype.toString;  
o.f();  
```  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Vyvolat jenom logickou hodnotu**. prototype.toString** nebo **Boolean.prototype.valueOf** metody pro objekty typu **logická hodnota.**  
  
## <a name="see-also"></a>Viz také  
 [Boolean – objekt](../../javascript/reference/boolean-object-javascript.md)   
 [Datové typy](../../javascript/data-types-javascript.md)   
 [Řízení toku programu](../../javascript/controlling-program-flow-javascript.md)   
 [Kopírování, předávání a porovnávání dat](../../javascript/advanced/copying-passing-and-comparing-data-javascript.md)