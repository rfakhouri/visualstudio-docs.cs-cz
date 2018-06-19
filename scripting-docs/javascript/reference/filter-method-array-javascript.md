---
title: Filter – metoda (pole) (JavaScript) | Microsoft Docs
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
- arrays [JavaScript], filter method
- filter method [JavaScript]
ms.assetid: 1d260370-9e6e-43fc-870f-2d35850db7ee
caps.latest.revision: 32
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 33a08fdba38de558dabc749a634fb9b69c52c98a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790842"
---
# <a name="filter-method-array-javascript"></a>filter – metoda (Pole) (JavaScript)
Vrátí elementy pole, které splňují podmínky určené ve funkci zpětného volání.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
array1.filter(callbackfn[, thisArg])  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Definice|  
|---------------|----------------|  
|`array1`|Požadováno. Objekt Array.|  
|`callbackfn`|Požadováno. Funkce, která přijímá až tři argumenty. `filter` Volání metod `callbackfn` funkce jednou pro každý prvek v poli.|  
|`thisArg`|Volitelné. Objekt, ke kterému `this` – klíčové slovo najdete v `callbackfn` funkce. Pokud `thisArg` je vynechán, `undefined` slouží jako `this` hodnotu.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Nové pole, která obsahuje všechny hodnoty, pro které se vrátí funkce zpětného volání `true`. Funkce zpětného volání vrátí-li `false` pro všechny elementy `array1`, délka nové pole je 0.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud `callbackfn` argument není objekt funkce `TypeError` je vyvolána výjimka.  
  
## <a name="remarks"></a>Poznámky  
 `filter` Volání metod `callbackfn` funkce jednou pro každý prvek v poli ve vzestupném pořadí index. Funkce zpětného volání není volána pro chybějící prvky pole.  
  
 Kromě pole objektů `filter` metodu lze použít objektem, který má `length` vlastnost a že má indexované podle čísel názvy vlastností.  
  
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
 `filter` Metoda neupravuje přímo původní pole, ale může upravit funkce zpětného volání. Následující tabulka popisuje výsledky změnu objekt array po `filter` metoda spustí.  
  
|Podmínka po `filter` spustí – metoda|Byl prvek předán funkci zpětného volání?|  
|------------------------------------------------|------------------------------------------|  
|Prvek se přidá za původní délku pole.|Ne.|  
|Prvek vyplní chybějící prvky pole.|Ano, pokud tento index nebyl dosud předán funkci zpětného volání.|  
|Prvek se změní.|Ano, pokud tento prvek nebyl dosud předán funkci zpětného volání.|  
|Prvek je odstraněn z pole.|Ne, pokud tento prvek již nebyl předán funkci zpětného volání.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `filter` metoda.  
  
```JavaScript  
// Define a callback function.  
function CheckIfPrime(value, index, ar) {  
    high = Math.floor(Math.sqrt(value)) + 1;  
  
    for (var div = 2; div <= high; div++) {  
        if (value % div == 0) {  
            return false;  
        }  
    }   
    return true;  
}  
  
// Create the original array.  
var numbers = [31, 33, 35, 37, 39, 41, 43, 45, 47, 49, 51, 53];  
  
// Get the prime numbers that are in the original array.   
var primes = numbers.filter(CheckIfPrime);  
  
document.write(primes);  
// Output: 31,37,41,43,47,53  
```  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu `callbackfn` argument obsahuje kód funkce zpětného volání.  
  
```JavaScript  
// Create the original array.  
var arr = [5, "element", 10, "the", true];  
  
// Create an array that contains the string  
// values that are in the original array.  
var result = arr.filter(  
    function (value) {  
        return (typeof value === 'string');  
    }  
);  
  
document.write(result);  
// Output: element, the  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad zobrazuje názvy vlastností, které začínají s písmenem "css" v `window` objekt DOM.  
  
```JavaScript  
var filteredNames = Object.getOwnPropertyNames(window).filter(IsC);  
  
    for (i in filteredNames)  
        document.write(filteredNames[i] + "<br/>");  
  
// Check whether the string starts with "css".  
function IsC(value) {  
    var firstChar = value.substr(0, 3);  
    if (firstChar.toLowerCase() == "css")  
        return true;  
    else  
        return false;  
    }  
  
// Output:  
// CSSRule  
// CSSFontFaceRule  
// CSSImportRule  
// CSSMediaRule  
// CSSNamespaceRule  
// CSSPageRule  
// CSSRuleList  
// CSSStyleDeclaration  
// CSSStyleRule  
// CSSStyleSheet  
  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `thisArg` argument, který určuje objekt, ke kterému `this` – klíčové slovo se může vztahovat.  
  
```JavaScript  
var checkNumericRange = function(value) {  
    if (typeof value !== 'number')  
        return false;  
    else   
        return value >= this.minimum && value <= this.maximum;  
}  
  
var numbers = [6, 12, "15", 16, "the", -12];  
  
// The obj argument enables use of the this value  
// within the callback function.  
var obj = { minimum: 10, maximum: 20 }  
  
var result = numbers.filter(checkNumericRange, obj);  
  
document.write(result);  
// Output: 12,16  
  
```  
  
## <a name="example"></a>Příklad  
 `filter` Metoda lze použít na řetězec místo pole. Následující příklad ukazuje, jak to provést.  
  
```JavaScript  
// Define a callback function that returns true  
// if the current array element follows a space  
// or is the first character.  
function CheckValue(value, index, ar) {  
    if (index == 0)  
        return true;  
    else  
        return ar[index - 1] === " ";  
}  
  
// Create a string.  
var sentence = "The quick brown fox jumps over the lazy dog.";   
  
// Create an array that contains all characters that follow a space.  
var subset = [].filter.call(sentence, CheckValue);   
  
// You can use this alternative syntax.  
//var subset = Array.prototype.filter.call(sentence, CheckValue);  
  
document.write(subset);  
// Output: T,q,b,f,j,o,t,l,d  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Array – objekt](../../javascript/reference/array-object-javascript.md)   
 [Použití polí](../../javascript/advanced/using-arrays-javascript.md)   
 [map – metoda (pole)](../../javascript/reference/map-method-array-javascript.md)   
 [foreach – metoda (pole)](../../javascript/reference/foreach-method-array-javascript.md)