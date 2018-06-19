---
title: foreach – metoda (Set) (JavaScript) | Microsoft Docs
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
ms.assetid: 813bff6e-6098-4260-ab6e-b0d2da6be94d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b89c56b54fd74c25c43a84f2f0fd68922aa9f637
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790536"
---
# <a name="foreach-method-set-javascript"></a>forEach – metoda (Set) (JavaScript)
Provede zadanou akci pro každý prvek v sadě.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
setObj.forEach(callbackfn[, thisArg])  
```  
  
#### <a name="parameters"></a>Parametry  
 `setObj`  
 Požadováno. A `Set` objektu.  
  
 `callbackfn`  
 Požadováno. `callbackfn`přijme až tři argumenty. Funkce, `forEach` volá jednou pro každý prvek v sadě.  
  
 `thisArg`  
 Volitelné. Objekt, `this` – klíčové slovo najdete v `callbackfn` funkce. Pokud `thisArg` je vynechán, `undefined` slouží jako `this` hodnotu.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud `callbackfn` argument není objekt funkce `TypeError` je vyvolána výjimka.  
  
## <a name="remarks"></a>Poznámky  
 Syntaxe funkce zpětného volání je následující:  
  
 `function callbackfn(value, key, setObj)`  
  
 Funkce zpětného volání je možné deklarovat pomocí až tři parametry, jak je znázorněno v následující tabulce.  
  
|Argument zpětného volání|Definice|  
|-----------------------|----------------|  
|`value`|Hodnota, obsažené v sadě.|  
|`key`|Hodnota, obsažené v sadě. Sada nemá žádné klíče, takže tato hodnota je stejná jako `value`.|  
|`setObj`|`Set` Objekt, který chcete procházet.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak používat `forEach`. `callbackfn` Argument obsahuje kód pro funkce zpětného volání.  
  
```JavaScript  
var s = new Set();  
  
s.add("scale");  
s.add(10);  
s.add("5");  
  
s.forEach(function(item, sameItem, s) {  
    document.write("Size of the set object is: " + s.size + "<br />");  
    document.write("Deleting item: " + item + "<br />");  
    s.delete(sameItem);  
});  
  
// Output:  
// Size of the set object is: 3  
// Deleting item: scale  
// Size of the set object is: 2  
// Deleting item: 10  
// Size of the set object is: 1  
// Deleting item: 5  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, že je také možné načíst členy ze sady pomocí předání jenom jeden parametr funkce zpětného volání.  
  
```JavaScript  
var s = new Set();  
s.add("Thomas Jefferson");  
s.add(1776);  
s.add("founding father");  
  
s.forEach(function (item) {  
    document.write(item.toString() + ", ");  
});  
  
// Output:  
// Thomas Jefferson, 1776, founding father,  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]