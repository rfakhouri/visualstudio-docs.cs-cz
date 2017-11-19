---
title: Metoda slice (pole) (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: slice
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- zero-based index
- Array object
- slice method
ms.assetid: 3c122219-14de-4126-b091-809659c026d6
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a61cd331abef9d1a0d979f547f6d6f12222c1eee
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="slice-method-array-javascript"></a>slice – metoda (Pole) (JavaScript)
Vrátí část pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
arrayObj.slice(start, [end])   
```  
  
## <a name="parameters"></a>Parametry  
 `arrayObj`  
 Požadováno. `Array` Objektu.  
  
 `start`  
 Požadováno. Na začátek zadaný část `arrayObj`.  
  
 `end`  
 Volitelné. Konec zadané část `arrayObj`.  
  
## <a name="remarks"></a>Poznámky  
 `slice` Metoda vrátí `Array` objekt obsahující zadanou část `arrayObj`.  
  
 `slice` Metoda zkopíruje až do, nikoli však element indikován `end`. Pokud `start` je záporná, je považován za `length`  +  `start`, kde `length` je délka pole. Pokud `end` je záporná, je považován za `length`  +  `end` kde `length` je délka pole. Pokud `end` je vynechán, extrakce pokračuje na konec `arrayObj`. Pokud `end` dojde před `start`, žádné elementy jsou zkopírovány do nového pole.  
  
## <a name="example"></a>Příklad  
 Následující příklady ukazují, jak používat `slice` metoda. V prvním příkladu, všechny kromě poslední elementu `myArray` se zkopíruje do `newArray`. V druhém příkladu pouze poslední dva elementy `myArray` se zkopírují do `newArray`.  
  
```JavaScript  
var origArray = [3, 5, 7, 9];  
var newArray = origArray. slice(0, -1);  
document.write(origArray);  
document.write("<br/>");  
newArray = origArray. slice(-2);  
document.write(newArray);  
  
// Output:  
// 3,5,7,9  
// 7,9  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Metoda slice (řetězec)](../../javascript/reference/slice-method-string-javascript.md)   
 [String – objekt](../../javascript/reference/string-object-javascript.md)