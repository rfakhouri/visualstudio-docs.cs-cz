---
title: Byl očekáván objekt | Dokumentace Microsoftu
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
- VS.WebClient.Help.SCRIPT5007
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 5d88c93d-e5b5-4b11-9bb5-bf1a5e41ccc3
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 49d66c82081af06bf23a43922629a579a6d6f590
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345783"
---
# <a name="object-expected"></a>Očekáván objekt
Pokusili jste se vyvolat metodu nebo vlastnost na objekt typu jiného než `Object`, nebo předaný argument typu jiného než `Object` při `Object` nebyla nutná.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Pouze vyvolat metodu nebo vlastnost u objektů typu `Object`.  
  
-   Pokud argument není objekt dojde k chybě, předat objekt typu `Object`.  
  
-   Zkontrolujte, zda je získávání undefined nebo null reference vyvolána místo objektu typu `Object`.  
  
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