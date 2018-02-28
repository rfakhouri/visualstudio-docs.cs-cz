---
title: "Funkce – objekt (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- function
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Function object
ms.assetid: d3834767-203c-475e-848c-95c423ba15b6
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4392fd57967e6312c96af50bdff2415d0f2dcd4d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="function-object-javascript"></a>Function – objekt (JavaScript)
Vytvoří novou funkci.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
function functionName([argname1  [, ...[, argnameN]]])  
{  
   body  
}  
```  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
functionName = new Function( [argname1,  [... argnameN,]] body );  
```  
  
## <a name="parameters"></a>Parametry  
 `functionName`  
 Požadováno. Název nově vytvořený funkce  
  
 `argname1...argnameN`  
 Volitelné. Seznam argumentů, které přijímá funkce.  
  
 `body`  
 Volitelné. Řetězec, který obsahuje blok [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] být spuštěn, když je tato funkce volána.  
  
## <a name="remarks"></a>Poznámky  
 Funkce je základní datový typ v [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]. Syntaxe 1 vytvoří hodnotu funkce, která [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] převede `Function` objektu, pokud je to nezbytné. [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]Převede `Function` objekty vytvořené pomocí syntaxe 2 do funkce hodnot v době je tato funkce volána.  
  
 Syntaxe 1 je standardní způsob, jak vytvořit nové funkce v [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]. Syntaxe 2 je alternativní formě slouží k vytvoření objektů funkce explicitně.  
  
 Například deklarovat funkci, která přidá dva argumenty, které do ní předán, můžete provést v jednom ze dvou způsobů:  
  
## <a name="example-1"></a>Příklad 1  
  
```JavaScript  
function add(x, y)  
{  
   return(x + y);  
}  
```  
  
## <a name="example-2"></a>Příklad 2  
  
```  
var add = function(x, y) {  
     return(x+y);  
}  
```  
  
 V obou případech můžete pro volání funkce s řádkem kódu podobný následujícímu:  
  
```JavaScript  
add(2, 3);  
```  
  
> [!NOTE]
>  Při volání funkce, zajistěte, aby vždy zahrnovat závorkách a všechny požadované argumenty. Volání funkce bez závorek způsobí, že funkce samotné má být vrácen, namísto návratové hodnoty funkce.  
  
## <a name="properties"></a>Vlastnosti  
 [0... n vlastnosti](../../javascript/reference/0-dot-dot-dot-n-properties-arguments-javascript.md) &#124;[ arguments – vlastnost](../../javascript/reference/arguments-property-function-javascript.md) &#124; [callee – vlastnost](../../javascript/reference/callee-property-arguments-javascript.md) &#124; [caller – vlastnost](../../javascript/reference/caller-property-function-javascript.md) &#124; [constructor – vlastnost](../../javascript/reference/constructor-property-object-javascript.md) &#124; [length – vlastnost (Function)](../../javascript/reference/length-property-function-javascript.md) &#124; [prototype – vlastnost](../../javascript/reference/prototype-property-object-javascript.md)  
  
## <a name="methods"></a>Metody  
 [Apply – metoda](../../javascript/reference/apply-method-function-javascript.md) &#124; [bind – metoda](../../javascript/reference/bind-method-function-javascript.md) &#124; [volat metodu](../../javascript/reference/call-method-function-javascript.md) &#124; [toString – metoda](../../javascript/reference/tostring-method-object-javascript.md) &#124; [valueOf – metoda](../../javascript/reference/valueof-method-object-javascript.md)  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Function – příkaz](../../javascript/reference/function-statement-javascript.md)   
 [New – operátor](../../javascript/reference/new-operator-decrementjavascript.md)   
 [var – příkaz](../../javascript/reference/var-statement-javascript.md)