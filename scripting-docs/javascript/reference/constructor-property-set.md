---
title: constructor – vlastnost (Set) | Microsoft Docs
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
ms.assetid: f350b7eb-8994-40bf-9011-f8b20fcef34f
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ea9af6d60c2ae8bc8a383c4cebbf0955e183895e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790371"
---
# <a name="constructor-property-set"></a>constructor – vlastnost (Set)
Určuje funkce, která vytvoří sadu.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
set.constructor  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `set` je název sady.  
  
 `constructor` Vlastnost je členem prototyp každý objekt, který má prototypu. To zahrnuje všechny vnitřní objekty jazyka JavaScript s výjimkou `Global` a `Math` objekty. `constructor` Vlastnost obsahuje odkaz na funkci, která vytvoří instanci daný objekt.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]