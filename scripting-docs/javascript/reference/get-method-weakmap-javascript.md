---
title: Get – metoda (WeakMap) (JavaScript) | Microsoft Docs
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
ms.assetid: d922c55d-486d-4feb-aedc-1f4867c417d2
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 29decb7e6a050188b75639eb7cf4f27494b31da2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790455"
---
# <a name="get-method-weakmap-javascript"></a>get – metoda (WeakMap) (JavaScript)
Vrátí zadaný element z `WeakMap` objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
weakmapObj.get(key)  
```  
  
#### <a name="parameters"></a>Parametry  
 `weakmapObj`  
 Požadováno. A `WeakMap` objektu.  
  
 `key`  
 Požadováno. Klíč elementu v `WeakMap`.  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 Vrátí objekt přidružené ke klíči. Pokud `WeakMap` neobsahuje klíče, vrátí tato metoda `undefined` hodnotu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak načíst členy z `WeakMap` objektu.  
  
```JavaScript  
var dog = {  
    breed: "yorkie"  
}  
  
var cat = {  
    breed: "burmese"  
}  
  
var wm = new WeakMap();  
wm.set(dog, "fido");  
wm.set(cat, "pepper");  
  
document.write(wm.get(dog) + ": ");  
document.write(dog.breed);  
document.write("<br />");  
document.write(wm.get(cat) + ": ");  
document.write(cat.breed);  
  
// Output:  
// fido: yorkie  
// pepper: burmese  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]