---
title: příkaz ' return' mimo funkci | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1018
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 03568f9f-5f4f-4a10-a738-9a73f3832b9e
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e23a3b7f4c1979132cf9ec6285c2f60c89341540
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2019
ms.locfileid: "56843075"
---
# <a name="return-statement-outside-of-function"></a>příkaz 'return' mimo funkci
Použili jste `return` příkazu v globálním oboru kódu. `return` Příkaz objevit jenom v těle funkce.  
  
 Volání funkce s `()` výrazu je operátor. Mají všechny výrazy hodnot. `return` prohlášení se používá k určení hodnoty vrácené funkcí. Obecný formát je následující:  
  
```js
  
return [ expression ];  
```  
  
 Když `return` je proveden příkaz *výraz* vyhodnotí a vrátí hodnotu funkce. Pokud není žádný výraz **nedefinované** je vrácena.  
  
 Spuštění funkce zastaví, když `return` je proveden příkaz, i když existují další příkazy stále zbývající v těle funkce. Výjimkou z tohoto pravidla je-li **vrátit** příkazu vyvolá se v rámci **zkuste** bloku, a existuje odpovídající **nakonec** bloku kódu  **Nakonec** blok se spustí předtím, než funkce vrátí.  
  
 Pokud funkce vrátí, protože ji bez spuštění dosáhne konce tělo funkce `return` příkaz, vrácená hodnota je **nedefinované** hodnotu (to znamená, že výsledek funkce nelze použít jako součást rozsáhlejšího výrazu ).  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Odeberte `return` příkaz od hlavní části kódu (globální rozsah).  
  
## <a name="see-also"></a>Viz také  
 [Return – příkaz](../../javascript/reference/return-statement-javascript.md)   
 [Function – objekt](../../javascript/reference/function-object-javascript.md)   
 [caller – vlastnost (Function)](../../javascript/reference/caller-property-function-javascript.md)