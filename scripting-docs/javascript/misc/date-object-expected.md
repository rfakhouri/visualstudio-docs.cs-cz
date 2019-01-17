---
title: Byl očekáván objekt Date | Dokumentace Microsoftu
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
- VS.WebClient.Help.SCRIPT5006
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: d6ab82e6-ca64-46b4-a06c-5c6b0aa057cb
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 05e27b822f933ade811084552f6f0379257ae82e
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54349111"
---
# <a name="date-object-expected"></a>Byl očekáván objekt Date
Pokusili jste se vyvolat **Date.prototype.toString** nebo **Date.prototype.valueOf** metodu na objekt typu než `Date`. Objekt tohoto typu volání musí být typu `Date`. Příklad:  
  
```JavaScript  
var o = new Object;  
o.f = Date.prototype.toString;  
o.f();  
```  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Vyvolat pouze **Date.prototype.toString** nebo **Date.prototype.valueOf** metod u objektů typu `Date`.  
  
## <a name="see-also"></a>Viz také  
 [Date – objekt](../../javascript/reference/date-object-javascript.md)   
 [getDate – metoda (Date)](../../javascript/reference/getdate-method-date-javascript.md)   
 [Vnitřní objekty](../../javascript/intrinsic-objects-javascript.md)