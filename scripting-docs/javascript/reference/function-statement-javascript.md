---
title: "Funkce – příkaz (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: function_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- new operator
- declaring functions, syntax
- function statement
- declaring functions
ms.assetid: cc9cfd43-1305-41c8-ad67-545d20f4fafe
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e5fac3647e9374a9c909a420b73b86354cac69b6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="function-statement-javascript"></a>function – příkaz (JavaScript)
Deklaruje novou funkci.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
function functionname ([arg1 [, arg2 [,...[, argN]]]]) {  
    statements  
}   
```  
  
## <a name="parameters"></a>Parametry  
 `functionname`  
 Požadováno. Název funkce.  
  
 `arg1...argN`  
 Volitelné. Volitelné, oddělených čárkami seznam argumentů funkce rozumí.  
  
 `statements`  
 Volitelné. Jeden nebo více[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] příkazy.  
  
## <a name="remarks"></a>Poznámky  
 Použít `function` příkaz deklarovat funkce pro pozdější použití. Kód, který je součástí `statements` není provést, dokud je tato funkce volána z jiného místa ve skriptu.  
  
 [Vrátit](../../javascript/reference/return-statement-javascript.md) příkaz se používá k vrácení hodnoty z funkce. Není nutné používat `return` příkaz; program bude vracet ukončení funkce. Pokud žádné `return` ve funkci, je spustit příkaz nebo, pokud `return` příkaz má žádný výraz, funkce vrátí hodnotu `undefined`.  
  
> [!NOTE]
>  Při volání funkce, nezapomeňte zahrnout závorkách a všechny požadované argumenty. Volání funkce bez závorek vrátí odkaz na tuto funkci, není výsledky této funkce.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `function` příkaz.  
  
```JavaScript  
function myfunction (arg1, arg2) {  
    var r = arg1 * arg2;  
    return(r);  
}  
```  
  
## <a name="example"></a>Příklad  
 Funkci lze přiřadit k proměnné. To je znázorněno v následujícím příkladu.  
  
```JavaScript  
function AddFive(x) {  
    return x + 5;  
}  
  
function AddTen(x) {  
    return x + 10;  
}  
  
var condition = false;  
  
var MyFunc;  
if (condition) {  
    MyFunc = AddFive;  
}  
else {  
    MyFunc = AddTen;  
}  
  
var result = MyFunc(123);  
// Output: 133  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [New – operátor](../../javascript/reference/new-operator-decrementjavascript.md)