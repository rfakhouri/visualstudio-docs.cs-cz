---
title: "map – metoda (pole) (JavaScript) | Microsoft Docs"
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
- map method [JavaScript]
- arrays [JavaScript], map method
ms.assetid: 500dc4f8-d73d-4a28-a5b8-c9bd5674ea36
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 609d9c88000a7a30fe8edc03b52df032f7d19ba9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="map-method-array-javascript"></a>map – metoda (Pole) (JavaScript)
Volá definovanou funkci zpětného volání na každý prvek pole a vrátí pole obsahující výsledky.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
array1.map(callbackfn[, thisArg])  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Definice|  
|---------------|----------------|  
|`array1`|Požadováno. Objekt Array.|  
|`callbackfn`|Požadováno. Funkce, která přijímá až tři argumenty. `map` Volání metod `callbackfn` funkce jednou pro každý prvek v poli.|  
|`thisArg`|Volitelné. Objekt, ke kterému `this` – klíčové slovo najdete v `callbackfn` funkce. Pokud `thisArg` je vynechán, `undefined` slouží jako `this` hodnotu.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Nové pole, ve kterém je každý prvek návratovou hodnotou funkce zpětného volání pro odpovídající prvek původního pole.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud `callbackfn` argument není objekt funkce `TypeError` je vyvolána výjimka.  
  
## <a name="remarks"></a>Poznámky  
 `map` Volání metod `callbackfn` funkce jednou pro každý prvek v poli ve vzestupném pořadí index. Funkce zpětného volání není volána pro chybějící prvky pole.  
  
 Kromě pole objektů `map` metodu lze použít objektem, který má `length` vlastnost a že má indexované podle čísel názvy vlastností.  
  
## <a name="callback-function-syntax"></a>Syntaxe funkce zpětného volání  
 Syntaxe funkce zpětného volání je následující:  
  
 `function callbackfn(value, index, array1)`  
  
 Funkci zpětného volání můžete deklarovat pomocí až tří parametrů.  
  
 V následující tabulce jsou uvedeny parametry funkce zpětného volání.  
  
|Argument zpětného volání|Definice|  
|-----------------------|----------------|  
|`value`|Hodnota prvku pole.|  
|`index`|Číselný index prvku pole.|  
|`array1`|Objekt pole obsahující prvek.|  
  
## <a name="modifying-the-array-object"></a>Úprava objektu pole  
 Objekt pole může být upraven funkcí zpětného volání.  
  
 Následující tabulka popisuje výsledky změnu objekt array po `map` metoda spustí.  
  
|Podmínka po `map` spustí – metoda|Byl prvek předán funkci zpětného volání?|  
|---------------------------------------------|------------------------------------------|  
|Prvek se přidá za původní délku pole.|Ne.|  
|Prvek vyplní chybějící prvky pole.|Ano, pokud tento index nebyl dosud předán funkci zpětného volání.|  
|Prvek se změní.|Ano, pokud tento prvek nebyl dosud předán funkci zpětného volání.|  
|Prvek je odstraněn z pole.|Ne, pokud tento prvek již nebyl předán funkci zpětného volání.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `map` metoda.  
  
```JavaScript  
// Define the callback function.  
function AreaOfCircle(radius) {  
    var area = Math.PI * (radius * radius);  
    return area.toFixed(0);  
}  
  
// Create an array.  
var radii = [10, 20, 30];  
  
// Get the areas from the radii.  
var areas = radii.map(AreaOfCircle);  
  
document.write(areas);  
  
// Output:  
// 314,1257,2827  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `thisArg` argument, který určuje objekt, ke kterému `this` – klíčové slovo se může vztahovat.  
  
```JavaScript  
// Define an object that contains a divisor property and  
// a remainder function.  
var obj = {  
    divisor: 10,  
    remainder: function (value) {  
        return value % this.divisor;  
    }  
}  
  
// Create an array.  
var numbers = [6, 12, 25, 30];  
  
// Get the remainders.  
// The obj argument specifies the this value in the callback function.  
var result = numbers.map(obj.remainder, obj);  
document.write(result);  
  
// Output:  
// 6,2,5,0  
```  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu, integrované[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] metoda se používá jako funkce zpětného volání.  
  
```JavaScript  
// Apply Math.sqrt(value) to each element in an array.  
var numbers = [9, 16];  
var result = numbers.map(Math.sqrt);  
  
document.write(result);  
// Output: 3,4  
```  
  
## <a name="example"></a>Příklad  
 `map` Metoda lze použít na řetězec. Toto dokládá následující příklad.  
  
```JavaScript  
// Define the callback function.  
function threeChars(value, index, str) {  
    // Create a string that contains the previous, current,  
    // and next character.  
    return str.substring(index - 1, index + 2);  
}  
  
// Create a string.  
var word = "Thursday";  
  
// Apply the map method to the string.  
// Each array element in the result contains a string that  
// has the previous, current, and next character.  
// The commented out statement shows an alternative syntax.  
var result = [].map.call(word, threeChars);  
// var result = Array.prototype.map.call(word, threeChars);  
  
document.write(result);  
  
// Output:  
// Th,Thu,hur,urs,rsd,sda,day,ay  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Metody jazyka JavaScript](../../javascript/reference/javascript-methods.md)   
 [Array – objekt](../../javascript/reference/array-object-javascript.md)   
 [Použití polí](../../javascript/advanced/using-arrays-javascript.md)   
 [Filter – metoda (pole)](../../javascript/reference/filter-method-array-javascript.md)   
 [foreach – metoda (pole)](../../javascript/reference/foreach-method-array-javascript.md)   
 [Hilo JavaScript ukázkovou aplikaci (pro Windows Store)](http://hilojs.codeplex.com/SourceControl/latest)