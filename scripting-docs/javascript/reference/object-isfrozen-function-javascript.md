---
title: Object.isfrozen – funkce (JavaScript) | Microsoft Docs
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
- isFrozen function [JavaScript]
- Object.isFrozen function [JavaScript]
ms.assetid: 6cf1bbc6-56e8-429b-8e2c-0024fa614acc
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3e1ccd11d5b4ef3b5f24dbfc8e815f0e3e156347
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792039"
---
# <a name="objectisfrozen-function-javascript"></a>Object.isFrozen – funkce (JavaScript)
Vrátí `true` Pokud existující vlastnost atributy a hodnoty nemůže být upraven v objektu, a nové vlastnosti nelze přidat k objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
Object.isFrozen(object)  
```  
  
#### <a name="parameters"></a>Parametry  
 `object`  
 Požadováno. Objekt, který se má ověřit  
  
## <a name="return-value"></a>Návratová hodnota  
 `true`Pokud jsou splněny všechny z následujících akcí:  
  
-   Objekt je jiný rozšiřitelný, což naznačuje, že nové vlastnosti nelze přidat k objektu.  
  
-   `configurable` Atribut je `false` pro všechny existující vlastnosti.  
  
-   `writable` Atribut je `false` pro všechny vlastnosti existující data.  
  
 Pokud objekt nemá žádné existující vlastnosti, funkce vrátí hodnotu `true` Pokud se objekt bez extensible.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud `object` argument není objekt, `TypeError` je vyvolána výjimka.  
  
## <a name="remarks"></a>Poznámky  
 Když `configurable` je atribut vlastnost `false`, vlastnost atributy nelze změnit, a vlastnost nelze odstranit. Když `writable` je `false`, hodnota vlastnosti dat nelze změnit. Když `configurable` je `false` a `writable` je `true`, `value` a `writable` atributy lze změnit.  
  
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
|[Object.issealed –](../../javascript/reference/object-issealed-function-javascript.md)|Ne|Ano|Ne|  
|`Object.isFrozen`|Ne|Ano|Ano|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `Object.isFrozen` funkce.  
  
```JavaScript  
// Create an object that has two properties.  
var obj = { pasta: "spaghetti", length: 10 };  
  
// Freeze the object, and verify that it is frozen.  
Object.freeze(obj);  
document.write(obj.isFrozen());  
  
// Try to add a new property, and then verify that it is not added.   
obj.newProp = 50;  
document.write (obj.newProp);  
document.write ("<br/>");  
  
// Try to delete a property, and then verify that it is still present.  
delete obj.length;  
document.write (obj.length);  
document.write ("<br/> ");  
  
// Try to change a property value, and then verify that it is not changed.  
obj.pasta = "linguini";  
document.write (obj.pasta);  
  
// Output:  
// true  
// undefined  
// 10  
// spaghetti  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Object.preventextensions – funkce](../../javascript/reference/object-preventextensions-function-javascript.md)   
 [Object.Seal – funkce](../../javascript/reference/object-seal-function-javascript.md)   
 [Object.freeze – funkce](../../javascript/reference/object-freeze-function-javascript.md)   
 [Object.isextensible – funkce](../../javascript/reference/object-isextensible-function-javascript.md)   
 [Object.issealed – funkce](../../javascript/reference/object-issealed-function-javascript.md)   
 [Object.defineproperty – funkce](../../javascript/reference/object-defineproperty-function-javascript.md)   
 [Object.getownpropertydescriptor – funkce](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)   
 [Object.getownpropertynames – funkce](../../javascript/reference/object-getownpropertynames-function-javascript.md)