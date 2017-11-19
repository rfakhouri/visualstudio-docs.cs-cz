---
title: "constructor – vlastnost (Number) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: a348fe53-1b4a-42f5-964b-53d57342c906
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 72679f55aef9b0ac8dc01794c7460dbd8cf0bdf8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="constructor-property-number"></a>constructor – vlastnost (Number)
Určuje funkce, která vytvoří číslo.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
number.constructor  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `number` je název řetězce.  
  
 `constructor` Vlastnost je členem prototyp každý objekt, který má prototypu. To zahrnuje všechny vnitřní [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objekty s výjimkou `Global` a `Math` objekty. `constructor` Vlastnost obsahuje odkaz na funkci, která vytvoří instanci daný objekt.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití vlastnosti konstruktor.  
  
```JavaScript  
var num = new Number();  
  
if (num.constructor == Number)  
    document.write("Object is a Number.");  
else  
    document.write("Object is not a Number.");  
  
// Output:  
// Object is a Number.  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]