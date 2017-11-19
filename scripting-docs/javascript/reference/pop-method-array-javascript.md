---
title: "POP – metoda (pole) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: pop
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: Pop method
ms.assetid: 4fae7f98-29f1-4041-ba43-601f2e5145ec
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f7635ddcc1b3d336f5e3de66e62714bd93a06158
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="pop-method-array-javascript"></a>pop – metoda (Pole) (JavaScript)
Odstraní poslední prvek z pole a vrátí jej.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
arrayObj.pop( )  
```  
  
## <a name="remarks"></a>Poznámky  
 [Nabízené](../../javascript/reference/push-method-array-javascript.md) a `pop` metody umožňují simulovat zásobníku, která využívá princip poslední in, out (LIFO) k uložení dat nejprve.  
  
 Požadované `arrayObj` odkaz je `Array` objektu.  
  
 Pokud je pole prázdné, `undefined` je vrácen.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `pop` metoda.  
  
```JavaScript  
var number;  
var my_array = new Array();  
  
my_array.push (5, 6, 7);  
my_array.push (8, 9);  
  
number = my_array.pop();  
while (number != undefined)  
   {  
   document.write (number + " ");  
   number = my_array.pop();  
   }  
  
// Output: 9 8 7 6 5  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [push – metoda (pole)](../../javascript/reference/push-method-array-javascript.md)