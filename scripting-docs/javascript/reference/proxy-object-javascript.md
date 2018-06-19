---
title: Proxy – objekt (JavaScript) | Microsoft Docs
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
ms.assetid: 2b89abee-04fa-47e6-9676-980016cff5f8
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4ee75310f1d976e0a0896b1be34a80c594cdd054
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/15/2018
ms.locfileid: "29899594"
---
# <a name="proxy-object-javascript"></a>Proxy – objekt (JavaScript)
Umožňuje vlastní chování pro objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
proxyObj = new Proxy(target, handler)  
```  
  
#### <a name="parameters"></a>Parametry  
 `target`  
 Požadováno. Objekt nebo funkce, která se má Virtualizovat proxy serveru.  
  
 `handler`  
 Požadováno. Objekt s metody (depeše), které implementují vlastní chování.  
  
## <a name="remarks"></a>Poznámky  
 A `Proxy` objekt se používá k zachycení interní operace nízké úrovně, na jiný objekt. Objekty proxy lze použít pro zachycení, objekt virtualizace, protokolování nebo profilace a další účely.  
  
 Pokud depeše pro konkrétní operaci nebyl definován v obslužná rutina pro proxy server, operace se předají do cíle.  
  
 Objekt obslužné rutiny definuje následující metody (depeše), které implementují vlastní chování. Příklady zde nejsou vyčerpávající. Pro podporu podmíněného výchozí chování v metodě obslužné rutiny, použít metody [odráží objekt](../../javascript/reference/reflect-object-javascript.md).  
  
|Syntaxe obslužné rutiny (depeše) – metoda|Příklady využití|  
|------------------------------------|-----------------------|  
|`apply: function(target, thisArg, args)`|Depeše volání funkce.|  
|`construct: function(target, args)`|Depeše pro konstruktor.|  
|`defineProperty: function(target, propertyName, descriptor)`|K zachycení [Object.defineproperty – funkce](../../javascript/reference/object-defineproperty-function-javascript.md).|  
|`deleteProperty: function(target, propertyName)`|K zachycení `delete` příkaz.|  
|`enumerate: function(target)`|K zachycení [for... v](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md) příkaz [Object.getownpropertysymbols –](../../javascript/reference/object-getownpropertysymbols-function-javascript.md), [Object.Keys –](../../javascript/reference/object-keys-function-javascript.md) funkce, a [JSON.stringify](../../javascript/reference/json-stringify-function-javascript.md).|  
|`get: function(target, propertyName, receiver)`|Depeše pro žádné [getter](../../javascript/creating-objects-javascript.md) vlastnosti.|  
|`getOwnPropertyDescriptor: function(target, propertyName)`|K zachycení [Object.getownpropertydescriptor – funkce](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md).|  
|`getPrototypeOf: function(target)`|K zachycení [Object.getprototypeof – funkce](../../javascript/reference/object-getprototypeof-function-javascript.md).|  
|`has: function(target, propertyName)`|K zachycení `in` operátor, [hasOwnProperty – metoda (Object)](../../javascript/reference/hasownproperty-method-object-javascript.md)a jiné metody.|  
|`isExtensible: function(target)`|K zachycení [Object.isextensible – funkce](../../javascript/reference/object-isextensible-function-javascript.md).|  
|`ownKeys: function(target)`|K zachycení [Object.getownpropertynames – funkce](../../javascript/reference/object-getownpropertynames-function-javascript.md).|  
|`preventExtensions: function(target)`|K zachycení [Object.preventextensions – funkce](../../javascript/reference/object-preventextensions-function-javascript.md).|  
|`set: function(target, propertyName, value, receiver)`|Depeše pro žádné [setter](../../javascript/creating-objects-javascript.md) vlastnosti.|  
|`setPrototypeOf: function(target, prototype)`|K zachycení [Object.setprototypeof –](../../javascript/reference/object-setprototypeof-function-javascript.md).|  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak vytvořit proxy pro objekt literálu pomocí `get` depeše.  
  
```JavaScript  
var target = {};  
var handler = {  
  get: function (target, property, receiver) {  
    // This example includes a template string.  
    return `Hello, ${property}!`;  
  }  
};  
  
var p = new Proxy(target, handler);  
console.log(p.world);  
  
// Output:  
// Hello, world!  
  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak vytvořit proxy pro funkce pomocí `apply` depeše.  
  
```JavaScript  
var target = function () { return 'I am the target'; };  
var handler = {  
  // This example includes a rest parameter.  
  apply: function (receiver, ...args) {  
    return 'I am the proxy';  
  }  
};  
  
var p = new Proxy(target, handler);  
console.log(target()):  
console.log(p()):  
  
// Output:  
// I am the target  
// I am the proxy  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]
