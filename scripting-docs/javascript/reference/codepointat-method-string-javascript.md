---
title: codepointat – metoda (String) (JavaScript) | Microsoft Docs
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
ms.assetid: 7979018f-1be3-4a13-9e8f-c84c7ed35288
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0dd5ef17db177dfb1d532bfb88d1d0d77cdb7304
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788937"
---
# <a name="codepointat-method-string-javascript"></a>codePointAt – metoda (String) (JavaScript)
Vrátí bod kódu pro znak Unicode UTF-16.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
stringObj.codePointAt(pos);  
```  
  
#### <a name="parameters"></a>Parametry  
 `stringObj`  
 Požadováno. Objekt řetězce.  
  
 `pos`  
 Požadováno. Pozice znaku.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda vrátí hodnotou kódu, včetně astral kód body (body kódu s více než čtyři hexadecimální hodnoty), pro všechny znaky UTF-16.  
  
 Pokud `pos` je menší než nula (0) nebo větší než velikost řetězce, je vrácenou hodnotu `undefined`.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `codePointAt` metoda.  
  
```JavaScript  
var cp1 = "𠮷".codePointAt(0);  
var cp2 = 'abc'.codePointAt(1);  
  
if(console && console.log) {  
    console.log(cp1);  
    console.log(cp2);}  
  
// Output:  
// 0x20BB7  
// 98   
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]
