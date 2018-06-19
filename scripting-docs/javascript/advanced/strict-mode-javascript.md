---
title: Striktní režim (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT1038
- VS.WebClient.Help.SCRIPT1050
- VS.WebClient.Help.SCRIPT1042
- VS.WebClient.Help.SCRIPT1041
- VS.WebClient.Help.SCRIPT1046
- VS.WebClient.Help.SCRIPT1045
- VS.WebClient.Help.SCRIPT1037
- VS.WebClient.Help.SCRIPT1039
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- strict mode
- use strict
ms.assetid: 0f27022a-f41c-4504-965c-5a2701f342cd
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 77ee7d54dd265026b2bf4c9af52a71cccf9a7675
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789261"
---
# <a name="strict-mode-javascript"></a>Striktní režim (JavaScript)
Striktní režim je způsob, jak zavést lepší kontrolu chyb do vašeho kódu. Při použití striktní režim můžete nelze, například použít implicitně deklarované proměnné, nebo přiřadit hodnotu vlastnosti jen pro čtení nebo přidání vlastnosti do objektu, který není rozšiřitelný. Omezení jsou uvedeny v [omezení kódu v striktní režim](../../javascript/advanced/strict-mode-javascript.md#rest) později v tomto tématu. Další informace o striktní režim najdete v tématu [specifikace jazyka ECMAScript, 5. edice](http://www.ecma-international.org/publications/standards/Ecma-262.htm).  
  
> [!WARNING]
>  Striktní režim není podporován ve verzích aplikace Internet Explorer starších než Internet Explorer 10.  
  
## <a name="declaring-strict-mode"></a>Deklarování striktní režim  
 Striktní režim můžou deklarovat přidáním `"use strict";` na začátku souboru, programu nebo funkce. Tento druh deklarace se označuje jako *direktivy prologu*. Striktní režim deklarace oboru závisí na jeho kontextu. Pokud je deklarovaná v globálním kontextu (mimo rozsah funkce), všechny kód v programu je v striktní režim. Pokud je deklarovaná ve funkci, všechny kód ve funkci je v striktní režim. Například v následujícím příkladu je celý kód v striktní režim a deklarace proměnné mimo funkci způsobuje chybu syntaxe "Proměnné není definovaná v striktní režim."  
  
```JavaScript  
"use strict";  
function testFunction(){  
    var testvar = 4;  
    return testvar;  
}  
  
// This causes a syntax error.  
testvar = 5;  
  
```  
  
 V následujícím příkladu, pouze kód uvnitř `testFunction` v striktní režim. Deklarace proměnné mimo funkci nezpůsobí chybu syntaxe, ale nemá deklaraci uvnitř funkce.  
  
```JavaScript  
function testFunction(){  
    "use strict";  
    // This causes a syntax error.  
    testvar = 4;  
    return testvar;  
}  
testvar = 5;  
  
```  
  
<a name="rest"></a>   
## <a name="restrictions-on-code-in-strict-mode"></a>Omezení kódu v striktní režim  
 Následující tabulka uvádí nejdůležitější omezení, které se vztahují v striktní režim.  
  
|||||  
|-|-|-|-|  
|**Jazyk – element**|**Omezení**|**Chyba**|**Příklad**|  
|Proměnná|Použití proměnné bez deklarace ho.|SCRIPT5042: Proměnná není definovaná v striktní režim|`testvar = 4;`|  
|Vlastnost jen pro čtení|Zápis do vlastnosti jen pro čtení.|SCRIPT5045: Přiřazení vlastnosti jen pro čtení, není povolené v striktní režim|`var testObj = Object.defineProperties({}, {     prop1: {         value: 10,         writable: false // by default     },     prop2: {         get: function () {         }     } }); testObj.prop1 = 20;  testObj.prop2 = 30;`|  
|Bez extensible vlastnost|Přidání vlastnosti do objektu jejichž `extensible` je nastavena na hodnotu `false`.|SCRIPT5046: Nelze vytvořit vlastnost pro objekt extensible|`var testObj = new Object();  Object.preventExtensions(testObj);  testObj.name = "Bob";`|  
|`delete`|Odstranění proměnné, funkci nebo v argumentu.<br /><br /> Odstraňování vlastnost jejichž `configurable` je nastavena na hodnotu `false`.|SCRIPT1045: Volání odstraníte \<výraz > není povolen v striktní režim|`var testvar = 15; function testFunc() {}; delete testvar; delete testFunc;  Object.defineProperty(testObj, "testvar", {     value: 10,     configurable: false     }); delete testObj.testvar;`|  
|Duplikování vlastnost|Definování vlastnosti více než jednou v objekt literálu.|SCRIPT1046: Několik definic vlastnosti není povoleno v striktní režim|`var testObj = {     prop1: 10,     prop2: 15,     prop1: 20 };`|  
|Duplikování název parametru|Použití více než jednou. název parametru ve funkci.|SCRIPT1038: Duplicitní formální parametr názvy nejsou povoleny v striktní režim|`function testFunc(param1, param1) {     return 1; };`|  
|Budoucí vyhrazená slova|Pomocí budoucí rezervované klíčové slovo jako název proměnné nebo funkce.|SCRIPT1050: Použití budoucího rezervovaného slova pro identifikátor je neplatné. Název identifikátoru je vyhrazená v striktní režim.|-                      `implements`<br /><br /> -                      `interface`<br /><br /> -                      `package`<br /><br /> -                      `private`<br /><br /> -                      `protected`<br /><br /> -                      `public`<br /><br /> -                      `static`<br /><br /> -                      `yield`|  
|Octals|Přiřazování osmičkovou hodnotu číselný literál nebo pokus o použití řídicí na osmičkovou hodnotu.|SCRIPT1039: Osmičkové literály číselné a řídicí znaky nejsou povoleny v striktní režim|`var testoctal = 010; var testescape = \010;`|  
|`this`|Hodnota `this` není převést na objekt globální, když je `null` nebo `undefined`.||`function testFunc() {     return this; } var testvar = testFunc();`<br /><br /> V režimu – striktní, hodnota `testvar` je globální objekt, ale v striktní režim hodnota je `undefined`.|  
|`eval`jako identifikátor|Řetězec "zkušební verze" nelze použít jako identifikátor (název proměnné nebo funkce, název parametru a tak dále).||`var eval = 10;`|  
|Funkce deklarována uvnitř příkazu nebo bloku|Nelze deklarovat funkci uvnitř příkazu nebo bloku.|SCRIPT1047: V striktní režim deklarace funkce nelze vnořit do příkazu nebo bloku. Se může vyskytovat pouze na nejvyšší úrovni nebo přímo v tělo funkce.|`var arr = [1, 2, 3, 4, 5]; var index = null; for (index in arr) {     function myFunc() {}; }`|  
|Proměnná definovaná uvnitř `eval` – funkce|Pokud je proměnná deklarována uvnitř `eval` funkce, se nedají použít mimo této funkce.|SCRIPT1041: Neplatné použití eval v striktní režim|`eval("var testvar = 10"); testvar = 15;`<br /><br /> Nepřímý vyhodnocení je možné, ale stále nemůžete použít proměnná definovaná mimo `eval` funkce.<br /><br /> `var indirectEval = eval; indirectEval("var testvar = 10;"); document.write(testVar);`<br /><br /> Tento kód má za následek chyby SCRIPT5009: 'testVar' není definovaný.|  
|`Arguments`jako identifikátor|Řetězec "argumenty" nelze použít jako identifikátor (název proměnné nebo funkce, název parametru a tak dále).|SCRIPT1042: Neplatné použití 'argumentů' striktní režim|`var arguments = 10;`|  
|`arguments`uvnitř funkce|Nelze změnit hodnoty členů místní `arguments` objektu.||`function testArgs(oneArg) {     arguments[0] = 20; }`<br /><br /> V jiných striktní režim, můžete změnit hodnotu `oneArg` parametr tak, že změníte hodnotu `arguments[0]`tak, aby hodnota obou `oneArg` a `arguments[0]` je 20. V striktní režim, změna hodnoty `arguments[0]` nemá vliv na hodnotu `oneArg`, protože `arguments` objekt je jenom místní kopii.|  
|`arguments.callee`|Není povoleno.||`function (testInt) {     if (testInt-- == 0)         return;     arguments.callee(testInt--); }`|  
|`with`|Není povoleno.|SCRIPT1037: 'with' příkazy nejsou povoleny v striktní režim|`with (Math){     x = cos(3);     y = tan(7); }`|