---
title: constructor – vlastnost (chyba) | Microsoft Docs
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
ms.assetid: 18aea278-2bd5-457b-83a5-d8d8f1226e0c
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f1ade0ab1ba771b2ff9dfb7051b2983b3da77ed4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790314"
---
# <a name="constructor-property-error"></a>constructor – vlastnost (Chyba)
Určuje funkce, která vytvoří chybu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
error.constructor  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `error` je název objektu k chybě.  
  
 `constructor` Vlastnost je členem prototyp každý objekt, který má prototypu. `constructor` Vlastnost obsahuje odkaz na funkci, která vytvoří instanci daný objekt.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití vlastnosti konstruktor.  
  
```JavaScript  
var x = new Error("This is an error");  
  
if (x.constructor == Error)  
    document.write("Object is an error.");  
  
// Output:  
// Object is an error.  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]