---
title: constructor – vlastnost (String) | Microsoft Docs
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
ms.assetid: ef0e9c82-4651-4404-87b1-d00cad38c6f9
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7f1942073a9950a77c7e0cae759a9653318d8a18
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790326"
---
# <a name="constructor-property-string"></a>constructor – vlastnost (String)
Určuje funkce, která vytvoří řetězec.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
string.constructor  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `string` je název řetězce.  
  
 `constructor` Vlastnost je členem prototyp každý objekt, který má prototypu. To zahrnuje všechny vnitřní [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objekty s výjimkou `Global` a `Math` objekty. `constructor` Vlastnost obsahuje odkaz na funkci, která vytvoří instanci daný objekt.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití vlastnosti konstruktor.  
  
```JavaScript  
var x = new String();  
  
if (x.constructor == String)  
    document.write("Object is a String.");  
else  
    document.write("Object is not a String.");  
  
// Output:  
// Object is a String.  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]