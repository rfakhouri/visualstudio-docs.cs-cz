---
title: "splice – metoda (pole) (JavaScript) | Microsoft Docs"
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
- splice
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- splice method
ms.assetid: 85fdfb13-e3d9-4c89-b524-3ccee7001c93
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0d56a22244f76f5ce7221c276629907811733d51
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="splice-method-array-javascript"></a>splice – metoda (Pole) (JavaScript)
Odstraní prvky z pole, v případě potřeby vloží na jejich místo nové prvky a vrátí odstraněné prvky.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
arrayObj.splice(start, deleteCount, [item1[, item2[, . . . [,itemN]]]])  
```  
  
## <a name="parameters"></a>Parametry  
 `arrayObj`  
 Požadováno. `Array` Objektu.  
  
 `start`  
 Požadováno. Umístění, počítáno od nuly v poli, ze kterého má začít odebírání elementů.  
  
 `deleteCount`  
 Požadováno. Počet elementů k odebrání.  
  
 `item1, item2,. . ., itemN`  
 Volitelné. Elementy pro vložení do pole místo odstraněné elementy.  
  
## <a name="remarks"></a>Poznámky  
 `splice` Metoda upraví `arrayObj` odebráním zadaný počet elementů od pozice `start` a vkládání nových elementů. Odstraněné elementy se vrátí jako nový `Array` objektu.  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje způsob použití `splice` metoda.  
  
```JavaScript  
var arr = new Array("4", "11", "2", "10", "3", "1");  
arr.splice(2, 2, "21", "31");  
document.write(arr);  
  
// Output: 4,11,21,31,3,1  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Metoda slice (pole)](../../javascript/reference/slice-method-array-javascript.md)