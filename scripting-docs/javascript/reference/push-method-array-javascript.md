---
title: "push – metoda (pole) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: push
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: Push method
ms.assetid: fa6e5799-dabe-4b3d-bd1f-0afc68c77134
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ddb49f310eaff51fe9e9ba584281fdf07bc2e818
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="push-method-array-javascript"></a>push – metoda (Pole) (JavaScript)
Přidá do pole nové prvky a vrátí novou velikost pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
arrayObj.push([item1 [item2 [. . . [itemN ]]]])  
```  
  
## <a name="parameters"></a>Parametry  
 `arrayObj`  
 Požadováno. `Array` Objektu.  
  
 `item, item2,. . ., itemN`  
 Volitelné. Nové prvky `Array`.  
  
## <a name="remarks"></a>Poznámky  
 `push` a `pop` metody vám umožňují k simulaci poslední, nejprve se zásobníku.  
  
 `push` Metoda připojí elementů v pořadí, ve kterém jsou zobrazeny. Pokud jeden z argumentů pole, je přidán jako jeden prvek. Použití `concat` metoda připojení elementy ze dvou nebo více polí.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `push` metoda.  
  
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
  
// Output:  
// 9 8 7 6 5  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Metoda concat (pole)](../../javascript/reference/concat-method-array-javascript.md)   
 [POP – metoda (pole)](../../javascript/reference/pop-method-array-javascript.md)