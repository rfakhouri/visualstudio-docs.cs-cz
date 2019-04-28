---
title: Byl očekáván objekt regulárního výrazu | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT5016
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: e226096c-c58f-4bcb-a71e-fa32ce474b67
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a42cf4b76f4de6d4170f7ef85dafc00841964cfc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63006418"
---
# <a name="regular-expression-object-expected"></a>Byl očekáván objekt regulárního výrazu
Pokusili jste se vyvolat **RegExp.prototype.toString** nebo **RegExp.prototype.valueOf** metodu na objekt typu než `RegExp`. Objekt tohoto typu volání musí být typu `RegExp`.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Vyvolat pouze **RegExp.prototype.toString** nebo **RegExp.prototype.valueOf** metod u objektů typu `RegExp`.  
  
## <a name="see-also"></a>Viz také  
 [Objekt regulárního výrazu](../../javascript/reference/regular-expression-object-javascript.md)   
 [Syntaxe regulárního výrazu (JavaScript)](https://msdn.microsoft.com/library/1400241x)