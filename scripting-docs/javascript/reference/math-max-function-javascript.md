---
title: "Math.Max – funkce (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: max
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: max method
ms.assetid: f3ea1b8a-5fd0-482a-971b-b7f8e2b9b7eb
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: adf66164346f3802d92f8e0de82356df49bad5fa
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="mathmax-function-javascript"></a>Math.max – funkce (JavaScript)
Vrátí větší sadu zadaný numerických výrazů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Math.max([number1[, number2[... [, numberN]]]])   
```  
  
## <a name="remarks"></a>Poznámky  
 Volitelné `number1, number2, ..., numberN` argumenty jsou numerické výrazy k vyhodnocení.  
  
 Pokud jsou k dispozici žádné argumenty, návratová hodnota se rovná [Number.negative_infinity –](../../javascript/reference/number-constants-javascript.md). Pokud je některý argument `NaN`, vrácená hodnota je také `NaN`.  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje, jak získat větší dvou výrazů.  
  
```JavaScript  
var x = Math.max(107 - 3,  48 * 90);  
document.write(x);  
  
// Output:  
// 4320  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Math.min – funkce](../../javascript/reference/math-min-function-javascript.md)