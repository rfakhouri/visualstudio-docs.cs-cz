---
title: Math.min – funkce (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- min
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- min method
ms.assetid: a1d7dd85-27ef-45cd-aa2a-f8e80f0b2898
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bb496cff65db11cf6c99d6a6e687f39e20ea857c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791232"
---
# <a name="mathmin-function-javascript"></a>Math.min – funkce (JavaScript)
Vrátí menší sadu numerických výrazů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Math.min([number1[, number2[... [,numberN]]]])  
```  
  
## <a name="remarks"></a>Poznámky  
 Volitelné `number1, number2, ..., numberN` argumenty jsou numerické výrazy k vyhodnocení.  
  
 Pokud jsou k dispozici žádné argumenty, návratová hodnota se rovná [Number.positive_infinity –](../../javascript/reference/number-constants-javascript.md). Pokud je některý argument `NaN`, vrácená hodnota je také `NaN`.  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje, jak získat menší ze dvou výrazů.  
  
```JavaScript  
var x = Math.min(107 - 3, 48 * 90);  
document.write(x);  
  
// Output:  
// 104  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Math.Max – funkce](../../javascript/reference/math-max-function-javascript.md)