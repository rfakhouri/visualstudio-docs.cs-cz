---
title: Objekty a pole (JavaScript) | Microsoft Docs
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
- arrays [JavaScript]
- arrays [JavaScript], objects
ms.assetid: f5106284-1240-4f47-8c3b-5a45e227e5e1
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6776701ba108ae0ecefc2331c2b12272e0c1be19
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789132"
---
# <a name="objects-and-arrays-javascript"></a>Objekty a pole (JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)]objekty jsou kolekce vlastností a metod. Funkce, který je členem objektu je metoda. Vlastnost je hodnota nebo sadu hodnot (ve formě pole nebo objekt), který je členem objektu. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]podporuje čtyři typy objektů:  
  
-   Vnitřních objektů, jako například `Array` a `String`.  
  
-   Objekty, které vytvoříte.  
  
-   Hostování objekty, jako například `window` a `document`.  
  
-   Objekty ActiveX.  
  
## <a name="expando-properties-and-methods"></a>Vlastnosti a metody Expando  
 Všechny objekty v [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] podporu expando vlastnosti a metody, které můžete přidat nebo odebrat za běhu. Tyto vlastnosti a metody může mít libovolný název a lze identifikovat podle čísla. Pokud název vlastnosti nebo metody je jednoduchý identifikátor, může být zapsán po názvu objektu s dobou, jako například `myObj.name`, `myObj.age`, a `myObj.getAge` v následujícím kódu:  
  
```JavaScript  
var myObj = new Object();  
myObj.name = "Fred";  
myObj.age = 42;  
  
myObj.getAge =   
    function () {  
        return this.age;  
    };  
  
document.write(myObj.name);  
document.write("<br/>");  
document.write(myObj.age);  
document.write("<br/>");  
document.write(myObj.getAge());  
  
// Output:  
// Fred  
// 42  
// 42  
  
```  
  
 Pokud název vlastnosti nebo metody není jednoduchý identifikátor nebo neznámé v době, kdy zápisu skriptu, můžete indexování vlastnost výraz uvnitř hranaté závorky. Názvy všech vlastností expando v [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] jsou převedeny na řetězce před se přidává do objektu.  
  
```JavaScript  
var myObj = new Object();  
  
// Add two expando properties that cannot be written in the  
// object.property syntax.  
// The first contains invalid characters (spaces), so must be  
// written inside square brackets.  
myObj["not a valid identifier"] = "This is the property value";  
  
// The second expando name is a number, so it also must  
// be placed inside square brackets  
myObj[100] = "100";  
```  
  
 Informace o vytvoření objektu z definice najdete v tématu [vytváření objektů](../javascript/creating-objects-javascript.md).  
  
## <a name="arrays-as-objects"></a>Pole jako objekty  
 V [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], prakticky stejně jako zpracovává objekty a pole, protože pole jsou jenom speciální typ objektu. Objekty a pole může mít vlastnosti a metody.  
  
 Pole mají `length` vlastnost ale objekty nepodporují. Přiřadíte-li hodnotu na element pole jehož index je větší než jeho délka (například `myArray[100] = "hello"`), `length` vlastnost je automaticky zvýšena na nové délky. Podobně pokud uděláte `length` vlastnost menší libovolný element, jehož index je mimo délka pole se odstraní.  
  
```JavaScript  
// An array with three elements  
var myArray = new Array(3);  
  
// Add some data  
myArray[0] = "Hello";  
myArray[1] = 42;  
myArray[2] = new Date(2000, 1, 1);  
  
document.write("original length is: " + myArray.length);  
document.write("<br/>");  
// Add some expando properties  
myArray.expando = "JavaScript!";  
myArray["another Expando"] = "Windows";  
  
// This will still display 3, since the two expando properties  
// don't affect the length.  
document.write("new length is : " + myArray.length);  
  
// Output:  
// original length is: 3  
// new length is : 3  
  
```  
  
 Pole poskytují metody k iteraci nad a upravit členy. Následující příklad ukazuje, jak získat vlastnosti objektů, které jsou uloženy do pole.  
  
```JavaScript  
var myArray = new Array(3);  
  
// Add some data  
for(var i = 1; i <= 3; i++) {  
    myArray[i] = new Date(2000 + i, 1, 1);  
}  
  
myArray.forEach(function (item) {  
    document.write(item.getFullYear());  
});  
  
// Output:  
// 2001  
// 2002  
// 2003  
```  
  
## <a name="multi-dimensional-arrays"></a>Vícerozměrná pole  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]nemá podporu vícerozměrných polí není přímo, ale chování vícerozměrných polí získáte tak, že ukládání polí v rámci prvky jiné pole. (Můžete ukládat žádné řazení dat uvnitř elementy pole, včetně jiné pole.) Například následující kód vytvoří násobení pro čísla až 5.  
  
```JavaScript  
// The size of the table.  
var iMaxNum = 5;  
// Loop counters.  
var i, j;  
  
// Set the length of the array to iMaxNum + 1.   
// The first array index is zero, not 1.  
var MultiplicationTable = new Array(iMaxNum + 1);  
  
// Loop for each major number (each row in the table)  
for (i = 1; i <= iMaxNum; i++)  
{  
    // Create the columns in the table  
    MultiplicationTable[i] = new Array(iMaxNum + 1);  
  
    // Fill the row with the results of the multiplication  
    for (j = 1; j <= iMaxNum; j++)  
    {  
        MultiplicationTable[i][j] = i * j;  
    }  
}  
  
document.write(MultiplicationTable[3][4]);  
document.write("<br/>");   
document.write(MultiplicationTable[5][2]);  
document.write("<br/>");  
document.write(MultiplicationTable[1][4]);  
  
// Output:  
// 12  
// 10  
// 4  
  
```