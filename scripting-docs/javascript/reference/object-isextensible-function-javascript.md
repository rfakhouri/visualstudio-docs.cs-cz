---
title: Object.isextensible – funkce (JavaScript) | Microsoft Docs
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
- Object.isExtensible function [JavaScript]
- isExtensible function [JavaScript]
ms.assetid: a7d10beb-0d01-4e2d-8263-59ff07ac4352
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f88a61917811a5c6b5583e6c30539efc682296df
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791841"
---
# <a name="objectisextensible-function-javascript"></a>Object.isExtensible – funkce (JavaScript)
Vrátí hodnotu, která určuje, zda nové vlastnosti lze přidat do objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
Object.isExtensible(object)  
```  
  
#### <a name="parameters"></a>Parametry  
 `object`  
 Požadováno. Objekt, který se má ověřit  
  
## <a name="return-value"></a>Návratová hodnota  
 `true`Pokud se objekt rozšiřitelné, což naznačuje, že nové vlastnosti lze přidat do objektu; v opačném `false`.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud `object` argument není objekt, `TypeError` je vyvolána výjimka.  
  
## <a name="remarks"></a>Poznámky  
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
|`Object.isExtensible`|Ano|Ne|Ne|  
|[Object.issealed –](../../javascript/reference/object-issealed-function-javascript.md)|Ne|Ano|Ne|  
|[Object.isfrozen –](../../javascript/reference/object-isfrozen-function-javascript.md)|Ne|Ano|Ano|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `Object.isExtensible` funkce.  
  
```JavaScript  
// Create an object that has two properties.  
var obj = { pasta: "spaghetti", length: 10 };  
  
// Make the object non-extensible.  
Object.preventExtensions(obj);  
  
// Try to add a new property, and then verify that it is not added.  
obj.newProp = 50;  
document.write(obj.newProp);  
  
// Output:  
undefined  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Object.preventextensions – funkce](../../javascript/reference/object-preventextensions-function-javascript.md)   
 [Object.Seal – funkce](../../javascript/reference/object-seal-function-javascript.md)   
 [Object.freeze – funkce](../../javascript/reference/object-freeze-function-javascript.md)   
 [Object.issealed – funkce](../../javascript/reference/object-issealed-function-javascript.md)   
 [Object.isfrozen – funkce](../../javascript/reference/object-isfrozen-function-javascript.md)