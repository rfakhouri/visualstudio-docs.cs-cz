---
title: "let – příkaz (JavaScript) | Microsoft Docs"
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
- let_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- let statement
- declaring variables, let statement
ms.assetid: c7e4f8a9-8f54-47b6-aed2-956959c1ecfd
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c447a1bf0c430771ff146965a592f7e160e2055b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="let-statement-javascript"></a>let – příkaz (JavaScript)
Deklaruje proměnnou s rozsahem bloku.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
let variable1 = value1  
```  
  
#### <a name="parameters"></a>Parametry  
 `variable1`  
 Název proměnné se deklarovat.  
  
 `value1`  
 Počáteční hodnotu přiřazenou proměnné.  
  
## <a name="remarks"></a>Poznámky  
 Použití `let` příkaz deklarovat proměnnou rozsahu, který je omezen na blok v kterého je deklarovaná. Můžete přiřadit hodnoty proměnných, když je deklarujete nebo později ve vašem skriptu.  
  
 Proměnná definovaná pomocí `let` nelze použít před jeho deklaraci nebo chybu způsobí.  
  
 Pokud není inicializovat vaše proměnná v `let` příkaz, je automaticky přiřazen [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] hodnotu `undefined`.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `let` příkaz.  
  
```JavaScript  
var  l = 10;  
{  
    let l = 2;  
   // At this point, l = 2.  
}  
// At this point, l = 10.  
  
// Additional ways to declare a variable using let.  
let index;  
let name = "Thomas Jefferson";  
let answer = 42, counter, numpages = 10;  
let myarray = new Array();  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Const – příkaz](../../javascript/reference/const-statement-javascript.md)   
 [New – operátor](../../javascript/reference/new-operator-decrementjavascript.md)   
 [Array – objekt](../../javascript/reference/array-object-javascript.md)   
 [Proměnné](../../javascript/variables-javascript.md)