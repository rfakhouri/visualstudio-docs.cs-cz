---
title: "constructor – vlastnost (WeakMap) | Microsoft Docs"
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
ms.assetid: 1e3f9333-ce75-4d32-9b14-fbe81fd73dfb
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c7340e1e5eeff9a80e231cf1aa49443adc94e72
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="constructor-property-weakmap"></a>constructor – vlastnost (WeakMap)
Určuje funkce, která vytvoří `WeakMap` objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
weakmap.constructor  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `weakmap` je název `WeakMap` objektu.  
  
 `constructor` Vlastnost je členem prototyp každý objekt, který má prototypu. To zahrnuje všechny vnitřní objekty jazyka JavaScript s výjimkou `Global` a `Math` objekty. `constructor` Vlastnost obsahuje odkaz na funkci, která vytvoří instanci daný objekt.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]