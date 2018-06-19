---
title: Object.freeze – funkce (JavaScript) | Microsoft Docs
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
- Object.freeze function
- freeze function
ms.assetid: 83ffe193-0a37-4e0c-9b66-44c422765fb3
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ec08b34c3c8b32245928e6e75f5df1fbdfe2d4a6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792072"
---
# <a name="objectfreeze-function-javascript"></a>Object.freeze – funkce (JavaScript)
Zabrání se úpravě existující vlastnost atributy a hodnoty a zabrání přidání nových vlastností.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
Object.freeze(object)  
```  
  
#### <a name="parameters"></a>Parametry  
 `object`  
 Požadováno. Objekt, na které se mají zamknout atributy.  
  
## <a name="return-value"></a>Návratová hodnota  
 Objekt, který je předaný funkci.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud `object` argument není objekt, `TypeError` je vyvolána výjimka.  
  
## <a name="remarks"></a>Poznámky  
 `Object.freeze` Funkce provede následující akce:  
  
-   Vytvoří objekt bez rozšiřitelný, tak, aby k němu nelze přidat nové vlastnosti.  
  
-   Nastaví `configurable` atribut `false` pro všechny vlastnosti objektu. Když `configurable` je `false`, vlastnost atributy nelze změnit, a vlastnost nelze odstranit.  
  
-   Nastaví `writable` atribut `false` pro všechny vlastnosti datového objektu. Když `writable` je nastavena hodnota false, hodnota vlastnosti dat nelze změnit.  
  
 Další informace o tom, jak nastavit vlastnost atributy najdete v tématu [Object.defineproperty – funkce](../../javascript/reference/object-defineproperty-function-javascript.md). Chcete-li získat atributy vlastnost, můžete použít [Object.getownpropertydescriptor – funkce](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md).  
  
## <a name="related-functions"></a>Související funkce  
 Následující funkce související zabránit změna atributů objektu.  
  
|Funkce|Objekt se provádí jiný extensible|`configurable`je nastavena na `false` pro každou vlastnost|`writable`je nastavena na `false` pro každou vlastnost|  
|--------------|------------------------------------|--------------------------------------------------------|----------------------------------------------------|  
|[Object.preventextensions –](../../javascript/reference/object-preventextensions-function-javascript.md)|Ano|Ne|Ne|  
|[Object.Seal –](../../javascript/reference/object-seal-function-javascript.md)|Ano|Ano|Ne|  
|`Object.freeze`|Ano|Ano|Ano|  
  
 Následující funkce vrátí `true` Pokud jsou splněny všechny podmínky označené v následující tabulce.  
  
|Funkce|Objekt je rozšiřitelný?|`configurable`je `false` pro všechny vlastnosti?|`writable`je `false` pro všechny vlastnosti dat?|  
|--------------|---------------------------|---------------------------------------------------|----------------------------------------------------|  
|[Object.isextensible –](../../javascript/reference/object-isextensible-function-javascript.md)|Ano|Ne|Ne|  
|[Object.issealed –](../../javascript/reference/object-issealed-function-javascript.md)|Ne|Ano|Ano|  
|[Object.isfrozen –](../../javascript/reference/object-isfrozen-function-javascript.md)|Ne|Ano|Ano|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `Object.freeze` funkce.  
  
```JavaScript  
// Create an object that has two properties.  
var obj = { pasta: "spaghetti", length: 10 };  
  
// Freeze the object.  
Object.freeze(obj);  
  
// Try to add a new property, and then verify that it is not added.   
    obj.newProp = 50;  
    document.write(obj.newProp);  
    document.write("<br/>");  
  
// Try to delete a property, and then verify that it is still present.   
delete obj.length;  
document.write(obj.length);  
document.write("<br/>");  
  
// Try to change a property value, and then verify that it is not changed.   
obj.pasta = "linguini";  
document.write(obj.pasta);  
  
// Output:  
// undefined  
// 10  
// spaghetti  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Object.preventextensions – funkce](../../javascript/reference/object-preventextensions-function-javascript.md)   
 [Object.Seal – funkce](../../javascript/reference/object-seal-function-javascript.md)   
 [Object.isextensible – funkce](../../javascript/reference/object-isextensible-function-javascript.md)   
 [Object.issealed – funkce](../../javascript/reference/object-issealed-function-javascript.md)   
 [Object.isfrozen – funkce](../../javascript/reference/object-isfrozen-function-javascript.md)