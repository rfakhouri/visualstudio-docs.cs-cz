---
title: Object.getownpropertydescriptor – funkce (JavaScript) | Microsoft Docs
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
- getOwnPropertyDescriptor method [JavaScript]
ms.assetid: 8f0e1c90-c4f9-44c4-bf76-726bacecbc14
caps.latest.revision: 45
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd147d567fc4d8a39d7a251d55772c40518e7a26
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791217"
---
# <a name="objectgetownpropertydescriptor-function-javascript"></a>Object.getOwnPropertyDescriptor – funkce (JavaScript)
Získá popisovač vlastní vlastnost zadaného objektu. Popisovač vlastní vlastnost je ten, který je definován přímo na objekt a není zděděna z objektu prototypu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Object.getOwnPropertyDescriptor(object, propertyname)  
```  
  
## <a name="parameters"></a>Parametry  
 `object`  
 Požadováno. Objekt, který obsahuje vlastnost.  
  
 `propertyname`  
 Požadováno. Název vlastnosti  
  
## <a name="return-value"></a>Návratová hodnota  
 Popisovač vlastnosti.  
  
## <a name="remarks"></a>Poznámky  
 Můžete použít `Object.getOwnPropertyDescriptor` funkce získat popisovač objektu, který popisuje atributy vlastnosti.  
  
 [Object.defineproperty – funkce](../../javascript/reference/object-defineproperty-function-javascript.md) se používá k přidání nebo změna vlastností.  
  
## <a name="data-property-example"></a>Příklad datové vlastnosti  
 Následující příklad získá popisovač vlastnosti data a použije ho k nastavení vlastnosti jen pro čtení.  
  
```JavaScript  
// Create a user-defined object.  
var obj = {};  
  
// Add a data property.  
obj.newDataProperty = "abc";  
  
// Get the property descriptor.  
var descriptor = Object.getOwnPropertyDescriptor(obj, "newDataProperty");  
  
// Change a property attribute.  
descriptor.writable = false;  
Object.defineProperty(obj, "newDataProperty", descriptor);  
  
```  
  
 Seznam atributů vlastnosti, můžete přidat následující kód pro tento příklad.  
  
```JavaScript  
// Get the descriptor from the object.  
var desc2 = Object.getOwnPropertyDescriptor(obj, "newDataProperty");  
  
// List the descriptor attributes.  
for (var prop in desc2) {  
    document.write(prop + ': ' + desc2[prop]);  
    document.write("<br />");  
}  
  
// Output:  
// value: abc  
// writable: false  
// enumerable: true  
// configurable: true  
```  
  
## <a name="requirements"></a>Požadavky  
 Všechny funkce jsou podporované v [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)].  
  
 [!INCLUDE[jsv58textspecific](../../javascript/reference/includes/jsv58textspecific-md.md)]podporuje objekty DOM však není uživatelem definované objekty. `enumerable` a `configurable` atributy lze zadat, ale nebudou použity.  
  
## <a name="see-also"></a>Viz také  
 [Prototypy modelu objektu dokumentu, část 2: Přístupového objektu (metoda getter/setter) podpory](http://msdn.microsoft.com/library/dd229916\(v=VS.85\).aspx)   
 [Object.defineproperty – funkce](../../javascript/reference/object-defineproperty-function-javascript.md)