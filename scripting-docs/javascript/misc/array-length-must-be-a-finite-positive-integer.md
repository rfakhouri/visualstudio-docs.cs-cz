---
title: "Délka pole musí být konečné kladné celé číslo | Microsoft Docs"
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
- VS.WebClient.Help.SCRIPT5029
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1a467040-4702-4178-848f-418a5974e907
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c6589bd2e9bb4acbec5f169087a49e64417dfae7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="array-length-must-be-a-finite-positive-integer"></a>Délka pole musí být konečné kladné celé číslo
Při volání **pole** konstruktor s argument, který není celé číslo (celá čísla se skládají z nula plus sadu kladná celá čísla).  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Používejte kladná celá čísla jenom v případě, že vytvoření nové `Array` objektu. Pokud chcete vytvořit pole s jediným elementem, který není typu integer, proveďte ve dvou krocích. Pole s jedním prvkem, vytvořte nejdříve umístit hodnota v prvním elementem (array[0]). Následuje příklad, který generuje této chybě.  
  
    ```JavaScript  
    var piArray = new Array(3.14159);  
    ```  
  
     Následující příklad ukazuje správný způsob, jak chcete určit pole s jediným elementem číselná.  
  
    ```JavaScript  
    var piArray = new Array(1);  
    piArray [0] = 3.14159;  
    ```  
  
     Neexistuje žádné horní limit pro velikost pole, než maximální celočíselná hodnota (přibližně 4 miliardy).  
  
## <a name="see-also"></a>Viz také  
 [Použití polí](../../javascript/advanced/using-arrays-javascript.md)