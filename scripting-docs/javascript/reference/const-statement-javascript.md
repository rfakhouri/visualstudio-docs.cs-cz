---
title: "Const – příkaz (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: const_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- declaring variables, const statement
- const statement
ms.assetid: 3ad0840f-437f-4163-9571-86ecc5ddb987
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 68130cec4f1b1fe89d2fe3e673b28963d79aebde
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="const-statement-javascript"></a>const – příkaz (JavaScript)
Deklaruje proměnnou s rozsahem bloku s konstantní hodnotou.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
const constant1 = value1  
```  
  
#### <a name="parameters"></a>Parametry  
 `constant1`  
 Název proměnné se deklarovat.  
  
 `value1`  
 Počáteční hodnotu přiřazenou proměnné.  
  
## <a name="remarks"></a>Poznámky  
 Použití `const` příkaz deklarovat proměnnou s konstantní hodnotou, rozsah, který je omezen na blok v kterého je deklarovaná. Nelze změnit hodnotu proměnné.  
  
 Proměnná definovaná pomocí `const` musí být inicializován, když je deklarován.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `const` příkaz.  
  
```JavaScript  
var c = 10;  
{  
    const c = 2;  
   // At this point, c = 2.  
}  
// At this point, c = 10.  
  
// Additional ways to declare a variable using const.  
const name = "Thomas Jefferson";  
const answer = 42, numpages = 10;  
const myarray = new Array();  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [let – příkaz](../../javascript/reference/let-statement-javascript.md)   
 [New – operátor](../../javascript/reference/new-operator-decrementjavascript.md)   
 [Array – objekt](../../javascript/reference/array-object-javascript.md)   
 [Proměnné](../../javascript/variables-javascript.md)