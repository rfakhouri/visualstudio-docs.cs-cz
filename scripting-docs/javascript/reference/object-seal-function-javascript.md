---
title: "Object.Seal – funkce (JavaScript) | Microsoft Docs"
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
helpviewer_keywords:
- Object.seal function
- seal function
ms.assetid: e72c804a-4dab-4ec9-b9df-9c9c908aa12d
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2dca9066be9a557b97a52ae749cecfb218504509
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="objectseal-function-javascript"></a>Object.seal – funkce (JavaScript)
Zabrání se úpravě atributů existující vlastnosti a brání přidání nových vlastností.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
Object.seal(object)  
```  
  
#### <a name="parameters"></a>Parametry  
 `object`  
 Požadováno. Objekt, na které se mají zamknout atributy.  
  
## <a name="return-value"></a>Návratová hodnota  
 Objekt, který je předaný funkci.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud `object` argument není objekt, `TypeError` je vyvolána výjimka.  
  
## <a name="remarks"></a>Poznámky  
 `Object.seal` Funkce nemá obě z následujících akcí:  
  
-   Vytvoří objekt bez rozšiřitelný, tak, aby k němu nelze přidat nové vlastnosti.  
  
-   Nastaví `configurable` atribut `false` pro všechny vlastnosti objektu.  
  
 Když `configurable` atribut je `false`, vlastnost atributy nelze změnit, a vlastnost nelze odstranit. Když `configurable` je `false` a `writable` je `true`, `value` a `writable` atributy lze změnit.  
  
 `Object.seal` Funkce nezmění `writable` atribut.  
  
 Další informace o tom, jak nastavit vlastnost atributy najdete v tématu [Object.defineproperty – funkce](../../javascript/reference/object-defineproperty-function-javascript.md). Chcete-li získat atributy vlastnosti, můžete použít [Object.getownpropertydescriptor – funkce](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md).  
  
## <a name="related-functions"></a>Související funkce  
 Následující funkce související zabránit změna atributů objektu.  
  
|Funkce|Objekt se provádí jiný extensible|`configurable`je nastavena na `false` pro každou vlastnost|`writable`je nastavena na `false` pro každou vlastnost|  
|--------------|------------------------------------|--------------------------------------------------------|----------------------------------------------------|  
|[Object.preventextensions –](../../javascript/reference/object-preventextensions-function-javascript.md)|Ano|Ne|Ne|  
|`Object.seal`|Ano|Ano|Ne|  
|[Object.freeze –](../../javascript/reference/object-freeze-function-javascript.md)|Ano|Ano|Ano|  
  
 Následující funkce vrátí `true` Pokud jsou splněny všechny podmínky označené v následující tabulce.  
  
|Funkce|Objekt je rozšiřitelný?|`configurable`je `false` pro všechny vlastnosti?|`writable`je `false` pro všechny vlastnosti dat?|  
|--------------|---------------------------|---------------------------------------------------|----------------------------------------------------|  
|[Object.isextensible –](../../javascript/reference/object-isextensible-function-javascript.md)|Ano|Ne|Ne|  
|[Object.issealed –](../../javascript/reference/object-issealed-function-javascript.md)|Ne|Ano|Ne|  
|[Object.isfrozen –](../../javascript/reference/object-isfrozen-function-javascript.md)|Ne|Ano|Ano|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `Object.seal` funkce.  
  
```JavaScript  
// Create an object that has two properties.  
var obj = { pasta: "spaghetti", length: 10 };  
// Seal the object.  
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
 [Object.freeze – funkce](../../javascript/reference/object-freeze-function-javascript.md)   
 [Object.isextensible – funkce](../../javascript/reference/object-isextensible-function-javascript.md)   
 [Object.issealed – funkce](../../javascript/reference/object-issealed-function-javascript.md)   
 [Object.isfrozen – funkce](../../javascript/reference/object-isfrozen-function-javascript.md)