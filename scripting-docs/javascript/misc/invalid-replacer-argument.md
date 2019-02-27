---
title: Neplatný argument nahrazení | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5035
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 4727186f-facd-4aa6-9447-bbefbae83f07
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 640eefb53304de48e4ad2398a02910a1cff1b57d
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2019
ms.locfileid: "56841283"
---
# <a name="invalid-replacer-argument"></a>Neplatný argument nahrazení
Byl proveden pokus o vyvolání `JSON.stringify` s argumentem, který není platný. `replacer` Argument musí být funkce nebo pole.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Změnit `replacer` argumentu funkce nebo pole.  
  
## <a name="example"></a>Příklad  
 Kód v tomto příkladu způsobí chybu modulu runtime, protože `memberfilter` je objekt namísto funkce nebo pole.  
  
```JavaScript  
var contact = new Object();  
contact.firstname = "Jesper";  
contact.surname = "Aaberg";  
contact.phone = ["555-0100", "555-0120"];  
  
var memberfilter = new Object();  
  
// This line will cause a runtime error.  
var jsontext = JSON.stringify(contact, memberfilter, "\t");  
```  
  
## <a name="see-also"></a>Viz také  
 [JSON – objekt](../../javascript/reference/json-object-javascript.md)   
 [JSON.parse – funkce](../../javascript/reference/json-parse-function-javascript.md)   
 [JavaScript – chyby za běhu](../../javascript/reference/javascript-run-time-errors.md)