---
title: propertyIsEnumerable – metoda (Object) (JavaScript) | Microsoft Docs
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
- propertyIsEnumerable
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- propertyIsEnumerable property
ms.assetid: d90c7c2e-ea23-4710-a957-9aefbbd1f68b
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5664732db6a311586f11eb13eee4407fdf81410f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791163"
---
# <a name="propertyisenumerable-method-object-javascript"></a>propertyIsEnumerable – metoda (Object) (JavaScript)
Určuje, zda je zadaná vlastnost vyčíslitelná.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
object. propertyIsEnumerable(proName)  
```  
  
## <a name="parameters"></a>Parametry  
 `object`  
 Požadováno. Instance objektu.  
  
 `proName`  
 Požadováno. Hodnota názvu vlastnosti typu řetězec.  
  
## <a name="remarks"></a>Poznámky  
 `propertyIsEnumerable` Metoda vrátí `true` Pokud `proName` existuje v `object` a mohou být uvedené pomocí `For` smyčky. `propertyIsEnumerable` Metoda vrátí `false` Pokud `object` nemá vlastnost se zadaným názvem nebo pokud je zadaná vlastnost není vyčíslitelná. Obvykle předdefinované vlastnosti nejsou vyčíslitelná, ale jsou vždy vyčíslitelná uživatelem definované vlastnosti.  
  
 `propertyIsEnumerable` Metoda nebere v úvahu objekty v řetězu prototypu.  
  
## <a name="example"></a>Příklad  
  
```JavaScript  
var a = new Array("apple", "banana", "cactus");  
document.write(a.propertyIsEnumerable(1));  
  
// Output: true  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [prototype – vlastnost (Object)](../../javascript/reference/prototype-property-object-javascript.md)