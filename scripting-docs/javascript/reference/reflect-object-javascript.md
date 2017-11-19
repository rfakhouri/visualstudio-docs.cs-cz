---
title: "Reflect – objekt (JavaScript) | Microsoft Docs"
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
ms.assetid: 1df74f34-2eb4-42f1-a930-b943c86daa0e
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3574c54ee7ff69f56951cd7f4c9a93cac5275fc1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="reflect-object-javascript"></a>Reflect – objekt (JavaScript)
Poskytuje metody pro použití při operacích, které jsou zachytit.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Reflect.[method]  
```  
  
#### <a name="parameters"></a>Parametry  
 `method`  
 Požadováno. Název jedné z metod `Reflect` objektu.  
  
## <a name="remarks"></a>Poznámky  
 Objekt zrcadlení nelze vytvořit instanci s `new` operátor.  
  
 Podle metody se často používají s [proxy](../../javascript/reference/proxy-object-javascript.md) vzhledem k tomu, že umožňují vám delegovat na výchozí chování bez implementace výchozí chování v kódu.  
  
 Odráží poskytuje statické metody se stejným názvem jako každý proxy depeše. Popisy v tabulce nejsou vyčerpávající.  
  
|Metoda|Popis|  
|------------|-----------------|  
|`Reflect.apply(target, thisArg, args)`|Podobně jako [použít](../../javascript/reference/apply-method-function-javascript.md) metodu objektu funkce.|  
|`Reflect.construct(target, args)`|Ekvivalentní pro funkci `new` operátor.|  
|`Reflect.defineProperty(target, propertyName, descriptor)`|Podobně jako [Object.defineproperty –](../../javascript/reference/object-defineproperty-function-javascript.md). Vrátí logickou hodnotu udávající, zda bylo volání úspěšné.|  
|`Reflect.deleteProperty(target, propertyName)`|Podobně jako `delete` příkaz. Vrátí logickou hodnotu udávající, zda bylo volání úspěšné.|  
|`Reflect.enumerate(target)`|Podobně jako [for... v](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md) příkaz [Object.getownpropertysymbols –](../../javascript/reference/object-getownpropertysymbols-function-javascript.md), [Object.Keys –](../../javascript/reference/object-keys-function-javascript.md) funkce, a [JSON.stringify](../../javascript/reference/json-stringify-function-javascript.md).|  
|`Reflect.get(target, propertyName, receiver)`|Ekvivalentní pro všechny funkce [getter](../../javascript/creating-objects-javascript.md) vlastnosti.|  
|`Reflect.getOwnPropertyDescriptor(target, propertyName)`|Podobně jako [Object.getownpropertydescriptor –](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md). Vrátí logickou hodnotu udávající, zda bylo volání úspěšné.|  
|`Reflect.getPrototypeOf(target)`|Podobně jako [Object.getprototypeof –](../../javascript/reference/object-getprototypeof-function-javascript.md).|  
|`Reflect.has(target, propertyName)`|Podobně jako `in` operátor, [hasOwnProperty – metoda (Object)](../../javascript/reference/hasownproperty-method-object-javascript.md)a jiné metody. Vrátí logickou hodnotu udávající, zda bylo volání úspěšné.|  
|`Reflect.isExtensible(target)`|Podobně jako [Object.isextensible –](../../javascript/reference/object-isextensible-function-javascript.md).|  
|`Reflect.ownKeys(target)`|Podobně jako [Object.getownpropertynames –](../../javascript/reference/object-getownpropertynames-function-javascript.md).|  
|`Reflect.preventExtensions(target)`|Podobně jako [Object.preventextensions –](../../javascript/reference/object-preventextensions-function-javascript.md). Vrátí logickou hodnotu udávající, zda bylo volání úspěšné.|  
|`Reflect.set(target, propertyName, value, receiver)`|Podobně jako pomocí kteréhokoli [setter](../../javascript/creating-objects-javascript.md) vlastnost. Vrátí logickou hodnotu udávající, zda bylo volání úspěšné.|  
|`Reflect.setPrototypeOf(target, prototype)`|Podobně jako [Object.setprototypeof –](../../javascript/reference/object-setprototypeof-function-javascript.md). Vrátí logickou hodnotu udávající, zda bylo volání úspěšné.|  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak používat `Reflect.get` zápis proxy server, že bloky získat operace pro vlastnosti, které začínají podtržítkem.  
  
```JavaScript  
var p = new Proxy({}, {  
    get(k, t, r) {  
        // return undefined if key begins with underscore  
        if(k[0] === '_') return undefined;  
  
       // otherwise do default behavior  
       return Reflect.get(k, t, r);  
    }  
});  
  
p._foo = 1;  
console.log(p._foo);  
  
p.foo = 1;  
console.log(p.foo);  
  
// Output:  
// undefined  
// 1  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]