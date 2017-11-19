---
title: "sort – metoda (pole) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: sort
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: Sort method
ms.assetid: 9bd8b54a-c838-4806-85c8-62eebe6bc48c
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2d098b47591ca7bbb4e3e8da5e5c14f8c0e9b255
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="sort-method-array-javascript"></a>sort – metoda (Pole) (JavaScript)
Řazení `Array`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
arrayobj.sort(sortFunction)   
```  
  
## <a name="parameters"></a>Parametry  
 `arrayObj`  
 Požadováno. Všechny `Array` objektu.  
  
 `sortFunction`  
 Volitelné. Název funkce použitá k určení pořadí elementů. Pokud tento parametr vynechán, jsou elementy seřazené ve vzestupném pořadí znaků ASCII.  
  
## <a name="return-value"></a>Návratová hodnota  
 Seřazené pole.  
  
## <a name="remarks"></a>Poznámky  
 `sort` Metoda řazení `Array` objekt přímo; ne nové `Array` objekt se vytvoří během provádění.  
  
 Pokud zadáte funkce při `sortFunction` argument, musí vracet jednu z následujících hodnot:  
  
-   Záporná, pokud je první argument předaný menší než druhý argument.  
  
-   Nula, pokud odpovídají dva argumenty.  
  
-   Kladná hodnota, pokud první argument je větší než druhý argument.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `sort` metoda.  
  
```JavaScript  
var a = new Array(4, 11, 2, 10, 3, 1);  
  
var b = a.sort();  
document.write(b);  
document.write("<br/>");  
  
// This is ASCII character order.  
// Output: 1,10,11,2,3,4)  
  
// Sort the array elements with a function that compares array elements.  
b = a.sort(CompareForSort);  
document.write(b);  
document.write("<br/>");  
// Output: 1,2,3,4,10,11.  
  
// Sorts array elements in ascending order numerically.  
function CompareForSort(first, second)  
{  
    if (first == second)  
        return 0;  
    if (first < second)  
        return -1;  
    else  
        return 1;   
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]