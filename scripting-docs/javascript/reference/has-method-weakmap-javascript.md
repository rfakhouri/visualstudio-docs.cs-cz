---
title: has – metoda (WeakMap) (JavaScript) | Microsoft Docs
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
ms.assetid: 12bedca1-bde7-413a-a4e2-06c03559044f
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e9a1706a1b96b5273ec280c4cef2be47a3bc6e17
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790515"
---
# <a name="has-method-weakmap-javascript"></a>has – metoda (WeakMap) (JavaScript)
Vrátí `true` Pokud `WeakMap` objekt obsahuje zadaný element.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
weakmapObj.has(key)  
```  
  
#### <a name="parameters"></a>Parametry  
 `weakmapObj`  
 Požadováno. A `WeakMap` objektu.  
  
 `key`  
 Požadováno. Klíč elementu, který chcete otestovat.  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 `true`Pokud `WeakMap` obsahuje zadaný klíč.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak přidat člena do `WeakMap` a pak použijte `has` zkontrolujte, zda je k dispozici.  
  
```JavaScript  
var dog = {  
    breed: "yorkie"  
}  
  
var wm = new WeakMap();  
wm.set(dog, "fido");  
  
document.write(wm.has(dog));  
  
// Output:  
// true  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]