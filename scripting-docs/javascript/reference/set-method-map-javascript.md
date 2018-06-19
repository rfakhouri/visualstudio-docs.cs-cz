---
title: set – metoda (Map) (JavaScript) | Microsoft Docs
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
ms.assetid: 31ee71a0-b09d-442a-9e02-825accf94ffa
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a84a5b2714fde55fba03d581faa851d7245e001
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791337"
---
# <a name="set-method-map-javascript"></a>set – metoda (Map) (JavaScript)
Přidá nového elementu mapy.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
mapObj.set(key, value)  
```  
  
#### <a name="parameters"></a>Parametry  
 `mapObj`  
 Požadováno. A `Map` objektu.  
  
 `key`  
 Požadováno. Klíč pro nového elementu.  
  
 `value`  
 Požadováno. Hodnota elementu, který chcete přidat.  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 Vrátí `Map` objekt, který obsahuje nový pár klíč/hodnota.  
  
## <a name="remarks"></a>Poznámky  
 Pokud přidáte do kolekce pomocí existujícího klíče hodnotu, nová hodnota nahradí původní hodnoty.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak přidávat členy do `Map` a potom je znovu načíst.  
  
```JavaScript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
  
m.forEach(function (item) {  
    document.write(item.toString() + "<br />");  
});  
  
// Output:  
// black  
// red  
// 2  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]