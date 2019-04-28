---
title: Byl očekáván objekt Enumerator | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5015
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: dc6e32c1-a6e6-4e12-ac99-e3f65f91c8d7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 06005f635e5173e903cfba6a952750d64181d0bf
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62946339"
---
# <a name="enumerator-object-expected"></a>Byl očekáván objekt Enumerator
Pokusili jste se vyvolat **Enumerator.prototype.atEnd, Enumerator.prototype.item, Enumerator.prototype.moveFirst,** nebo **Enumerator.prototype.moveNext** metodu na objekt typu další než `Enumerator`. Objekt tohoto typu volání musí být typu `Enumerator`. Tady je příklad kódu, který porušuje tato pravidla:  
  
```JavaScript  
var o = new Object;  
o.f = Enumerator.prototype.atEnd;  
o.f();  
```  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Vyvolat pouze **Enumerator.prototype.atEnd**, **Enumerator.prototype.item**, **Enumerator.prototype.moveFirst**, nebo  **Enumerator.prototype.moveNext** metod u objektů typu `Enumerator`. Pokud chcete zjistit, zda váš objekt je `Enumerator` objektu, použijte:  
  
    ```js
    if(x instanceof Enumerator)  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Enumerator – objekt](../../javascript/reference/enumerator-object-javascript.md)