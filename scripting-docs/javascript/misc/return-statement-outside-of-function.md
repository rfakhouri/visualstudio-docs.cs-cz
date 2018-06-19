---
title: '& č. 39; vrátí & č. 39; příkaz mimo funkci | Microsoft Docs'
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
- VS.WebClient.Help.SCRIPT1018
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 03568f9f-5f4f-4a10-a738-9a73f3832b9e
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 07b633c87dc11b291a5a5783f8121b2a368996d6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788907"
---
# <a name="39return39-statement-outside-of-function"></a>& č. 39; vrátí & č. 39; příkaz mimo funkci
Můžete použít `return` příkaz v globálním oboru kódu. `return` Příkaz by měl vyskytovat pouze v rámci tělo funkce.  
  
 Volání funkce s `()` operátor je výraz. Mají všechny výrazy hodnoty; `return` příkaz slouží k určení hodnota retuned funkcí. Obecné formuláře je:  
  
```  
  
return [ expression ];  
```  
  
 Když `return` je spustit příkaz, *výraz* je vyhodnocena a vrátí jako hodnotu funkce. Pokud neexistuje žádný výraz **nedefinované** je vrácen.  
  
 Spuštění funkce zastaví, když `return` spustit příkaz, i když existují další příkazy stále zbývající v těle funkce. Výjimka, která má toto pravidlo je pokud **vrátit** příkaz vyskytuje v **zkuste** blok, a že je odpovídající **nakonec** blok kódu  **Nakonec** bloku, budou spuštěny před funkce vrátí hodnotu.  
  
 Pokud funkce vrátí hodnotu, protože se dosáhne konce tělo funkce bez spuštění `return` prohlášení, je hodnota vrácená **nedefinované** hodnotu (to znamená výsledek funkce nelze použít jako součást rozsáhlejšího výrazu ).  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Odeberte `return` příkaz z hlavní části kódu (globální rozsah).  
  
## <a name="see-also"></a>Viz také  
 [Return – příkaz](../../javascript/reference/return-statement-javascript.md)   
 [Function – objekt](../../javascript/reference/function-object-javascript.md)   
 [caller – vlastnost (Function)](../../javascript/reference/caller-property-function-javascript.md)