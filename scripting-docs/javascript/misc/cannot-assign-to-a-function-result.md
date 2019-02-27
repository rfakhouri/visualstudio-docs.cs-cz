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
ms.openlocfilehash: 38cf04b388eaea8ad85f0399978f914feb937c0a
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2019
ms.locfileid: "56844010"
---
# <a name="cannot-assign-to-a-function-result"></a>Nelze přiřazovat hodnoty do výsledku funkce
Jste se pokusili pro přiřazení hodnoty do výsledku funkce. Výsledek funkce může být přiřazen proměnné, ale nelze ji použít jako proměnná. Pokud chcete přiřadit novou hodnotu samotné funkce, vynechejte závorky (operátor volání funkce). Následující příklad ukazuje situaci, ve kterém se tato chyba je generována.  
  
```js
myFunction() = 42;  // Attempting to assign the value 42 to the result of the function call.  
```  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Nepoužívejte hodnotu výsledku volání funkce jako něco můžete *přiřadit*. Můžete přiřadit výsledek volání funkce *proměnné* když.  
  
    ```JavaScript  
    myVar = myFunction(42);  
    ```  
  
-   Funkce můžete alternativně přiřadit samostatně (a ne její návratová hodnota) a proměnné.  
  
    ```JavaScript  
    myFunction = new Function("return 42;");  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Function – objekt](../../javascript/reference/function-object-javascript.md)   
 [Psaní kódu jazyka JavaScript](../../javascript/writing-javascript-code.md)   
 [Funkce](../../javascript/functions-javascript.md)