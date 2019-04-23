---
title: Byl očekáván objekt Date | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5006
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: d6ab82e6-ca64-46b4-a06c-5c6b0aa057cb
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2767ffc16b637c6b1e7bdf51cb0815d71f58edac
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60050502"
---
# <a name="date-object-expected"></a>Byl očekáván objekt Date
Pokusili jste se vyvolat **Date.prototype.toString** nebo **Date.prototype.valueOf** metodu na objekt typu než `Date`. Objekt tohoto typu volání musí být typu `Date`. Příklad:  
  
```JavaScript  
var o = new Object;  
o.f = Date.prototype.toString;  
o.f();  
```  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Vyvolat pouze **Date.prototype.toString** nebo **Date.prototype.valueOf** metod u objektů typu `Date`.  
  
## <a name="see-also"></a>Viz také  
 [Date – objekt](../../javascript/reference/date-object-javascript.md)   
 [getDate – metoda (Date)](../../javascript/reference/getdate-method-date-javascript.md)   
 [Vnitřní objekty](../../javascript/intrinsic-objects-javascript.md)