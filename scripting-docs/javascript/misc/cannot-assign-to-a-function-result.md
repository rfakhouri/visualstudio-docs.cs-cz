---
title: Nelze přiřazovat hodnoty do výsledku funkce | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5003
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ee8ffb3a-1451-4cb3-99bf-5e9cf8b77d79
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 226056f139e45f432d757aff8f8774b013742de3
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60076809"
---
# <a name="cannot-assign-to-a-function-result"></a>Nelze přiřazovat hodnoty do výsledku funkce
Jste se pokusili pro přiřazení hodnoty do výsledku funkce. Výsledek funkce může být přiřazen proměnné, ale nelze ji použít jako proměnná. Pokud chcete přiřadit novou hodnotu samotné funkce, vynechejte závorky (operátor volání funkce). Následující příklad ukazuje situaci, ve kterém se tato chyba je generována.  
  
```js
myFunction() = 42;  // Attempting to assign the value 42 to the result of the function call.  
```  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Nepoužívejte hodnotu výsledku volání funkce jako něco můžete *přiřadit*. Můžete přiřadit výsledek volání funkce *proměnné* když.  
  
    ```JavaScript  
    myVar = myFunction(42);  
    ```  
  
- Funkce můžete alternativně přiřadit samostatně (a ne její návratová hodnota) a proměnné.  
  
    ```JavaScript  
    myFunction = new Function("return 42;");  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Function – objekt](../../javascript/reference/function-object-javascript.md)   
 [Psaní kódu jazyka JavaScript](../../javascript/writing-javascript-code.md)   
 [Funkce](../../javascript/functions-javascript.md)