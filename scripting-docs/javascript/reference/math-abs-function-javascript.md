---
title: "Math.Abs – funkce (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: abs
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- absolute values, calculating
- absolute values
- numeric expressions
- abs method
ms.assetid: 9af4b5b8-de77-47bb-bb59-abdde371e4c3
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5719905a7de375f1b409378f0579e3d8b25209fc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="mathabs-function-javascript"></a>Math.abs – funkce (JavaScript)
Vrátí absolutní hodnotu čísla (hodnota bez ohledu na tom, jestli je kladné a záporné). Například absolutní hodnota -5 je stejná jako absolutní hodnota 5.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Math.abs(number)  
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `number` argument je číselného výrazu, pro kterou je potřeba absolutní hodnotu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Absolutní hodnota `number` argument.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `abs` funkce.  
  
```JavaScript  
var s;  
var v1 = Math.abs(6);  
var v2 = Math.abs(-6);  
if (v1 == v2) {  
    document.write("Absolute values are the same.");  
}  
else {  
document.write("Absolute values are different.");  
}  
  
// Output: Absolute values are the same.  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [Math – objekt](../../javascript/reference/math-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Math – objekt](../../javascript/reference/math-object-javascript.md)