---
title: sort – metoda (pole) (JavaScript) | Microsoft Docs
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
- sort
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Sort method
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0462e60e623b99af458beb61eb7ef4215fe8ef41
ms.sourcegitcommit: b01406355e3b97547b7cbf8ce3960f101b165cec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/05/2018
ms.locfileid: "28987812"
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
  
 `sortFunction`přebírá dva argumenty a musí vrátit jednu z následujících hodnot:  
  
-   Záporná (je menší než 0.) Pokud první argument předaný je menší než druhý argument.  První argument je řazen dolní index.
  
-   Nula (0), pokud odpovídají dva argumenty.  Dva argumenty jsou seřazeny s ohledem na další prvky v poli, nikoli však s ohledem na sebe navzájem.
  
-   Kladnou hodnotu (větší než 0.) Pokud první argument je větší než druhý argument.  Druhý argument je řazen dolní index.
  
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