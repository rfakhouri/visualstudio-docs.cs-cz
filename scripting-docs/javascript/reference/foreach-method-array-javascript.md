---
title: foreach – metoda (pole) (JavaScript) | Microsoft Docs
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
- forEach method [JavaScript]
- arrays [JavaScript], forEach method
- callback function, forEach method [JavaScript]
ms.assetid: bd188034-a62b-4cbd-99c8-46d70dd6823d
caps.latest.revision: 28
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ec35c49e272ba50e26d3e4e7d892aa719a090d73
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790755"
---
# <a name="foreach-method-array-javascript"></a>forEach – metoda (Array) (JavaScript)
Provede zadanou akci pro každý prvek v poli.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
array1.forEach(callbackfn[, thisArg])  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Definice|  
|---------------|----------------|  
|`array1`|Požadováno. Objekt Array.|  
|`callbackfn`|Požadováno. Funkce, která přijímá až tři argumenty. `forEach`volání `callbackfn` funkce jednou pro každý prvek v poli.|  
|`thisArg`|Volitelné. Objekt, ke kterému `this` – klíčové slovo najdete v `callbackfn` funkce. Pokud `thisArg` je vynechán, `undefined` slouží jako `this` hodnotu.|  
  
## <a name="exceptions"></a>Výjimky  
 Pokud `callbackfn` argument není objekt funkce `TypeError` je vyvolána výjimka.  
  
## <a name="remarks"></a>Poznámky  
 `forEach` Volání metod `callbackfn` funkce jednou pro každý prvek v poli ve vzestupném pořadí index. Funkce zpětného volání není volána pro chybějící prvky pole.  
  
 Kromě pole objektů `forEach` metodu lze použít objektem, který má `length` vlastnost a že má indexované podle čísel názvy vlastností.  
  
## <a name="callback-function-syntax"></a>Syntaxe funkce zpětného volání  
 Syntaxe funkce zpětného volání je následující:  
  
 `function callbackfn(value, index, array1)`  
  
 Funkci zpětného volání můžete deklarovat pomocí až tří parametrů.  
  
 Parametry funkce zpětného volání jsou následující.  
  
|Argument zpětného volání|Definice|  
|-----------------------|----------------|  
|`value`|Hodnota prvku pole.|  
|`index`|Číselný index prvku pole.|  
|`array1`|Objekt pole obsahující prvek.|  
  
## <a name="modifying-the-array-object"></a>Úprava objektu pole  
 `forEach` Metoda neupravuje přímo původní pole, ale může upravit funkce zpětného volání. Následující tabulka popisuje výsledky změnu objekt array po `forEach` metoda spustí.  
  
|Podmínka po `forEach` spustí – metoda|Byl prvek předán funkci zpětného volání?|  
|---------------------------------------------|------------------------------------------|  
|Prvek se přidá za původní délku pole.|Ne.|  
|Prvek vyplní chybějící prvky pole.|Ano, pokud tento index nebyl dosud předán funkci zpětného volání.|  
|Prvek se změní.|Ano, pokud tento prvek nebyl dosud předán funkci zpětného volání.|  
|Prvek je odstraněn z pole.|Ne, pokud tento prvek již nebyl předán funkci zpětného volání.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `forEach` metoda.  
  
```JavaScript  
// Define the callback function.  
function ShowResults(value, index, ar) {  
    document.write("value: " + value);  
    document.write(" index: " + index);  
    document.write("<br />");  
}  
  
// Create an array.  
var letters = ['ab', 'cd', 'ef'];  
  
// Call the ShowResults callback function for each  
// array element.  
letters.forEach(ShowResults);  
  
// Output:  
//  value: ab index: 0   
//  value: cd index: 1   
//  value: ef index: 2   
```  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu `callbackfn` argument obsahuje kód funkce zpětného volání.  
  
```JavaScript  
// Create an array.  
var numbers = [10, 11, 12];  
  
// Call the addNumber callback function for each array element.  
var sum = 0;  
numbers.forEach(  
    function addNumber(value) { sum += value; }  
);  
  
document.write(sum);  
// Output: 33  
  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `thisArg` argument, který určuje objekt, který lze odkazovat pomocí `this` – klíčové slovo.  
  
```JavaScript  
// Define the object that contains the callback function.  
var obj = {  
    showResults: function(value, index) {  
        // Call calcSquare by using the this value.  
        var squared = this.calcSquare(value);  
  
        document.write("value: " + value);  
        document.write(" index: " + index);  
        document.write(" squared: " + squared);  
        document.write("<br />");  
    },  
    calcSquare: function(x) { return x * x }  
};  
  
// Define an array.  
var numbers = [5, 6];  
  
// Call the showResults callback function for each array element.  
// The obj is the this value within the   
// callback function.  
numbers.forEach(obj.showResults, obj);  
  
// Embed the callback function in the forEach statement.  
// The obj argument is the this value within the obj object.  
// The output is the same as for the previous statement.  
numbers.forEach(function(value, index) { this.showResults(value, index) }, obj);  
  
// Output:  
//  value: 5 index: 0 squared: 25  
//  value: 6 index: 1 squared: 36  
//  value: 5 index: 0 squared: 25  
//  value: 6 index: 1 squared: 36  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Filter – metoda (pole)](../../javascript/reference/filter-method-array-javascript.md)   
 [map – metoda (pole)](../../javascript/reference/map-method-array-javascript.md)   
 [SOME – metoda (pole)](../../javascript/reference/some-method-array-javascript.md)   
 [Array – objekt](../../javascript/reference/array-object-javascript.md)   
 [Použití polí](../../javascript/advanced/using-arrays-javascript.md)   
 [Hilo JavaScript ukázkovou aplikaci (pro Windows Store)](http://hilojs.codeplex.com/SourceControl/latest)