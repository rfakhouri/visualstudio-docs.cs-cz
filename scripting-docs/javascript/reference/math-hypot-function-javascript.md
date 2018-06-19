---
title: Math.hypot – funkce (JavaScript) | Microsoft Docs
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
ms.assetid: 31488f5a-2230-4114-911e-b6d854c7b0a0
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a66c0b082356b8dde3f51f739c130378d694f3b4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790986"
---
# <a name="mathhypot-function-javascript"></a>Math.hypot – funkce (JavaScript)
Vrátí druhou odmocninu čísla součet kvadratických argumenty.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Math.hypot ( value1[, value2[, ...values] );  
```  
  
#### <a name="parameters"></a>Parametry  
 `value1`  
 Požadováno. První číslo.  
  
 `value2`  
 Volitelné. Druhé číslo.  
  
 `values`  
 Volitelné. Jeden nebo více čísla.  
  
## <a name="remarks"></a>Poznámky  
 Je-li některý argument NaN, vrátí funkce NaN. Pokud jsou poskytovat žádné argumenty, funkce vrátí hodnotu 0.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje příklad použití `Math.hypot` funkce.  
  
```JavaScript  
Math.hypot(3, 4);  
// Returns 5  
  
Math.hypot(3, "4");  
// Returns 5  
  
Math.hypot(3, "four");  
// Returns NaN   
  
Math.hypot(3, 4, 10);  
// Returns 11.180339887498949  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]