---
title: "EVERY – metoda (pole) (JavaScript) | Microsoft Docs"
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
- every method
- arrays [JavaScript], every method
ms.assetid: dc4ee2f8-fb9e-4c9f-af5a-fe836e40ddd1
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4a05263ae45df61c47a3580d474863c8d4ff3dd1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="every-method-array-javascript"></a>every – metoda (Pole) (JavaScript)
Určuje, zda všechny členy pole splňují zadanou test.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
array1.every(callbackfn[, thisArg])  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Definice|  
|---------------|----------------|  
|`array1`|Požadováno. Objekt Array.|  
|`callbackfn`|Požadováno. Funkce, která přijímá až tři argumenty. `every` Volání metod `callbackfn` funkci pro každý prvek v `array1` dokud `callbackfn` vrátí `false`, nebo až do ukončení tohoto pole.|  
|`thisArg`|Volitelné. Objekt, ke kterému `this` – klíčové slovo najdete v `callbackfn` funkce. Pokud `thisArg` je vynechán, `undefined` slouží jako `this` hodnotu.|  
  
## <a name="return-value"></a>Návratová hodnota  
 `true`Pokud `callbackfn` funkce vrátí `true` pro všechny elementy; pole, jinak hodnota `false`. Pokud je pole nemá žádné elementy, `every` metoda vrátí `true`.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud `callbackfn` argument není objekt funkce `TypeError` je vyvolána výjimka.  
  
## <a name="remarks"></a>Poznámky  
 `every` Volání metod `callbackfn` funkce jednou pro každý element pole, ve vzestupném pořadí index, dokud `callbackfn` funkce vrátí `false`. Pokud element, který způsobí, že `callbackfn` vrátit `false` nenajde, `every` metoda hned vrátí `false`. Jinak `every` metoda vrátí `true`.  
  
 Funkce zpětného volání není volána pro chybějící prvky pole.  
  
 Kromě pole objektů `every` metodu lze použít objektem, který má `length` vlastnost a že má indexované podle čísel názvy vlastností.  
  
> [!NOTE]
>  Můžete použít [some – metoda (pole)](../../javascript/reference/some-method-array-javascript.md) zkontrolujte, zda funkce zpětného volání vrátí `true` pro libovolný element pole.  
  
## <a name="callback-function-syntax"></a>Syntaxe funkce zpětného volání  
 Syntaxe funkce zpětného volání je následující:  
  
 `function callbackfn(value, index, array1)`  
  
 Funkce zpětného volání s až tři parametry můžou deklarovat.  
  
 V následující tabulce jsou uvedeny parametry funkce zpětného volání.  
  
|Parametr zpětného volání|Definice|  
|------------------------|----------------|  
|`value`|Hodnota prvku pole.|  
|`index`|Číselný index prvku pole.|  
|`array1`|Objekt pole obsahující prvek.|  
  
## <a name="modifying-the-array-object"></a>Úprava objektu pole  
 Objekt pole může být upraven funkcí zpětného volání.  
  
 Následující tabulka popisuje výsledky změnu objekt array po `every` metoda spustí.  
  
|Podmínka po `every` spustí – metoda|Byl prvek předán funkci zpětného volání?|  
|-----------------------------------------------|------------------------------------------|  
|Prvek se přidá za původní délku pole.|Ne.|  
|Prvek vyplní chybějící prvky pole.|Ano, pokud tento index nebyl dosud předán funkci zpětného volání.|  
|Prvek se změní.|Ano, pokud tento prvek nebyl dosud předán funkci zpětného volání.|  
|Prvek je odstraněn z pole.|Ne, pokud tento prvek již nebyl předán funkci zpětného volání.|  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `every` metoda.  
  
```JavaScript  
// Define the callback function.  
function CheckIfEven(value, index, ar) {  
    document.write(value + " ");  
  
    if (value % 2 == 0)  
        return true;  
    else  
        return false;  
}  
  
// Create an array.  
var numbers = [2, 4, 5, 6, 8];  
  
// Check whether the callback function returns true for all of the  
// array values.  
if (numbers.every(CheckIfEven))  
    document.write("All are even.");  
else  
    document.write("Some are not even.");  
  
// Output:  
// 2 4 5 Some are not even.  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `thisArg` argument, který určuje objekt, ke kterému `this` – klíčové slovo se může vztahovat.  
  
```JavaScript  
// Create a function that returns true if the value is  
// numeric and within range.  
var checkNumericRange = function(value) {  
    if (typeof value !== 'number')  
        return false;  
    else   
        return value >= this.minimum && value <= this.maximum;  
}  
  
// Create an array of numbers.  
var numbers = [10, 15, 19];  
  
// Check whether the callback function returns true for  
// all of the array values.  
// The obj argument enables use of the this value  
// within the callback function.  
  
var obj = { minimum: 10, maximum: 20 }  
  
if (numbers.every(checkNumericRange, obj))  
    document.write ("All are within range.");  
else  
    document.write ("Some are not within range.");  
  
// Output:  
//   All are within range.  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [SOME – metoda (pole)](../../javascript/reference/some-method-array-javascript.md)   
 [Filter – metoda (pole)](../../javascript/reference/filter-method-array-javascript.md)   
 [Array – objekt](../../javascript/reference/array-object-javascript.md)   
 [Použití polí](../../javascript/advanced/using-arrays-javascript.md)