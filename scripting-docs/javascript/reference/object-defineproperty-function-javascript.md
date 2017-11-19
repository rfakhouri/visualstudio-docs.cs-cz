---
title: "Object.defineproperty – funkce (JavaScript) | Microsoft Docs"
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
- defineProperty function [JavaScript]
- Object.defineProperty function [JavaScript]
ms.assetid: c5d05346-940a-40c2-b12a-e8b25abc8d46
caps.latest.revision: "74"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 89291f5c836f74a5dd71099328ce389a12f6fd24
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="objectdefineproperty-function-javascript"></a>Object.defineProperty – funkce (JavaScript)
Přidá vlastnost do objektu nebo upravuje atributy existující vlastnost.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Object.defineProperty(object, propertyname, descriptor)  
```  
  
## <a name="parameters"></a>Parametry  
 `object`  
 Požadováno. Objekt, u kterého chcete přidat nebo upravit vlastnosti. To může být nativní [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] (to znamená, objekt definovaný uživatelem nebo objekt integrované) nebo objekt DOM.  
  
 `propertyname`  
 Požadováno. Řetězec, který obsahuje název vlastnosti.  
  
 `descriptor`  
 Požadováno. Popisovač pro vlastnost. Může být k vlastnosti dat nebo přistupujícího objektu vlastnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Upravený objekt.  
  
## <a name="remarks"></a>Poznámky  
 Můžete použít `Object.defineProperty` funkce, proveďte následující:  
  
-   Přidáte novou vlastnost k objektu. K tomu dochází, pokud objekt nemá zadaný název vlastnosti.  
  
-   Upravte atributy existující vlastnost. K tomu dochází, pokud objekt již má zadaný název vlastnosti.  
  
 Definici vlastnosti jsou uvedené v popisovač objektu, který popisuje atributy vlastnosti dat nebo přistupujícího objektu vlastnosti. Popisovač objektu je parametr `Object.defineProperty` funkce.  
  
 Chcete-li přidat více vlastností pro objekt, nebo k úpravě existující více vlastností, můžete použít [Object.defineproperties – funkce](../../javascript/reference/object-defineproperties-function-javascript.md).  
  
## <a name="exceptions"></a>Výjimky  
 A `TypeError` je vyvolána výjimka, pokud platí jedna z následujících podmínek:  
  
-   `object` Argument není objekt.  
  
-   Objekt není [extensible](../../javascript/reference/object-isextensible-function-javascript.md) a zadaný název vlastnosti neexistuje...  
  
-   `descriptor` Má `value` nebo `writable` atribut a má `get` nebo `set` atribut.  
  
-   `descriptor` Má `get` nebo `set` atribut tedy není funkcí, nebo není definovaná.  
  
-   Zadaný název vlastnosti již existuje, že má existující vlastnosti `configurable` atribut `false`a `descriptor` obsahuje jeden nebo více atributů, které se liší od těch v existující vlastnosti. Však, když má existující vlastnosti `configurable` atribut `false` a `writable` atribut `true`, je povoleno pro `value` nebo `writable` atributu na jiný.  
  
## <a name="adding-a-data-property"></a>Přidání vlastnosti dat  
 V následujícím příkladu `Object.defineProperty` funkce přidá vlastnost data na objekt definovaný uživatelem. Chcete-li místo toho přidat vlastnost do existujícího objektu modelu DOM, zrušte komentář u `var = window.document` řádku.  
  
```JavaScript  
var newLine = "<br />";  
  
// Create a user-defined object.  
var obj = {};  
  
// Add a data property to the object.  
Object.defineProperty(obj, "newDataProperty", {  
    value: 101,  
    writable: true,  
    enumerable: true,  
    configurable: true  
});  
  
// Set the property value.  
obj.newDataProperty = 102;  
document.write("Property value: " + obj.newDataProperty + newLine);  
  
// Output:  
// Property value: 102  
```  
  
 Pro zobrazení seznamu vlastnosti objektu, přidejte následující kód v tomto příkladu.  
  
```JavaScript  
var names = Object.getOwnPropertyNames(obj);  
for (var i = 0; i < names.length; i++) {  
    var prop = names[i];  
  
    document.write(prop + ': ' + obj[prop]);  
    document.write(newLine);  
}  
  
// Output:  
//  newDataProperty: 102  
```  
  
## <a name="modifying-a-data-property"></a>Úprava vlastností dat  
 Chcete-li upravit atribut vlastností pro objekt, přidejte následující kód do `addDataProperty` funkce uvedena výše. `descriptor` Parametr obsahuje pouze `writable` atribut. Ostatní atributy vlastnost data zůstávají stejné.  
  
```JavaScript  
// Modify the writable attribute of the property.  
Object.defineProperty(obj, "newDataProperty", { writable: false });  
  
// List the property attributes by using a descriptor.  
// Get the descriptor with Object.getOwnPropertyDescriptor.  
var descriptor = Object.getOwnPropertyDescriptor(obj, "newDataProperty");  
for (var prop in descriptor) {  
    document.write(prop + ': ' + descriptor[prop]);  
    document.write(newLine);  
}  
  
// Output  
// writable: false  
// value: 102  
// configurable: true  
// enumerable: true  
```  
  
## <a name="adding-an-accessor-property"></a>Přidání přístupové vlastnosti  
 V následujícím příkladu `Object.defineProperty` funkce přidá vlastnost přistupujícího objektu na objekt definovaný uživatelem.  
  
```JavaScript  
var newLine = "<br />";  
  
// Create a user-defined object.  
var obj = {};  
  
// Add an accessor property to the object.  
Object.defineProperty(obj, "newAccessorProperty", {  
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
});  
  
// Set the property value.  
obj.newAccessorProperty = 30;  
document.write("Property value: " + obj.newAccessorProperty + newLine);  
  
// Output:  
// in property set accessor  
// in property get accessor  
// Property value: 30  
  
```  
  
 Pro zobrazení seznamu vlastnosti objektu, přidejte následující kód v tomto příkladu.  
  
```JavaScript  
var names = Object.getOwnPropertyNames(obj);  
for (var i = 0; i < names.length; i++) {  
    var prop = names[i];  
  
    document.write(prop + ': ' + obj[prop]);  
    document.write(newLine);  
}  
// Output:  
// in property get accessor  
// newAccessorProperty: 30  
  
```  
  
## <a name="modifying-an-accessor-property"></a>Úprava přístupové vlastnosti  
 Pokud chcete upravit vlastnost atribut pro objekt, přidejte následující kód na výše uvedeném kódu. `descriptor` Parametr obsahuje pouze `get` definice přistupujícího objektu. Ostatní atributy vlastnost zůstávají stejné.  
  
```JavaScript  
// Modify the get accessor.  
Object.defineProperty(obj, "newAccessorProperty", {  
    get: function () { return this.newaccpropvalue; }  
});  
  
// List the property attributes by using a descriptor.  
// Get the descriptor with Object.getOwnPropertyDescriptor.  
var descriptor = Object.getOwnPropertyDescriptor(obj, "newAccessorProperty");  
for (var prop in descriptor) {  
    document.write(prop + ': ' + descriptor[prop]);  
    document.write(newLine);  
}  
  
// Output:  
// get: function () { return this.newaccpropvalue; }  
// set: function (x) { document.write("in property set accessor" + newLine); this.newaccpropvalue = x; }  
// configurable: true  
// enumerable: true  
```  
  
## <a name="modifying-a-property-on-a-dom-element"></a>Úprava vlastnosti elementu DOM  
 Následující příklad ukazuje, jak přizpůsobit předdefinované vlastnosti DOM pomocí `Object.getOwnPropertyDescriptor` funkce získat a upravit vlastnosti popisovačem vlastnosti. V tomto příkladu musí existuje DIV elementu s ID "div".  
  
```JavaScript  
// Get the querySelector property descriptor.  
var descriptor = Object.getOwnPropertyDescriptor(Element.prototype, "querySelector");  
  
// Make the property read-only.  
descriptor.value = "query";  
descriptor.writable = false;  
// Apply the changes to the Element prototype.  
Object.defineProperty(Element.prototype, "querySelector", descriptor);  
  
// Get a DOM element from the HTML body.  
var elem = document.getElementById("div");  
  
// Attempt to change the value. This causes the revised value attribute to be called.  
elem.querySelector = "anotherQuery";  
document.write(elem.querySelector);  
  
// Output:  
// query  
  
```  
  
## <a name="requirements"></a>Požadavky  
 Režim, režim standardů aplikace Internet Explorer 9 a režim standardů aplikace Internet Explorer 10, a také [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace, podporu všech funkcí.  
  
 [!INCLUDE[jsv58textspecific](../../javascript/reference/includes/jsv58textspecific-md.md)]podporuje objekty DOM však není uživatelem definované objekty. `enumerable` a `configurable` atributy lze zadat, ale nebudou použity.  
  
## <a name="see-also"></a>Viz také  
 [Prototypy modelu objektu dokumentu, část 2: Přístupového objektu (metoda getter/setter) podpory](http://msdn.microsoft.com/library/dd229916\(v=VS.85\).aspx)   
 [Object.defineproperties – funkce](../../javascript/reference/object-defineproperties-function-javascript.md)   
 [Object.Create – funkce](../../javascript/reference/object-create-function-javascript.md)   
 [Object.getownpropertydescriptor – funkce](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)   
 [Object.getownpropertynames – funkce](../../javascript/reference/object-getownpropertynames-function-javascript.md)