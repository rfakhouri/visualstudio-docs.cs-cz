---
title: "Object.getownpropertysymbols – funkce (JavaScript) | Microsoft Docs"
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
ms.assetid: 68dd69b9-5a33-44c2-ba5f-21a4ae6c0879
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2bcddba77305e30e4c5ae13f6b1fc5c9385b7108
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="objectgetownpropertysymbols-function-javascript"></a>Object.getOwnPropertySymbols – funkce (JavaScript)
Vrátí vlastní symbol vlastnosti objektu. Vlastní symbol vlastnosti objektu jsou ty, které jsou definovány přímo na tento objekt a nedědí od objektu prototypu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Object.getOwnPropertySymbols(object);  
```  
  
#### <a name="parameters"></a>Parametry  
 `object`  
 Požadováno. Objekt, který obsahuje vlastní symboly.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pole, které obsahuje vlastní symboly objektu.  
  
## <a name="remarks"></a>Poznámky  
 Budete muset použít `Object.getOwnPropertySymbols` získat symbol vlastnosti objektu. `Object.getOwnPropertyNames`nevrátí vlastnosti symbolu.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak získat symbol vlastnosti objektu.  
  
```JavaScript  
var obj = {};  
var key = Symbol('description');  
  
obj[key] = 'data';  
  
var symbols = Object.getOwnPropertySymbols(obj);  
  
console.log(s[0].toString());  
  
// Output:  
// undefined  
// Symbol(description)  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]