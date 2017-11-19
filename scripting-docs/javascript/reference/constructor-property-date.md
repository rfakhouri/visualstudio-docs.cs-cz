---
title: "constructor – vlastnost (Date) | Microsoft Docs"
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
ms.assetid: 5db153a1-788b-4a61-bfc8-2d2ec38f36ea
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 798064117e17ee5b2988396de3c6545917373b10
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="constructor-property-date"></a>constructor – vlastnost (Date)
Určuje funkce, která vytvoří datum.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
date.constructor  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `date` je název objektu datum.  
  
 `constructor` Vlastnost je členem prototyp každý objekt, který má prototypu. `constructor` Vlastnost obsahuje odkaz na funkci, která vytvoří instanci daný objekt.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití vlastnosti konstruktor.  
  
```JavaScript  
var x = new Date("Hi");  
  
if (x.constructor == Date)  
    document.write("Object is a date.");  
  
// Output:  
// Object is a date.  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]