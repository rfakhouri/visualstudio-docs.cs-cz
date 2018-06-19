---
title: Get – metoda (Map) (JavaScript) | Microsoft Docs
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
ms.assetid: bebbd6bc-6e61-4674-8196-7e907798973f
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 243d5aa93289cb7a13b34567b7824d028151bad3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790443"
---
# <a name="get-method-map-javascript"></a>get – metoda (Map) (JavaScript)
Vrátí zadaný element z mapy.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
mapObj.get(key)  
```  
  
#### <a name="parameters"></a>Parametry  
 `mapObj`  
 Požadováno. A `Map` objektu.  
  
 `key`  
 Požadováno. Klíč elementu v `Map`.  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 Vrátí objekt přidružené ke klíči. Pokud `Map` neobsahuje klíče, vrátí tato metoda `undefined` hodnotu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak načíst element z `Map` objektu.  
  
```JavaScript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
  
document.write(m.get(2));  
  
// Output:  
// red  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]