---
title: "SOME – metoda (pole) (JavaScript) | Microsoft Docs"
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
- arrays [JavaScript], some method
- some method [JavaScript]
ms.assetid: 7b6822f9-c406-4f4e-bfec-a93459745992
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ba3f855c61daac511bcf7aca6b47f643dda93313
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="some-method-array-javascript"></a>some – metoda (Pole) (JavaScript)
Určuje, zda zadaný zpětného volání funkce vrátí hodnotu `true` pro libovolný element pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
array1.some(callbackfn[, thisArg])  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Definice|  
|---------------|----------------|  
|`array1`|Požadováno. Objekt Array.|  
|`callbackfn`|Požadováno. Funkce, která přijímá až tři argumenty. `some` Volání metod `callbackfn` funkci pro každý prvek v `array1` dokud `callbackfn` vrátí `true`, nebo až do ukončení tohoto pole.|  
|`thisArg`|Volitelné. Objekt, ke kterému `this` – klíčové slovo najdete v `callbackfn` funkce. Pokud `thisArg` je vynechán, `undefined` slouží jako `this` hodnotu.|  
  
## <a name="return-value"></a>Návratová hodnota  
 `true`Pokud `callbackfn` funkce vrátí `true` pro libovolný element pole; jinak `false`.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud `callbackfn` argument není objekt funkce `TypeError` je vyvolána výjimka.  
  
## <a name="remarks"></a>Poznámky  
 `some` Volání metod `callbackfn` funkce pro každý element pole, ve vzestupném pořadí index, dokud `callbackfn` funkce vrátí `true`. Pokud element, který způsobí, že `callbackfn` vrátit `true` nenajde, `some` metoda hned vrátí `true`. Pokud zpětné volání nevrátí `true` u libovolného elementu `some` metoda vrátí `false`.  
  
 Funkce zpětného volání není volána pro chybějící prvky pole.  
  
 Kromě pole objektů `some` metodu lze použít objektem, který má `length` vlastnost a že má indexované podle čísel názvy vlastností.  
  
> [!NOTE]
>  Můžete použít [every – metoda (pole)](../../javascript/reference/every-method-array-javascript.md) zkontrolujte, zda funkce zpětného volání vrátí `true` pro všechny elementy pole.  
  
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
  
 Následující tabulka popisuje výsledky změnu objekt array po `some` metoda spustí.  
  
|Podmínka po `some` spustí – metoda|Byl prvek předán funkci zpětného volání?|  
|----------------------------------------------|------------------------------------------|  
|Prvek se přidá za původní délku pole.|Ne.|  
|Prvek vyplní chybějící prvky pole.|Ano, pokud tento index nebyl dosud předán funkci zpětného volání.|  
|Prvek se změní.|Ano, pokud tento prvek nebyl dosud předán funkci zpětného volání.|  
|Prvek je odstraněn z pole.|Ne, pokud tento prvek již nebyl předán funkci zpětného volání.|  
  
## <a name="example"></a>Příklad  
 Následující příklad používá `some` metodu za účelem zjištění, zda všechny elementy v pole jsou i.  
  
```JavaScript  
// The callback function.  
function CheckIfEven(value, index, ar) {  
    if (value % 2 == 0)  
        return true;  
}  
  
var numbers = [1, 15, 4, 10, 11, 22];  
  
var evens = numbers.some(CheckIfEven);  
document.write(evens);  
  
// Output:  
// true  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak používat `thisArg` parametr, který určuje objekt, ke kterému `this` – klíčové slovo se může vztahovat. Kontroluje, zda číslům v pole jsou mimo rozsah od předaný objekt  
  
```JavaScript  
// Create a function that returns true if the value is   
// outside the range.  
var isOutsideRange = function (value) {  
    return value < this.minimum || value > this.maximum;  
}  
  
// Create an array of numbers.  
var numbers = [6, 12, 16, 22, -12];  
  
// The range object is to be the 'this' object.  
var range = { minimum: 10, maximum: 20 };  
  
document.write(numbers.some(isOutsideRange, range));  
  
// Output: true  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [EVERY – metoda (pole)](../../javascript/reference/every-method-array-javascript.md)   
 [Filter – metoda (pole)](../../javascript/reference/filter-method-array-javascript.md)   
 [map – metoda (pole)](../../javascript/reference/map-method-array-javascript.md)