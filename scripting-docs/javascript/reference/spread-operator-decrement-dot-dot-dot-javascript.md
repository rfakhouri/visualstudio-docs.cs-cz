---
title: Spread – operátor (...) (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 10263a4c-bd27-4d87-9917-fb4b6bf373db
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a07d480360441906c445faa196f6d7771f97d75d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791577"
---
# <a name="spread-operator--javascript"></a>Spread – operátor (...) (JavaScript)
Umožňuje částí pole literálu inicializovat z iterable výrazu (například jiné pole literálu) nebo umožňuje výraz, který se rozšířit tak, aby více argumentů (ve volání funkce).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
var array = [[arg0ToN ,] ...iterable [, arg0ToN]]  
func([args ,] ...iterable [, args | ...iterable])  
  
```  
  
## <a name="parameters"></a>Parametry  
 `iterable`  
 Požadováno. Objekt iterable.  
  
 `arg0ToN`  
 Volitelné. Jeden či více elementů pole literálu.  
  
 `args`  
 Volitelné. Jeden nebo více argumentů funkce.  
  
## <a name="remarks"></a>Poznámky  
 Další informace o iterátory najdete v tématu [iterátory a generátory](../../javascript/advanced/iterators-and-generators-javascript.md). Další informace o použití operátoru šíření jako parametr rest, najdete v části [funkce](../../javascript/functions-javascript.md).  
  
## <a name="example"></a>Příklad  
 V tomto příkladu následující kód použití operátoru šíření je rozdíl od aktualizovaného použití `concat` metoda.  
  
```JavaScript  
var a, b, c, d, e;  
a = [1,2,3];  
b = "dog";  
c = [42, "cat"];  
  
// Using the concat method.  
d = a.concat(b, c);  
  
// Using the spread operator.  
e = [...a, b, ...c];  
  
console.log(d);  
console.log(e);  
  
// Output:  
// 1, 2, 3, "dog", 42, "cat"  
// 1, 2, 3, "dog", 42, "cat"  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak chcete použít operátor šíření ve volání funkce. V tomto příkladu jsou dvě pole literály předaný funkci pomocí operátoru šíření a pole jsou rozšířit tak, aby více argumentů.  
  
```JavaScript  
function f(a, b, c, x, y, z) {  
  return a + b + c + x + y + z;  
}  
  
var args = [1, 2, 3];  
console.log(f(...args, 4, ...[5, 6]));  
  
// Output:  
// 21  
  
```  
  
## <a name="example"></a>Příklad  
 S šíření operátory, můžete zjednodušit kód, který dříve vyžadovaly použití `apply`.  
  
```JavaScript  
function f(x, y, z) {  
    return x + y + z;  
}  
  
var args = [1, 2, 3];  
  
// Old method  
f.apply(this, args);  
// New method  
f(...args);  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)