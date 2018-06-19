---
title: Return – příkaz (JavaScript) | Microsoft Docs
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
- return_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- terminating execution
- return statement
- function statement
- return statement, syntax
- return statement, exiting functions in script
ms.assetid: a9130d90-11fb-43f5-a819-7e5435f74c05
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c28f17bed2dfff021ea1aea268bb7a2eb3f3e58
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791307"
---
# <a name="return-statement-javascript"></a>return – příkaz (JavaScript)
Ukončí z aktuální funkce a vrátí hodnotu z této funkce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
return[(][expression][)];   
```  
  
## <a name="remarks"></a>Poznámky  
 Volitelné *výraz* argument je hodnota, která má být vrácena z funkce. Pokud tento parametr vynechán, funkce nevrací hodnotu.  
  
 Můžete použít `return` příkaz Zastavit provádění funkce a vrátí hodnotu *výraz*. Pokud *výraz* je vynechán, nebo žádný `return` spustit příkaz z v rámci funkce, výraz, který volá funkci current přiřazena hodnota není definovaná.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `return` příkaz.  
  
```JavaScript  
function myfunction(arg1, arg2){  
   var r;  
   r = arg1 * arg2;  
   return(r);  
}  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `return` příkaz vrátit funkce.  
  
```JavaScript  
function doWork() {  
    return function calculate(y) { return y + 1; };  
}  
  
var func = doWork();  
var x = func(5);  
document.write(x);  
  
// Output: 6  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Function – příkaz](../../javascript/reference/function-statement-javascript.md)