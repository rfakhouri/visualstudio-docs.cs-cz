---
title: Throw musí následovat výraz na stejném řádku zdroje | Dokumentace Microsoftu
ms.date: 01/18/2017
ms.prod: visual-studio-windows
ms.technology: vs-javascript
ms.topic: reference
f1_keywords:
- VS.WebClient.Help.SCRIPT1035
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: b03b7747-01a1-40c6-af80-a1dd70bc5781
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4c8ed951fb30b84f114f8f44a60e94b88f0f1d0f
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60069520"
---
# <a name="throw-must-be-followed-by-an-expression-on-the-same-source-line"></a>Vyvolání musí být následováno výrazem na stejném řádku zdroje
Použili jste `throw` – klíčové slovo, ale neřídil se s výrazem na stejném řádku. A `throw` příkaz se skládá ze dvou částí: `throw` – klíčové slovo, za nímž následuje výraz, který má být vyvolána. Příklad:  
  
```JavaScript  
if (denominator == 0) {  
 throw new DivideByZeroException();  
}  
```  
  
 Tyto dvě součásti nelze rozdělit.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
- Ujistěte se, že `throw` – klíčové slovo a výraz, který má být vyvolána, zobrazí se na stejném řádku.  
  
## <a name="see-also"></a>Viz také  
 [Error – objekt](../../javascript/reference/error-object-javascript.md)   
 [Throw – příkaz](../../javascript/reference/throw-statement-javascript.md)   
 [try...catch...finally – příkaz](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)