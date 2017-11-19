---
title: "reduceright – metoda (Array) (JavaScript) | Microsoft Docs"
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
- arrays [JavaScript], reduceRight method
- reduceRight method [JavaScript]
ms.assetid: 85963761-da11-407c-8bce-278c930e61bd
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0d7fd2794157eadacefa7404f9333c51aed9425c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="reduceright-method-array-javascript"></a>reduceRight – metoda (Array) (JavaScript)
Volání funkce zadaný zpětného volání pro všechny elementy pole, v sestupném pořadí. Vrácená hodnota funkce zpětného volání je akumulovaný výsledek poskytnutý jako argument v dalším volání funkce zpětného volání.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
array1.reduceRight(callbackfn[, initialValue])  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Definice|  
|---------------|----------------|  
|`array1`|Požadováno. Objekt Array.|  
|`callbackfn`|Požadováno. Funkce, která přijímá až čtyři argumenty. `reduceRight` Volání metod `callbackfn` funkce jednou pro každý prvek v poli.|  
|`initialValue`|Volitelné. Pokud `initialValue` je zadána, je používán jako počáteční hodnota zahájíte nahromadění. První volání `callbackfn` funkce poskytuje tuto hodnotu jako argument místo hodnota pole.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Objekt, který obsahuje Akumulovaná výsledek od posledního volání funkce zpětného volání.  
  
## <a name="exceptions"></a>Výjimky  
 A `TypeError` je vyvolána výjimka, když je splněna jedna z následujících podmínek:  
  
-   `callbackfn` Argument není objekt funkce.  
  
-   Pole neobsahuje žádné elementy a `initialValue` není k dispozici.  
  
## <a name="remarks"></a>Poznámky  
 Pokud `initialValue` je k dispozici, `reduceRight` volání metod `callbackfn` funkce jednou pro každý prvek v poli v sestupném pořadí index. Pokud žádné `initialValue` je k dispozici, `reduceRight` volání metod `callbackfn` funkce pro každý element, počínaje sekundu poslední elementu v sestupném pořadí index.  
  
 Návratová hodnota funkce zpětného volání k dispozici jako `previousValue` argument na další volání funkce zpětného volání. Návratová hodnota poslední volání funkce zpětného volání se vrátí hodnotu, která `reduceRight` metoda.  
  
 Funkce zpětného volání není volána pro chybějící prvky pole.  
  
 Chcete-li accumulate výsledku ve vzestupném pořadí index, použijte [reduce – metoda (pole)](../../javascript/reference/reduce-method-array-javascript.md).  
  
## <a name="callback-function-syntax"></a>Syntaxe funkce zpětného volání  
 Syntaxe funkce zpětného volání je následující:  
  
 `function callbackfn(previousValue, currentValue, currentIndex, array1)`  
  
 Funkce zpětného volání můžou deklarovat pomocí až čtyři parametry.  
  
 V následující tabulce jsou uvedeny parametry funkce zpětného volání.  
  
|Argument zpětného volání|Definice|  
|-----------------------|----------------|  
|`previousValue`|Hodnota z předchozího volání funkce zpětného volání. Pokud `initialValue` zajišťuje `reduceRight` metody `previousValue` je `initialValue` prvním je tato funkce volána.|  
|`currentValue`|Hodnota aktuálního pole elementu.|  
|`currentIndex`|Číselný index aktuálního elementu pole.|  
|`array1`|Objekt pole obsahující prvek.|  
  
## <a name="first-call-to-the-callback-function"></a>První volání funkce zpětného volání  
 Prvním je volána funkce zpětného volání, hodnoty zadané jako argumenty závisí na tom, zda `reduceRight` metoda má `initialValue` argument.  
  
 Pokud `initialValue` zajišťuje `reduceRight` metoda:  
  
-   `previousValue` Argument je `initialValue`.  
  
-   `currentValue` Argument je hodnota v poli posledním elementem.  
  
 Pokud `initialValue` není k dispozici:  
  
-   `previousValue` Argument je hodnota v poli posledním elementem.  
  
-   `currentValue` Argument je hodnota v poli sekundu poslední elementu.  
  
## <a name="modifying-the-array-object"></a>Úprava objektu pole  
 Objekt pole může být upraven funkcí zpětného volání.  
  
 Následující tabulka popisuje výsledky změnu objekt array po `reduceRight` metoda spustí.  
  
|Podmínka po `reduceRight` spustí – metoda|Byl prvek předán funkci zpětného volání?|  
|-----------------------------------------------------|------------------------------------------|  
|Prvek se přidá za původní délku pole.|Ne.|  
|Prvek vyplní chybějící prvky pole.|Ano, pokud tento index nebyl dosud předán funkci zpětného volání.|  
|Prvek se změní.|Ano, pokud tento prvek nebyl dosud předán funkci zpětného volání.|  
|Prvek je odstraněn z pole.|Ne, pokud tento prvek již nebyl předán funkci zpětného volání.|  
  
## <a name="example"></a>Příklad  
 Následující příklad zřetězí pole hodnot do řetězce, hodnoty se oddělení "::". Protože je zadána žádná počáteční hodnota `reduceRight` metoda, první volání funkce zpětného volání má 456 jako `previousValue` argument a 123 jako `currentValue` argument.  
  
```JavaScript  
// Define the callback function.  
function appendCurrent (previousValue, currentValue) {  
    return previousValue + "::" + currentValue;  
    }  
  
// Create an array.  
var elements = ["abc", "def", 123, 456];  
  
// Call the reduceRight method, which calls the callback function  
// for each array element, in descending index order.  
var result = elements.reduceRight(appendCurrent);  
  
document.write(result);  
  
// Output:  
//  456::123::def::abc  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad vyhledá součet kvadratických prvků pole. `reduceRight` Metoda je volána s počáteční hodnotou 0.  
  
```JavaScript  
// Define the callback function.  
function Process(previousValue, currentValue, index, array) {  
    // Add the previous value to the current value squared.  
    var nextValue = previousValue + (currentValue * currentValue);  
  
    // If this is not the last call by the reduceRight method,  
    // the return value is previousValue on the next call.  
    // If this is the last call by the reduceRight method, the  
    // return value is the return value of the reduceRight method.  
    return nextValue;  
}  
  
// Create an array.  
var numbers = [3, 4, 5];  
  
// Call the reduceRight method with an initial value of 0.  
var sumOfSquares = numbers.reduceRight(Process, 0);  
  
document.write("sum of squares=" + sumOfSquares);  
  
// Output:  
//  sum of squares=50  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad načte tyto prvky pole jehož hodnoty jsou mezi 1 a 10. Počáteční hodnota poskytnutá `reduceRight` metoda je prázdné pole.  
  
```JavaScript  
function Process2(previousArray, currentValue) {  
    // If currentValue is between 1 and 10,   
    // append currentValue to the array.  
    var nextArray;  
    if (currentValue >= 1 && currentValue <= 10)  
        nextArray = previousArray.concat(currentValue);  
    else  
        nextArray = previousArray;  
  
    // If this is not the last call by the reduceRight method,  
    // the returned array is previousArray on the next call.  
    // If this is the last call by the reduceRight method, the  
    // returned array is the return value of the reduceRight method.  
    return nextArray;  
}  
  
// Create an array.  
var numbers = [20, 1, -5, 6, 50, 3];  
  
// Call the reduceRight method, starting with an empty array.  
var emptyArray = new Array();  
var resultArray = numbers.reduceRight(Process2, emptyArray);  
  
document.write("result array=" + resultArray);  
  
// Output:  
//  result array=3,6,1  
```  
  
## <a name="example"></a>Příklad  
 `reduceRight` Metoda lze použít na řetězec. Následující příklad ukazuje, jak lze pomocí této metody reverse znaky v řetězci.  
  
```JavaScript  
// Define the callback function.  
function AppendToArray(previousValue, currentValue) {  
    return previousValue + currentValue;  
}  
  
var word = "retupmoc";  
  
// Create a string that reverses the characters of another string.  
// The commented-out statement shows an alternative syntax.  
var result = [].reduceRight.call(word, AppendToArray, "the ");  
// var result = Array.prototype.reduceRight.call(word, AppendToArray, "the ");  
  
document.write(result);  
  
// Output:  
// the computer  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [reduce – metoda (pole)](../../javascript/reference/reduce-method-array-javascript.md)