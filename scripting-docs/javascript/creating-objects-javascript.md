---
title: Vytváření objektů (JavaScript) | Microsoft Docs
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
- constructors, including properties and methods
- function constructor
- creating objects, constructor functions
- constructor functions
- prototype objects
- creating objects
- custom objects, creating
- creating objects, about creating objects
- objects, creating [JavaScript]
- creating objects, prototypes
- custom objects
- initializing objects, using constructors
ms.assetid: 58d1baa5-4fe8-4a56-a926-5b11765df704
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0ba7962179cc2f0fcb972caee692edabee368c7d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24788871"
---
# <a name="creating-objects-javascript"></a>Vytváření objektů (JavaScript)
Existuje několik způsobů, jak můžete vytvořit vlastní objekty v jazyce JavaScript. Můžete vytvořit přímo instanci [objekt objektu](../javascript/reference/object-object-javascript.md) a poté přidejte vlastní vlastnosti a metody. Nebo můžete použít objekt literálu zápis k definování objektu. Funkce konstruktoru můžete také zadat objekt. Další informace o používání funkce konstruktoru najdete v tématu [pomocí konstruktorů definovat typy](../javascript/advanced/using-constructors-to-define-types.md).  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje postup vytvoření instance objektu a přidání některé vlastnosti. V takovém případě pouze `pasta` objekt má `grain`, `width`, a `shape` vlastnosti.  
  
```JavaScript  
const pasta = new Object();  
pasta.grain = "wheat";  
pasta.width = 0.5;  
pasta.shape = "round";  
pasta.getShape = function() {   
    return this.shape;   
};  
document.write(pasta.grain);  
document.write("<br/>");  
document.write(pasta.getShape());  
  
// Output:  
// wheat  
// round  
  
```  
  
## <a name="object-literals"></a>Objekt literály  
 Také můžete objekt literálu zápis Pokud chcete vytvořit pouze jednu instanci objektu. Následující kód ukazuje, jak vytvořit instanci objektu pomocí zápisu literálu objektu.  
  
```JavaScript  
const pasta = {  
    grain: "wheat",  
    width: 0.5,  
    shape: "round"  
};  
```  
  
 Můžete také použít objekt literálu do konstruktoru.  
  
> [!CAUTION]
>  Funkce popsané níže jsou podporovány pouze v [!INCLUDE[jsv12text](../javascript/includes/jsv12text-md.md)].  
  
 V [!INCLUDE[jsv12text](../javascript/includes/jsv12text-md.md)], můžete vytvořit objekt literálu syntaxi ve zkráceném tvaru.  
  
```JavaScript  
const key = 'a';  
const value = 5;  
  
// Older version  
const obj1 = {  
    key: key,  
    value: value  
};  
  
// Edge mode  
const obj2 = {key, value};  
  
console.log(obj2);  
  
// Output:  
// [object Object] {key: "a", value: 5}  
```  
  
 Následující příklad ukazuje použití syntaxi ve zkráceném tvaru definovat metody v literálech objektu.  
  
```JavaScript  
// Older versions  
const obj = {  
    method1: function() {},  
    method2: function() {}  
};  
  
// Edge mode  
const obj = {  
    method1() {},  
    method2() {}  
};  
```  
  
 Můžete také nastavit názvy vlastností dynamicky v objektu literály v [!INCLUDE[jsv12text](../javascript/includes/jsv12text-md.md)]. Následující příklad kódu vytvoří název vlastnosti pro objekt dynamicky pomocí syntaxe sady.  
  
```JavaScript  
const propName = "prop_42";  
  
const obj = {  
    value: 0,  
    set [propName](v) {  
        this.value = v;  
    }  
}  
  
console.log(obj.value);  
// Runs the setter property.  
obj.prop_42 = 777;  
console.log(obj.value);  
  
// Output:  
// 0  
// 777  
  
```  
  
 Následující příklad kódu vytvoří název vlastnosti pro objekt dynamicky pomocí syntaxe get.  
  
```JavaScript  
const propName = "prop_42";  
  
const obj = {  
    get [propName]() {  
        return 777;  
    }  
}  
  
console.log(obj.prop_42);  
  
// Output:  
// 777  
```  
  
 Následující příklad kódu vytvoří vypočítané vlastnosti pomocí [syntaxe funkce šipku](../javascript/functions-javascript.md) 42 připojit k názvu vlastnosti.  
  
```JavaScript  
const obj = {  
    [ 'prop_' + (() => 42)() ]: 42  
};  
```
