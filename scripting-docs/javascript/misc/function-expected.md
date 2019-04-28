---
title: Byla očekávána funkce | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5002
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: f62ade94-9f6f-4832-9b9b-49a06a385bbe
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4442143b2766ed3608a852d0f811a6b943fd19df
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63007103"
---
# <a name="function-expected"></a>Byla očekávána funkce
Buď jste se pokusili vyvolat jeden z **prototyp funkce** metody u objektu, který nebyl `Function` objektu, nebo můžete použít objekt v kontextu volání funkce. Například následující kód vytvoří tuto chybu, protože **příklad** není funkce.  
  
```JavaScript  
var example = new Object();  // Create a new object called "example".  
var x = example();           // Try and call example as if it were a function.  
```  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Volat pouze **prototyp funkce** metody `Function` objekty.  
  
- Ujistěte se, že používáte operátoru volání funkce `()` volat pouze funkce.  
  
## <a name="see-also"></a>Viz také  
 [Function – objekt](../../javascript/reference/function-object-javascript.md)   
 [prototype – vlastnost (Object)](../../javascript/reference/prototype-property-object-javascript.md)