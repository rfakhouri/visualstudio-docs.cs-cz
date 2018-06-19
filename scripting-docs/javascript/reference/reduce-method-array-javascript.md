---
title: reduce – metoda (pole) (JavaScript) | Microsoft Docs
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
- callback function, reduce method [JavaScript]
- arrays [JavaScript], reduce method
- reduce method [JavaScript]
ms.assetid: 48d069e0-e083-494f-86d5-d459d2377dc5
caps.latest.revision: 21
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d99f92d90885f26b19392b476ee64ae17bd40aed
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
ms.locfileid: "34264773"
---
# <a name="reduce-method-array-javascript"></a>reduce – metoda (Pole) (JavaScript)
Volání funkce zadaný zpětného volání pro všechny elementy pole. Vrácená hodnota funkce zpětného volání je akumulovaný výsledek poskytnutý jako argument v dalším volání funkce zpětného volání.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
array1.reduce(callbackfn[, initialValue])  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Definice|  
|---------------|----------------|  
|`array1`|Požadováno. Objekt Array.|  
|`callbackfn`|Požadováno. Funkce, která přijímá až čtyři argumenty. `reduce` Volání metod `callbackfn` funkce jednou pro každý prvek v poli.|  
|`initialValue`|Volitelné. Pokud `initialValue` je zadána, je používán jako počáteční hodnota zahájíte nahromadění. První volání `callbackfn` funkce poskytuje tuto hodnotu jako argument místo hodnota pole.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Akumulovaná výsledek od posledního volání funkce zpětného volání.  
  
## <a name="exceptions"></a>Výjimky  
 A `TypeError` je vyvolána výjimka, když je splněna jedna z následujících podmínek:  
  
-   `callbackfn` Argument není objekt funkce.  
  
-   Pole neobsahuje žádné elementy a `initialValue` není k dispozici.  
  
## <a name="remarks"></a>Poznámky  
 Pokud `initialValue` je k dispozici, `reduce` volání metod `callbackfn` funkce jednou pro každý prvek v poli ve vzestupném pořadí index. Pokud `initialValue` není k dispozici, `reduce` volání metod `callbackfn` funkce pro každý element, počínaje druhý prvkem.  
  
 Návratová hodnota funkce zpětného volání k dispozici jako `accumulator` argument na další volání funkce zpětného volání. Návratová hodnota poslední volání funkce zpětného volání se vrátí hodnotu, která `reduce` metoda.  
  
 Funkce zpětného volání není volána pro chybějící prvky pole.  
  
> [!NOTE]
>  [Reduceright – metoda (Array)](../../javascript/reference/reduceright-method-array-javascript.md) zpracovává elementů v sestupném pořadí index.  
  
## <a name="callback-function-syntax"></a>Syntaxe funkce zpětného volání  
 Syntaxe funkce zpětného volání je následující:  
  
 `function callbackfn(accumulator, currentValue, currentIndex, array1)`  
  
 Funkce zpětného volání můžou deklarovat pomocí až čtyři parametry.  
  
 V následující tabulce jsou uvedeny parametry funkce zpětného volání.  
  
|Argument zpětného volání|Definice|  
|-----------------------|----------------|  
|`accumulator`|Hodnota z předchozího volání funkce zpětného volání. Pokud `initialValue` zajišťuje `reduce` metody `accumulator` je `initialValue` prvním je tato funkce volána.|  
|`currentValue`|Hodnota aktuálního pole elementu.|  
|`currentIndex`|Číselný index aktuálního elementu pole.|  
|`array1`|Objekt pole obsahující prvek.|  
  
## <a name="first-call-to-the-callback-function"></a>První volání funkce zpětného volání  
 Prvním je volána funkce zpětného volání, hodnoty zadané jako argumenty závisí na tom, zda `reduce` metoda má `initialValue` argument.  
  
 Pokud `initialValue` je poskytnutá metodě snižte:  
  
-   `accumulator` Argument je `initialValue`.  
  
-   `currentValue` Argument je hodnota první prvek v poli.  
  
 Pokud `initialValue` není k dispozici:  
  
-   `accumulator` Argument je hodnota první prvek v poli.  
  
-   `currentValue` Argument je hodnota v poli druhý elementu.  
  
## <a name="modifying-the-array-object"></a>Úprava objektu pole  
 Objekt pole může být upraven funkcí zpětného volání.  
  
 Následující tabulka popisuje výsledky změnu objekt array po `reduce` metoda spustí.  
  
|Podmínka po `reduce` spustí – metoda|Byl prvek předán funkci zpětného volání?|  
|------------------------------------------------|------------------------------------------|  
|Prvek se přidá za původní délku pole.|Ne.|  
|Prvek vyplní chybějící prvky pole.|Ano, pokud tento index nebyl dosud předán funkci zpětného volání.|  
|Prvek se změní.|Ano, pokud tento prvek nebyl dosud předán funkci zpětného volání.|  
|Prvek je odstraněn z pole.|Ne, pokud tento prvek již nebyl předán funkci zpětného volání.|  
  
## <a name="example"></a>Příklad  
 Následující příklad zřetězí pole hodnot do řetězce, hodnoty se oddělení "::". Protože je zadána žádná počáteční hodnota `reduce` metoda, první volání funkce zpětného volání má "abc" jako `accumulator` argument a "def" jako `currentValue` argument.  
  
```JavaScript  
// Define the callback function.  
function appendCurrent (accumulator, currentValue) {  
    return accumulator + "::" + currentValue;  
    }  
  
// Create an array.  
var elements = ["abc", "def", 123, 456];  
  
// Call the reduce method, which calls the callback function  
// for each array element.  
var result = elements.reduce(appendCurrent);  
  
document.write(result);  
  
// Output:  
//  abc::def::123::456  
  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad přidá hodnoty pole po byla zaokrouhlena. `reduce` Metoda je volána s počáteční hodnotou 0.  
  
```JavaScript  
// Define the callback function.  
function addRounded (accumulator, currentValue) {  
    return accumulator + Math.round(currentValue);  
    }  
  
// Create an array.  
var numbers = [10.9, 15.4, 0.5];  
  
// Call the reduce method, starting with an initial value of 0.  
var result = numbers.reduce(addRounded, 0);  
  
document.write (result);  
// Output: 27  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad přidá hodnoty v matici. `currentIndex` a `array1` parametry se používají ve funkci zpětného volání.  
  
```JavaScript  
function addDigitValue(accumulator, currentDigit, currentIndex, array) {  
    var exponent = (array.length - 1) - currentIndex;  
    var digitValue = currentDigit * Math.pow(10, exponent);  
    return accumulator + digitValue;  
    }  
  
var digits = [4, 1, 2, 5];  
  
// Determine an integer that is computed from values in the array.  
var result = digits.reduce(addDigitValue, 0);  
  
document.write (result);  
// Output: 4125  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad načte pole, které obsahuje pouze hodnoty, které jsou v rozmezí od 1 do 10 v jiné pole. Počáteční hodnota poskytnutá `reduce` metoda je prázdné pole.  
  
```JavaScript  
function Process(accumulatedArray, currentValue) {  
    // If currentValue is between 1 and 10,   
    // append currentValue to the array.  
    var nextArray;  
    if (currentValue >= 1 && currentValue <= 10)  
        nextArray = accumulatedArray.concat(currentValue);  
    else  
        nextArray = accumulatedArray;  
  
    // If this is not the last call by the reduce method,  
    // the returned array is accumulatedArray on the next call.  
    // If this is the last call by the reduce method, the  
    // returned array is the return value of the reduce method.  
    return nextArray;  
}  
  
// Create an array.  
var numbers = [20, 1, -5, 6, 50, 3];  
  
// Call the reduce method, starting with an initial empty array.  
var emptyArray = new Array();  
var resultArray = numbers.reduce(Process, emptyArray);  
  
document.write("result array=" + resultArray);  
  
// Output:  
// result array=1,6,3  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [reduceRight – metoda (Array)](../../javascript/reference/reduceright-method-array-javascript.md)
