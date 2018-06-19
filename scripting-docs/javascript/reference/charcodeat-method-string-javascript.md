---
title: charCodeAt – metoda (String) (JavaScript) | Microsoft Docs
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
- charCodeAt
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- charCodeAt method
ms.assetid: 5b0290a7-ee4d-4738-a909-c02ef64a2f1a
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8e7b8e62dfd29aa42d9816d0c5e27cc90440751a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789051"
---
# <a name="charcodeat-method-string-javascript"></a>charCodeAt – metoda (String) (JavaScript)
Vrátí hodnotu Unicode znaku v zadaném umístění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
strObj. charCodeAt(index)  
```  
  
## <a name="parameters"></a>Parametry  
 `strObj`  
 Požadováno. Všechny `String` objekt nebo řetězcový literál.  
  
 `index`  
 Požadováno. Index založený na nule požadované znaku. Pokud neexistuje žádné znak v zadaném indexu `NaN` je vrácen.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `charCodeAt` metoda.  
  
```JavaScript  
var str = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";   
document.write(str.charCodeAt(str.length - 1));  
  
// Output: 90   
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [String.fromCharCode – funkce](../../javascript/reference/string-fromcharcode-function-javascript.md)