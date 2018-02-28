---
title: "Neočekávaný kvantifikátor (JavaScript) | Microsoft Docs"
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
- VS.WebClient.Help.SCRIPT5018
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ba6d34f9-2d6f-486c-a929-6cd9818be322
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb6d6d3129057c399dd7369c6f69eb7396f07ab4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="unexpected-quantifier-javascript"></a>Neočekávaný kvantifikátor (JavaScript)
Při sestavování vaší vzor hledání regulárního výrazu, vytvořili jste vzor element s faktor neplatný opakování. Například vzoru  
  
```  
/^+/  
```  
  
 je neplatná, protože element ^ (začátku vstupu) nemůže mít faktor opakování. Následující tabulka uvádí prvky, které nemají faktory opakování.  
  
|Prvek|Popis|  
|-------------|-----------------|  
|^|Začátku vstupu|  
|$|Konec vstupu|  
|\b|Hranice slova|  
|\B|Hranice mimo slovo|  
|*|Opakování nula nebo více|  
|+|Jeden nebo více opakování|  
|?|Žádnou nebo jednu opakování|  
|{n}|n opakování|  
|{n}|n nebo další opakování|  
|{n, m}|Z n m opakování (včetně).|  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Zajistěte, aby že vaše element vzor hledání obsahuje pouze faktory právní opakování.  
  
## <a name="see-also"></a>Viz také  
 [Objekt regulárního výrazu](../../javascript/reference/regular-expression-object-javascript.md)   
 [Syntaxi regulárního výrazu (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)