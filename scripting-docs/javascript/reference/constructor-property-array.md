---
title: constructor – vlastnost (pole) | Microsoft Docs
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
ms.assetid: b78d517b-cb56-4866-b30f-ef8121a27843
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ca779a2fa2356c1f3e1ca816f16531c0930459a4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789045"
---
# <a name="constructor-property-array"></a>constructor – vlastnost (Pole)
Určuje funkci, která vytvoří pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
array.constructor  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `array` je název pole.  
  
 `constructor` Vlastnost je členem prototyp každý objekt, který má prototypu. To zahrnuje všechny vnitřní [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objekty s výjimkou `Global` a `Math` objekty. `constructor` Vlastnost obsahuje odkaz na funkci, která vytvoří instanci daný objekt.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití vlastnosti konstruktor.  
  
```JavaScript  
var x = new Array();  
  
if (x.constructor == Array)  
    document.write("Object is an Array.");  
else  
    document.write("Object is not an Array.");  
  
// Output:  
// Object is an Array.  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]