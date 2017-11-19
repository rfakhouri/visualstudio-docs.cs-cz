---
title: "Object.preventextensions – funkce (JavaScript) | Microsoft Docs"
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
- properties [JavaScript], preventing new
- preventing new properties [JavaScript]
- preventExtensions function [JavaScript]
- Object.preventExtensions function [JavaScript]
ms.assetid: e6b48197-2374-4437-a9fe-519dd45a2077
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 868f917cc2249a1634194e4b2dd097e0dcbd4c08
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="objectpreventextensions-function-javascript"></a>Object.preventExtensions – funkce (JavaScript)
Zabraňuje přidání nových vlastností do objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
Object.preventExtensions(object)  
```  
  
#### <a name="parameters"></a>Parametry  
 `object`  
 Požadováno. Objekt, aby bez extensible.  
  
## <a name="return-value"></a>Návratová hodnota  
 Objekt, který je předaný funkci.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud `object` argument není objekt, `TypeError` je vyvolána výjimka.  
  
## <a name="remarks"></a>Poznámky  
 `Object.preventExtensions` Funkce umožňuje objektu bez rozšiřitelný, tak, aby nové pojmenované vlastnosti nelze přidat k němu. Po objekt se bez extensible, nelze jako extensible.  
  
 Informace o tom, jak nastavit vlastnost atributy najdete v tématu [Object.defineproperty – funkce](../../javascript/reference/object-defineproperty-function-javascript.md).  
  
## <a name="related-functions"></a>Související funkce  
 Následující funkce související zabránit změna atributů objektu.  
  
|Funkce|Objekt se provádí jiný extensible|`configurable`je nastavena na `false` pro každou vlastnost|`writable`je nastavena na `false` pro každou vlastnost|  
|--------------|------------------------------------|--------------------------------------------------------|----------------------------------------------------|  
|`Object.preventExtensions`|Ano|Ne|Ne|  
|[Object.Seal –](../../javascript/reference/object-seal-function-javascript.md)|Ano|Ano|Ne|  
|[Object.freeze –](../../javascript/reference/object-freeze-function-javascript.md)|Ano|Ano|Ano|  
  
 Následující funkce vrátí `true` Pokud jsou splněny všechny podmínky označené v následující tabulce.  
  
|Funkce|Objekt je rozšiřitelný?|`configurable`je `false` pro všechny vlastnosti?|`writable`je `false` pro všechny vlastnosti dat?|  
|--------------|---------------------------|---------------------------------------------------|----------------------------------------------------|  
|[Object.isextensible –](../../javascript/reference/object-isextensible-function-javascript.md)|Ano|Ne|Ne|  
|[Object.issealed –](../../javascript/reference/object-issealed-function-javascript.md)|Ne|Ano|Ne|  
|[Object.isfrozen –](../../javascript/reference/object-isfrozen-function-javascript.md)|Ne|Ano|Ano|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `Object.preventExtensions` funkce.  
  
```JavaScript  
// Create an object that has two properties.  
var obj = { pasta: "spaghetti", length: 10 };  
  
// Make the object non-extensible.  
Object.preventExtensions(obj);  
document.write(Object.isExtensible(obj));  
document.write("<br/>");  
  
// Try to add a new property, and then verify that it is not added.  
obj.newProp = 50;  
document.write(obj.newProp);  
  
// Output:  
// false  
// undefined  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Object.Seal – funkce](../../javascript/reference/object-seal-function-javascript.md)   
 [Object.freeze – funkce](../../javascript/reference/object-freeze-function-javascript.md)   
 [Object.isextensible – funkce](../../javascript/reference/object-isextensible-function-javascript.md)   
 [Object.issealed – funkce](../../javascript/reference/object-issealed-function-javascript.md)   
 [Object.isfrozen – funkce](../../javascript/reference/object-isfrozen-function-javascript.md)