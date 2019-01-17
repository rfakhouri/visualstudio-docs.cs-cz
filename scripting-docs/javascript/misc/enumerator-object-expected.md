---
title: Byl očekáván objekt Enumerator | Dokumentace Microsoftu
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
- VS.WebClient.Help.SCRIPT5015
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: dc6e32c1-a6e6-4e12-ac99-e3f65f91c8d7
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 002c3a748af8f7fa5c21109adcb279f893b38965
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54347239"
---
# <a name="enumerator-object-expected"></a>Byl očekáván objekt Enumerator
Pokusili jste se vyvolat **Enumerator.prototype.atEnd, Enumerator.prototype.item, Enumerator.prototype.moveFirst,** nebo **Enumerator.prototype.moveNext** metodu na objekt typu další než `Enumerator`. Objekt tohoto typu volání musí být typu `Enumerator`. Tady je příklad kódu, který porušuje tato pravidla:  
  
```JavaScript  
var o = new Object;  
o.f = Enumerator.prototype.atEnd;  
o.f();  
```  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Vyvolat pouze **Enumerator.prototype.atEnd**, **Enumerator.prototype.item**, **Enumerator.prototype.moveFirst**, nebo  **Enumerator.prototype.moveNext** metod u objektů typu `Enumerator`. Pokud chcete zjistit, zda váš objekt je `Enumerator` objektu, použijte:  
  
    ```js
    if(x instanceof Enumerator)  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Enumerator – objekt](../../javascript/reference/enumerator-object-javascript.md)