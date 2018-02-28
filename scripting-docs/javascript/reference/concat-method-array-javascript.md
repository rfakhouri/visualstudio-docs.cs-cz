---
title: Metoda concat (pole) (JavaScript) | Microsoft Docs
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
- concat
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- concat method (array)
- Concat method
ms.assetid: bc2b4a6a-209e-4d59-8c24-59db01d53b1e
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 19f3a216a36f9ad8c422036476e46b89b6ee488c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="concat-method-array-javascript"></a>concat – metoda (Pole) (JavaScript)
Kombinací dvou nebo více polí.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
array1.concat([item1[, item2[, . . . [, itemN]]]])   
```  
  
## <a name="parameters"></a>Parametry  
 `array1`  
 Požadováno. `Array` Objektu, na kterém jsou zřetězeny jiné pole.  
  
 `item1,. . ., itemN`  
 Volitelné. Další položky, které chcete přidat na konec `array1`.  
  
## <a name="remarks"></a>Poznámky  
 `concat` Metoda vrátí `Array` objekt obsahující zřetězení `array1` a všechny zadané položky.  
  
 Položky, které chcete přidat (*item1 itemN*) do pole jsou přidány, v pořadí, počínaje z první položky v seznamu. Pokud některá z položek pole, její obsah jsou přidány na konec `array1`. Pokud je položka jakoukoli jinou hodnotu než pole, se přidá na konec pole jako element jednoho pole.  
  
 Elementy pole zdroje se zkopírují do výsledné pole následujícím způsobem:  
  
-   Pokud je objekt zkopírovali z libovolného pole, je zřetězen do nové pole, odkaz na objekt dál tak, aby odkazoval na stejný objekt. Ke změně v nové pole nebo pole původní způsobí změnu na druhý.  
  
-   Pokud přidáte nové pole hodnotu číslo nebo řetězec, se zkopíruje pouze hodnotu. Změna hodnoty v jedno pole nemá vliv na hodnotu v druhém.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `concat` metoda při použití s pole:  
  
```JavaScript  
var a, b, c, d;  
a = new Array(1,2,3);  
b = "dog";  
c = new Array(42, "cat");  
d = a.concat(b, c);  
document.write(d);  
  
//Output:   
1, 2, 3, "dog", 42, "cat"  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Metoda concat (řetězec)](../../javascript/reference/concat-method-string-javascript.md)   
 [JOIN – metoda (pole)](../../javascript/reference/join-method-array-javascript.md)