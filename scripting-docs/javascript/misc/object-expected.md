---
title: Byl očekáván objekt | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5007
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 5d88c93d-e5b5-4b11-9bb5-bf1a5e41ccc3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 501496c4f1bb929308ffbb75c6572de3d3f5b33b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63006363"
---
# <a name="object-expected"></a>Očekáván objekt
Pokusili jste se vyvolat metodu nebo vlastnost na objekt typu jiného než `Object`, nebo předaný argument typu jiného než `Object` při `Object` nebyla nutná.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Pouze vyvolat metodu nebo vlastnost u objektů typu `Object`.  
  
- Pokud argument není objekt dojde k chybě, předat objekt typu `Object`.  
  
- Zkontrolujte, zda je získávání undefined nebo null reference vyvolána místo objektu typu `Object`.  
  
     Například, pokud dojde k této chybě na myVar v následujícím kódu:  
  
    ```JavaScript  
    var str = myVar.toString();  
    ```  
  
     Místo toho můžete použít tento kód:  
  
    ```JavaScript  
    if (myVar) {  
        var str = myVar.toString();  
    }  
    ```  
  
## <a name="see-also"></a>Viz také  
 [Object – objekt](../../javascript/reference/object-object-javascript.md)   
 [Objekty a pole](../../javascript/objects-and-arrays-javascript.md)