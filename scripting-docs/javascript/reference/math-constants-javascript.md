---
title: "Matematické konstanty (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- LN2 constant [JavaScript]
- E constant [JavaScript]
- LOG10E constant [JavaScript]
- SQRT1_2 constant [JavaScript]
- LOG2E constant [JavaScript]
- Math.SQRT2 constant [JavaScript]
- PI constant [JavaScript]
- Math.LOG2E constant [JavaScript]
- constants [JavaScript], math
- Math.E constant [JavaScript]
- logarithm consants [JavaScript]
- Math.LOG10E constant [JavaScript]
- Math.SQRT1_2 constant [JavaScript]
- SQRT2 constant [JavaScript]
- square root constants [JavaScript]
- Math.PI constant [JavaScript]
- math constants [JavaScript]
- LN10 constant [JavaScript]
- Math.LN2 constant [JavaScript]
- Math.LN10 constant [JavaScript]
ms.assetid: 8a674046-cb99-4103-92be-83697fba6344
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9942abb69af416cd4cd7f092dc9f1478e0bc3a69
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="math-constants-javascript"></a>Matematické konstanty (JavaScript)
Matematické konstanty vrátit konstantní hodnoty, které jsou vlastnosti `Math` objektu.  
  
## <a name="math-object-constants"></a>Konstanty objektu Math  
 Následující tabulka uvádí konstantní hodnoty, které jsou vlastnosti [Math – objekt](../../javascript/reference/math-object-javascript.md).  
  
|Konstanta|Popis|Přibližná hodnota|  
|--------------|-----------------|-----------------------|  
|`Math.E`|Matematické konstanty e. Toto je Eulerova na číslo, je základ přirozeného logaritmu.|2.718|  
|`Math.LN2`|Přirozený logaritmus 2.|0.693|  
|`Math.LN10`|Přirozený logaritmus 10.|2.302|  
|`Math.LOG2E`|Základní 2 logaritmu e.|1.443|  
|`Math.LOG10E`|Základu 10 logaritmu e.|0.434|  
|`Math.PI`|Pí. Toto je poměr obvodu kruh k jeho průměru.|3.14159|  
|`Math.SQRT1_2`|Druhou odmocninu čísla 0,5 nebo, ekvivalentně, jeden dělený druhou odmocninu čísla 2.|0.707|  
|`Math.SQRT2`|Druhou odmocninu čísla 2.|1.414|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak používat `Math.PI` konstantní.  
  
```JavaScript  
var radius = 3;  
var area = Math.PI * radius * radius;  
document.write(area);  
  
// Output: 28.274333882308138  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [Math – objekt](../../javascript/reference/math-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Číselné konstanty](../../javascript/reference/number-constants-javascript.md)   
 [Konstanty jazyka JavaScript](../../javascript/reference/javascript-constants.md)