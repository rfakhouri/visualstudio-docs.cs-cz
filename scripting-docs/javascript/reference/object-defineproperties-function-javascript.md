---
title: "Object.defineproperties – funkce (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Object.defineProperties function [JavaScript]
ms.assetid: 2dae6658-a1c9-495f-bf06-bb3e964e6762
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 65f4f5817a105283a26c971bd98869d000ca0bc2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="objectdefineproperties-function-javascript"></a>Object.defineProperties – funkce (JavaScript)
Přidá jeden nebo více vlastností do objektu nebo upravuje atributy existující vlastnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
object.defineProperties(object, descriptors)  
```  
  
## <a name="parameters"></a>Parametry  
 `object`  
 Požadováno. Objekt, u kterého chcete přidat nebo upravit vlastnosti. To může být nativní [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objekt nebo objekt DOM.  
  
 `descriptors`  
 Požadováno. A [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] objekt, který obsahuje jeden nebo více objektů popisovač. Každý objekt popisovače popisuje vlastnosti dat nebo ve přistupujícího objektu vlastnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Objekt, který byl funkci předán.  
  
## <a name="remarks"></a>Poznámky  
 `descriptors` Argument je objekt, který obsahuje jeden nebo více objektů popisovač.  
  
 A *vlastnosti dat* je vlastnost, která můžete ukládat a načítat hodnotu. Popisovač vlastnosti dat obsahuje `value` atribut `writable` atribut, nebo obojí. Další informace najdete v tématu [dat a přístupové vlastnosti](../../javascript/advanced/data-properties-and-accessor-properties.md).  
  
 *Přistupujícího objektu vlastnosti* pokaždé, když je hodnota vlastnosti nastavit nebo načíst volá funkci zadaný uživatelem. Popisovač přistupujícího objektu vlastnosti obsahuje `set` atribut `get` atribut, nebo obojí.  
  
 Pokud objekt již má vlastnost, která má zadaný název, jsou upravit atributy vlastnost. Další informace najdete v tématu [Object.defineproperty – funkce](../../javascript/reference/object-defineproperty-function-javascript.md).  
  
 Chcete-li vytvořit objekt a přidání vlastnosti do nového objektu, můžete použít [Object.Create – funkce](../../javascript/reference/object-create-function-javascript.md).  
  
## <a name="adding-properties"></a>Přidání vlastností  
 V následujícím příkladu `Object.defineProperties` funkce přidá vlastnosti dat a ve vlastnosti přístupového objektu na objekt definovaný uživatelem.  
  
 Tento příklad používá objekt literálu k vytvoření `descriptors` objektu s `newDataProperty` a `newAccessorProperty` popisovač objekty.  
  
```JavaScript  
var newLine = "<br />";  
  
var obj = {};  
Object.defineProperties(obj, {  
    newDataProperty: {  
        value: 101,  
        writable: true,  
        enumerable: true,  
        configurable: true  
    },  
    newAccessorProperty: {  
        set: function (x) {  
            document.write("in property set accessor" + newLine);  
            this.newaccpropvalue = x;  
        },  
        get: function () {  
            document.write("in property get accessor" + newLine);  
            return this.newaccpropvalue;  
        },  
        enumerable: true,  
        configurable: true  
    }});  
  
// Set the accessor property value.  
obj.newAccessorProperty = 10;  
document.write ("newAccessorProperty value: " + obj.newAccessorProperty + newLine);  
  
// Output:  
// in property set accessor  
// in property get accessor  
// newAccessorProperty value: 10  
  
```  
  
 Podobně jako v příkladu starší následující příklad přidá vlastnosti dynamicky místo s objektem literálu.  
  
```JavaScript  
  
var newLine = "<br />";  
  
// Create the descriptors object.  
var descriptors = new Object();  
  
// Add a data property descriptor to the descriptors object.  
descriptors.newDataProperty = new Object();  
descriptors.newDataProperty.value = 101;  
descriptors.newDataProperty.writable = true;  
descriptors.newDataProperty.enumerable = true;  
descriptors.newDataProperty.configurable = true;  
  
// Add an accessor property descriptor to the descriptors object.  
descriptors.newAccessorProperty = new Object();  
descriptors.newAccessorProperty.set = function (x) {  
    document.write("in property set accessor" + newLine);  
    this.newaccpropvalue = x;  
};  
descriptors.newAccessorProperty.get = function () {  
    document.write("in property get accessor" + newLine);  
    return this.newaccpropvalue;  
};  
descriptors.newAccessorProperty.enumerable = true;  
descriptors.newAccessorProperty.configurable = true;  
  
// Call the Object.defineProperties function.  
var obj = new Object();  
Object.defineProperties(obj, descriptors);  
  
// Set the accessor property value.  
obj.newAccessorProperty = 10;  
document.write ("newAccessorProperty value: " + obj.newAccessorProperty + newLine);  
  
// Output:  
// in property set accessor  
// in property get accessor  
// newAccessorProperty value: 10  
  
```  
  
## <a name="modifying-properties"></a>Úpravy vlastností  
 Pokud chcete upravit atributy vlastností pro objekt, přidejte následující kód. `Object.defineProperties` Funkce upraví `writable` atribut `newDataProperty`a změní `enumerable` atribut `newAccessorProperty`. Přidá `anotherDataProperty` k objektu vzhledem k tomu, že název vlastnosti již neexistuje.  
  
```  
Object.defineProperties(obj, {  
    newDataProperty: { writable: false },  
    newAccessorProperty: { enumerable: false },  
    anotherDataProperty: { value: "abc" }  
});  
```  
  
## <a name="requirements"></a>Požadavky  
 Podporované v standardy aplikace Internet Explorer 9, standardy aplikace Internet Explorer 10 a [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace. Podporováno v aplikaci Internet Explorer 8 pro objekty DOM pouze, jinak není podporovaná.  
  
## <a name="see-also"></a>Viz také  
 [Object.getownpropertydescriptor – funkce](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)   
 [Object.getownpropertynames – funkce](../../javascript/reference/object-getownpropertynames-function-javascript.md)   
 [Object.defineproperty – funkce](../../javascript/reference/object-defineproperty-function-javascript.md)   
 [Object.Create – funkce](../../javascript/reference/object-create-function-javascript.md)   
 [Object – objekt](../../javascript/reference/object-object-javascript.md)