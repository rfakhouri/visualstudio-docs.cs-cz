---
title: Neplatný rozsah ve znakové nastavit (JavaScript) | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5021
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 971e9d5a-f88a-47a8-af94-f3c7c4aed5ab
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6b1e404a9df368f639530d533b8cf4bf063f8ad6
ms.sourcegitcommit: 23feea519c47e77b5685fec86c4bbd00d22054e3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/26/2019
ms.locfileid: "56842426"
---
# <a name="invalid-range-in-character-set-javascript"></a>Neplatný rozsah ve znakové sadě (JavaScript)
Pokoušíte se o vytvoření regulárního výrazu s rozsahem sadě neplatný znak. Znakových sad musí být v rozsahu od jednotlivé znaky, jako je například a-z nebo 0-9; třídy znaků, jako je například \w nemůže obsahovat ve znakové sadě. První znak v rozsahu také musí být uvedena před druhým znakem v rozsahu. Příklad:  
  
```JavaScript  
var good = /[a-z]/;     // A valid character range - a comes before z.  
var notGood = /[z-a]/;  // An invalid character range - z does not come before a.  
```  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
-   Používejte pouze jednotlivé znaky pro vytváření sady znak regulárního výrazu a ujistěte se, že jsou ve správném pořadí.  
  
## <a name="see-also"></a>Viz také  
 [Objekt regulárního výrazu](../../javascript/reference/regular-expression-object-javascript.md)   
 [Syntaxe regulárního výrazu (JavaScript)](https://msdn.microsoft.com/library/1400241x)