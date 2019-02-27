---
title: Neočekávaný kvantifikátor (JavaScript) | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5018
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ba6d34f9-2d6f-486c-a929-6cd9818be322
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f18195f344adca16fce7403d225c42826a2af544
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2019
ms.locfileid: "56843400"
---
# <a name="unexpected-quantifier-javascript"></a>Neočekávaný kvantifikátor (JavaScript)
Při vytváření vaší vyhledávací vzor regulárního výrazu, vytvoříte prvek modelu s faktorem neplatné opakování. Například vzor  
  
```js
/^+/  
```  
  
 je neplatné. protože elementu ^ (začátku vstupu) nemůže mít faktor opakování. Následující tabulka uvádí prvky, které nelze mít faktory opakování.  
  
|Prvek|Popis|  
|-------------|-----------------|  
|^|Začátku vstupu|  
|$|Konec vstupu|  
|\b|Hranice slova|  
|\B|Mimoslovní hranic|  
|*|Nula nebo více opakování|  
|+|Jeden nebo více opakování|  
|?|Žádný nebo jeden opakování|  
|{n}|n opakování|  
|{n,}|n nebo další opakování|  
|{n,m}|Z n až m, včetně opakování|  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Zajistěte, aby že vaše vyhledávací vzor prvek obsahuje pouze faktory právní opakování.  
  
## <a name="see-also"></a>Viz také  
 [Objekt regulárního výrazu](../../javascript/reference/regular-expression-object-javascript.md)   
 [Syntaxe regulárního výrazu (JavaScript)](https://msdn.microsoft.com/library/1400241x)