---
title: "Operátory (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- JavaScript, operators
ms.assetid: b8602b69-aba9-46e8-86e1-cb533ad41410
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a3068a609da2468c59066ccd38f6de87cef1ed17
ms.sourcegitcommit: 873c0e1a31def013bcca1b0caa0eb0249de89bec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2018
---
# <a name="operators-javascript"></a>Operátory (JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)] má plný rozsah operátory, včetně aritmetické logické, bitový, přiřazení a také některé různé operátory. Vysvětlení a příklady naleznete v tématech na konkrétní operátory.  
  
## <a name="computational-operators"></a>Výpočetní operátory  
  
|Popis|Symbol|  
|-----------------|------------|  
|[Unární negace](../javascript/reference/subtraction-operator-decrement-javascript.md)|-|  
|[Přírůstek](../javascript/reference/increment-and-decrement-operators-javascript.md)|++|  
|[Snížení](../javascript/reference/increment-and-decrement-operators-javascript.md)|--|  
|[Násobení](../javascript/reference/multiplication-operator-decrement-javascript.md)|*|  
|[dělení](../javascript/reference/division-operator-decrement-javascript.md)|/|  
|[Zbývající aritmetické](../javascript/reference/modulus-operator-decrementjavascript.md)|%|  
|[Přidání](../javascript/reference/addition-operator-decrement-javascript.md)|+|  
|[Odčítání](../javascript/reference/subtraction-operator-decrement-javascript.md)|-|  
  
## <a name="logical-operators"></a>Logické operátory  
  
|Popis|Symbol|  
|-----------------|------------|  
|[Logická NEGACE](../javascript/reference/logical-not-operator-decrement-exclpt-javascript.md)|!|  
|[Menší než](../javascript/reference/comparison-operators-javascript.md)|\<|  
|[Větší než](../javascript/reference/comparison-operators-javascript.md)|>|  
|[Menší než nebo rovno](../javascript/reference/comparison-operators-javascript.md)|\<=|  
|[Větší než nebo rovno](../javascript/reference/comparison-operators-javascript.md)|>=|  
|[Rovnosti](../javascript/reference/comparison-operators-javascript.md)|==|  
|[Nerovnosti](../javascript/reference/comparison-operators-javascript.md)|!=|  
|[Logické a](../javascript/reference/logical-and-operator-decrement-javascript.md)|&&|  
|[Logické nebo](../javascript/reference/logical-or-operator-decrement-javascript.md)|&#124;&#124;|  
|[Podmíněné (unární)](../javascript/reference/conditional-ternary-operator-decrement-javascript.md)|?:|  
|[Comma](../javascript/reference/comma-operator-decrement-javascript.md)|,|  
|[Striktní rovnosti](../javascript/reference/comparison-operators-javascript.md)|===|  
|[Přesná nerovnost](../javascript/reference/comparison-operators-javascript.md)|!==|  
  
## <a name="bitwise-operators"></a>Bitové operátory  
  
|Popis|Symbol|  
|-----------------|------------|  
|[Bitový operátor NOT](../javascript/reference/bitwise-not-operator-decrement-tilde-javascript.md)|~|  
|[Bitové posunutí vlevo](../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)|<\<|  
|[Bitového posunutí doprava](../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)|>>|  
|[Posunutí doprava bez znaménka](../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)|>>>|  
|[Bitový operátor AND](../javascript/reference/bitwise-and-operator-decrement-javascript.md)|&|  
|[Bitové operace XOR](../javascript/reference/bitwise-xor-operator-decrement-hat-javascript.md)|^|  
|[Bitový operátor OR](../javascript/reference/bitwise-or-operator-decrement-javascript.md)|&#124;|  
  
## <a name="assignment-operators"></a>Operátory přiřazení  
  
|Popis|Symbol|  
|-----------------|------------|  
|[Přiřazení](../javascript/reference/assignment-operator-decrement-equal-javascript.md)|=|  
|[Složené přiřazení](../javascript/reference/compound-assignment-operators-javascript.md)|*OP*= (třeba += a & =)|  
  
## <a name="miscellaneous-operators"></a>Různé operátory  
  
|Popis|Symbol|  
|-----------------|------------|  
|[delete](../javascript/reference/delete-operator-decrementjavascript.md)|Odstranit|  
|[typeof](../javascript/reference/typeof-operator-decrementjavascript.md)|typeof|  
|[void](../javascript/reference/void-operator-decrementjavascript.md)|void|  
|[instanceof](../javascript/reference/instanceof-operator-decrementjavascript.md)|instanceof|  
|[new](../javascript/reference/new-operator-decrementjavascript.md)|new|  
|[in](../javascript/reference/in-operator-decrementjavascript.md)|in|  
  
## <a name="equality-and-strict-equality"></a>Rovnost a přísná rovnost  
 Rozdíl mezi == (rovnosti) a === (striktní rovnosti) je, že bude operátor rovnosti coerce hodnoty různých typů před vyhledáním rovnosti. Například porovnání řetězce "1" s číslem 1 se porovná jako true. Operátor rovnosti striktní nebude na druhé straně coerce hodnoty pro různé typy, a proto nebude porovnat řetězec "1" jako stejná jako číslo 1.  
  
 Primitivní řetězců, čísel a logické hodnoty se porovná s hodnotou. Pokud mají stejnou hodnotu, jsou stejné. Objekty (včetně `Array`, `Function`, `String`, **číslo**, `Boolean`, **chyba**, `Date` a `RegExp` objekty) porovnat odkazem. I v případě, že dvě proměnné, které z těchto typů mají stejnou hodnotu, jsou stejné, pouze pokud odkazují přesně stejný objekt.  
  
 Příklad:  
  
```JavaScript  
// Two strings with the same value.  
var string1 = "Hello";  
var string2 = "Hello";  
  
// Two String objects with the same value.  
var StringObject1 = new String(string1);  
var StringObject2 = new String(string2);  
  
if (string1 == string2)  
    document.write("string1 is equal to string2 <br/>");  
  
if (StringObject1 != StringObject2)  
    document.write("StringObject1 is not equal to StringObject2 <br/>");  
  
// To compare the values of String objects, use the toString() or valueOf() methods.  
if (StringObject1.valueOf() == StringObject2.valueOf())  
    document.write("The value of StringObject1 is equal to the value of StringObject2");  
  
//Output:  
// string1 is equal to string2   
// StringObject1 is not equal to StringObject2   
// The value of StringObject1 is equal to the value of StringObject2  
  
```