---
title: Prototypy a jejich dědičnost | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- prototype [JavaScript]
- prototype inheritance [JavaScript]
ms.assetid: 1e1d0631-2a9f-4011-b9fe-fa338e1ef34c
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 200ca757e72b2eec8f09fd48a841cc8eb816c85d
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/10/2018
---
# <a name="prototypes-and-prototype-inheritance"></a>Prototypy a jejich dědičnost
V jazyce JavaScript `prototype` je vlastnost funkce a objekty, které jsou vytvořené pomocí funkce konstruktoru. Prototypem funkce je objekt. Nejčastěji se využívá, když se funkce použije jako konstruktor.  
  
```JavaScript  
function Vehicle(wheels, engine) {  
    this.wheels = wheels;  
    this.engine = engine;  
}  
```  
  
 V příkladu výše, prototyp `Vehicle` funkce je prototyp objektu, která je vytvořena s `Vehicle` konstruktor.  
  
## <a name="using-prototypes-to-add-properties-and-methods"></a>Přidání vlastností a metod pomocí prototypů  
 Můžete použít `prototype` vlastnost můžete přidávat vlastnosti a metody k objektům, i ty, které již byly vytvořeny:  
  
```JavaScript  
var testVehicle = new Vehicle(2, false);  
Vehicle.prototype.color = "red";  
var testColor = testVehicle.color;  
```  
  
 Hodnota `testColor` je "red".  
  
 Můžete dokonce přidat vlastnosti a metody předdefinovaných objektů. Například můžete definovat `Trim` metodu `String` objektu prototypu a všechny řetězce ve vašem skriptu zdědí metodu.  
  
```JavaScript  
String.prototype.trim = function()  
{  
    // Replace leading and trailing spaces with the empty string  
    return this.replace(/(^\s*)|(\s*$)/g, "");  
}  
var s = "    leading and trailing spaces    ";  
// Displays "    leading and trailing spaces     (35)"  
window.alert(s + " (" + s.length + ")");  
// Remove the leading and trailing spaces  
s = s.trim();  
// Displays "leading and trailing spaces (27)"  
window.alert(s + " (" + s.length + ")");  
```  
  
### <a name="using-prototypes-to-derive-one-object-from-another-with-objectcreate"></a>Použití prototypů k odvození jednoho objektu z jiného pomocí Object.create  

Prototyp `Object` lze použít k odvození jeden objekt z jiné. Například můžete použít [Object.create –](../../javascript/reference/object-create-function-javascript.md) funkce odvození nový objekt `Bicycle` pomocí prototypu z `Vehicle` definovaného dříve (plus nové vlastnosti potřebujete).  
  
```JavaScript  
var bicycle = Object.create(Object.getPrototypeOf(Vehicle), {  
    "pedals" :{value: true}  
});  
  
```  
  
 `bicycle` Objekt má vlastnosti `wheels`, `engine`, `color`, a `pedals`, a jeho prototypu `Vehicle.prototype`. Najde modul JavaScript `pedals` vlastnost `bicycle`, a dojde k vyhledání řetězce prototypu pro vyhledání `wheels`, `engine`, a `color` vlastnosti `Vehicle`.  
  
### <a name="changing-an-objects-prototype"></a>Změna prototypu objektu  
V aplikaci Internet Explorer 11, můžete nahradit interní prototyp objektu nebo funkce prototyp nové pomocí [ __proto –__ ](../../javascript/reference/proto-property-object-javascript.md) vlastnost. Když použijete tuto vlastnost, zdědíte vlastnosti a metody nového prototypu společně se všemi ostatními vlastnostmi a metodami v jejím řetězci prototypu.  

> [!WARNING]
> `__proto__` Vlastnost je starší verze funkce. Použití [Object.getprototypeof –](../reference/object-getprototypeof-function-javascript.md) místo.
  
Následující příklad ukazuje, jak lze změnit prototyp objektu. Tento příklad ukazuje, jak se změní zděděné vlastnosti objektu při změně jeho prototypu.  
  
```JavaScript  
function Friend() {  
    this.demeanor = "happy";  
}  
  
function Foe() {  
    this.demeanor = "suspicious";  
}  
  
var friend = new Friend();  
var foe = new Foe();  
  
var player = new Object();  
player.__proto__ = foe;  
  
friend.ally = "Tom";  
  
if (console && console.log) {  
    console.log(player.demeanor === "happy" );      // Returns false  
    console.log(player.demeanor === "suspicious");  // Returns true  
    console.log(player.ally === "Tom");             // Returns false  
    // Turn the foe to a friend.  
    player.__proto__ = friend;  
    console.log(player.demeanor === "happy");       // Returns true  
    console.log(player.demeanor === "suspicious");  // Returns false  
    console.log(player.ally === "Tom");             // Returns true  
}  
```
