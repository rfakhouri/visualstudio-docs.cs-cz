---
title: Object.issealed – funkce (JavaScript) | Microsoft Docs
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
helpviewer_keywords:
- properties [JavaScript], locking attributes
- isSealed function [JavaScript]
- Object.isSealed [JavaScript]
ms.assetid: af4f192e-cebe-44b9-8eef-90c096f5ae8f
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4d3b9cb603a456382e3b23e6f7d0037063027b98
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792129"
---
# <a name="objectissealed-function-javascript"></a>Object.isSealed – funkce (JavaScript)
Vrátí `true` Pokud existující atributy vlastnost nemůže být upravena v objektu, a nové vlastnosti nelze přidat k objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
Object.isSealed(object)  
```  
  
#### <a name="parameters"></a>Parametry  
 `object`  
 Požadováno. Objekt, který se má ověřit  
  
## <a name="return-value"></a>Návratová hodnota  
 `true`Pokud jsou splněny obě následující:  
  
-   Objekt je jiný rozšiřitelný, což naznačuje, že nové vlastnosti nelze přidat k objektu.  
  
-   `configurable` Atribut je `false` pro všechny existující vlastnosti.  
  
 Pokud objekt nemá žádné vlastnosti, funkce vrátí hodnotu `true` Pokud se objekt bez extensible.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud `object` argument není objekt, `TypeError` je vyvolána výjimka.  
  
## <a name="remarks"></a>Poznámky  
 Když `configurable` je atribut vlastnost `false`, vlastnost atributy nelze změnit, a vlastnost nelze odstranit. Když `writable` je `false`, hodnota vlastnosti dat nelze změnit. Když `configurable` je `false` a `writable` je `true`, `value` a `writable` atributy lze změnit.  
  
 `Object.isSealed` Funkce nepoužívá `writable` atribut vlastnosti k určení hodnoty.  
  
 Informace o tom, jak nastavit vlastnost atributy najdete v tématu [Object.defineproperty – funkce](../../javascript/reference/object-defineproperty-function-javascript.md). Chcete-li získat atributy vlastnost, můžete použít [Object.getownpropertydescriptor – funkce](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md).  
  
## <a name="related-functions"></a>Související funkce  
 Následující funkce související zabránit změna atributů objektu.  
  
|Funkce|Objekt se provádí jiný extensible|`configurable`je nastavena na `false` pro každou vlastnost|`writable`je nastavena na `false` pro každou vlastnost|  
|--------------|------------------------------------|--------------------------------------------------------|----------------------------------------------------|  
|[Object.preventextensions –](../../javascript/reference/object-preventextensions-function-javascript.md)|Ano|Ne|Ne|  
|[Object.Seal –](../../javascript/reference/object-seal-function-javascript.md)|Ano|Ano|Ne|  
|[Object.freeze –](../../javascript/reference/object-freeze-function-javascript.md)|Ano|Ano|Ano|  
  
 Následující funkce vrátí `true` Pokud jsou splněny všechny podmínky označené v následující tabulce.  
  
|Funkce|Objekt je rozšiřitelný?|`configurable`je `false` pro všechny vlastnosti?|`writable`je `false` pro všechny vlastnosti dat?|  
|--------------|---------------------------|---------------------------------------------------|----------------------------------------------------|  
|[Object.isextensible –](../../javascript/reference/object-isextensible-function-javascript.md)|Ano|Ne|Ne|  
|`Object.isSealed`|Ne|Ano|Ne|  
|[Object.isfrozen –](../../javascript/reference/object-isfrozen-function-javascript.md)|Ne|Ano|Ano|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `Object.isSealed` funkce.  
  
```JavaScript  
// Create an object that has two properties.  
var obj = { pasta: "spaghetti", length: 10 };  
  
// Seal the object, and verify that it is sealed.  
Object.seal(obj);  
document.write(Object.isSealed(obj));  
document.write("<br/>");  
  
// Try to add a new property, and then verify that it is not added.   
obj.newProp = 50;  
document.write(obj.newProp);  
document.write("<br/>");  
  
// Try to delete a property, and then verify that it is still present.   
delete obj.length;  
document.write(obj.length);  
  
// Output:  
// true  
// undefined  
// 10  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Object.preventextensions – funkce](../../javascript/reference/object-preventextensions-function-javascript.md)   
 [Object.Seal – funkce](../../javascript/reference/object-seal-function-javascript.md)   
 [Object.freeze – funkce](../../javascript/reference/object-freeze-function-javascript.md)   
 [Object.isextensible – funkce](../../javascript/reference/object-isextensible-function-javascript.md)   
 [Object.isfrozen – funkce](../../javascript/reference/object-isfrozen-function-javascript.md)   
 [Object.defineproperty – funkce](../../javascript/reference/object-defineproperty-function-javascript.md)   
 [Object.getownpropertydescriptor – funkce](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)