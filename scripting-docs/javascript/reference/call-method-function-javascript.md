---
title: Call – metoda (Function) (JavaScript) | Microsoft Docs
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
- call
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- call method
ms.assetid: fa356dec-48e6-4f75-8bf3-c1814a76818f
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2ef871f85459ad875a747ae79c7c054b30a82e55
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789117"
---
# <a name="call-method-function-javascript"></a>call – metoda (Function) (JavaScript)
Volá metodu objektu, nahraďte jiným objektem pro aktuální objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
call([thisObj[, arg1[, arg2[,  [, argN]]]]])  
```  
  
## <a name="parameters"></a>Parametry  
 `thisObj`  
 Volitelné. Objekt, který se má použít jako aktuální objekt.  
  
 `arg1, arg2, , argN`  
 Volitelné. Seznam argumentů, které mají být předány metodě.  
  
## <a name="remarks"></a>Poznámky  
 `call` Metoda se používá k volání metody jménem jiného objektu. Umožňuje změnit `this` objekt funkce z původního kontextu jako nový objekt určeného `thisObj`.  
  
 Pokud `thisObj` se nedodává `global` objekt se používá jako `thisObj`.  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje způsob použití `call` metoda.  
  
```JavaScript  
function callMe(arg1, arg2){  
    var s = "";  
  
    s += "this value: " + this;  
    s += "<br />";  
    for (i in callMe.arguments) {  
        s += "arguments: " + callMe.arguments[i];  
        s += "<br />";  
    }  
    return s;  
}  
  
document.write("Original function: <br/>");  
document.write(callMe(1, 2));  
document.write("<br/>");  
  
document.write("Function called with call: <br/>");  
document.write(callMe.call(3, 4, 5));  
  
// Output:   
// Original function:   
// this value: [object Window]  
// arguments: 1  
// arguments: 2  
  
// Function called with call:   
// this value: 3  
// arguments: 4  
// arguments: 5  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Function – objekt](../../javascript/reference/function-object-javascript.md)   
 [Apply – metoda (Function)](../../javascript/reference/apply-method-function-javascript.md)