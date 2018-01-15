---
title: Funkce (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: intrinsic JavaScript functions
ms.assetid: e2a72b5a-3edd-43d8-95e8-91721b38c1c1
caps.latest.revision: "24"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7275985d07f9f564dac98ba39e5ec31618dcaac4
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/13/2018
---
# <a name="functions-javascript"></a>Funkce (JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)]Funkce provádět akce; také se můžete vrátit hodnoty. Jsou to někdy výsledky výpočty nebo porovnání. Funkce se také nazývají "globální metody".  
  
 Funkce kombinovat několik operací v části jeden název. Díky tomu můžete zjednodušit kód. Můžete zapsat sadu příkazů, pojmenujte ji a potom spusťte celý nastavit voláním ho a předání žádné informace, které potřebuje.  
  
 Informace o funkci předat uzavřením informace do závorek za název funkce. Řadu informací, které se budou předávat na funkci se označují jako argumenty nebo parametry. Některé funkce nepřebírají žádné argumenty vůbec, zatímco jiné přijímají jeden nebo více argumentů. V některých funkcí počet argumentů závisí na tom, jak používáte funkci.  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]podporuje dva druhy funkce: ty, které jsou integrované do jazyka a těch, které jste sami vytvořili.  
  
## <a name="built-in-functions"></a>Integrované funkce  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] Jazyk obsahuje několik integrovaných funkcí. Některé umožňují zpracovat výrazy a speciální znaky, zatímco ostatní převod řetězců na numerické hodnoty.  
  
 V tématu [metody jazyka JavaScript](../javascript/reference/javascript-methods.md) informace o těchto integrovaných funkcí.  
  
## <a name="creating-your-own-functions"></a>Vytváření vlastních funkcí  
 Můžete vytvořit své vlastní funkce a použít je tam, kde je potřeba. Definice funkce se skládá z příkazu funkce a blok [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] příkazy.  
  
 **CheckTriplet** funkce v následujícím příkladu přebírá délek stran trojúhelníku jako argumenty. Počítá z nich zda trojúhelníku je pravý trojúhelník kontrolou, jestli tvoří tři číslice Pythagorova trojdílná (druhou mocninu délka přepony trojúhelníku práva je určena součtem kvadratických délek zbývající dvě strany) . Funkce checkTriplet volá ze dvou funkcí, aby skutečné test.  
  
 Všimněte si použití velmi malé množství ("epsilon") jako testování proměnné s plovoucí desetinnou čárkou verze testu. Z důvodu nejasností a zaokrouhlovací chyby s plovoucí desetinnou čárkou výpočty není praktické Ujistěte se, zda tří čísel představovat trojdílná Pythagorova, pokud jsou všechny tři hodnoty v známé jako celá čísla přímé testu. Vzhledem k tomu, že přímý test přesnější, kód v tomto příkladu určuje, zda je vhodné a, pokud se jedná, používá.  
  
```JavaScript  
var epsilon = 0.00000000001; // Some very small number to test against.  
  
// The test function for integers.  
function integerCheck(a, b, c)   
{  
   // The test itself.  
   if ( (a*a) == ((b*b) + (c*c)) )     
      return true;  
  
   return false;  
} // End of the integer checking function.  
  
// The test function for floating-point numbers.  
function floatCheck(a, b, c)     
{  
   // Make the test number.  
   var delta = ((a*a) - ((b*b) + (c*c)))  
  
   // The test requires the absolute value  
   delta = Math.abs(delta);  
  
   // If the difference is less than epsilon, then it's pretty close.  
   if (delta < epsilon)     
      return true;  
  
   return false;  
} // End of the floating-poing check function.  
  
// The triplet checker.   
function checkTriplet(a, b, c)  
{   
   // Create a temporary variable for swapping values  
   var d = 0;   
  
   // First, move the longest side to position "a".  
  
   // Swap a and b if necessary  
   if (b > a)  
   {  
      d = a;  
      a = b;  
      b = d;  
   }  
  
   // Swap a and c if necessary  
   if (c > a)  
   {  
      d = a;  
      a = c;  
      c = d;  
   }  
  
   // Test all 3 values. Are they integers?  
   if (((a % 1) == 0) && ((b % 1) == 0) && ((c % 1) == 0))  
   {   
      // If so, use the precise check.  
      return integerCheck(a, b, c);   
   }  
   else  
   {  
      // If not, get as close as is reasonably possible.  
      return floatCheck(a, b, c);   
   }  
} // End of the triplet check function.  
  
// The next three statements assign sample values for testing purposes.  
var sideA = 5;  
var sideB = 5;  
var sideC = Math.sqrt(50.001);  
  
// Call the function. After the call, 'result' contains the result.  
var result = checkTriplet(sideA, sideB, sideC);  
```  
  
<a name="Arrow"></a>   
## <a name="arrow-functions"></a>Šipka funkce  
 Syntaxe funkce šipku, `=>`, poskytuje rychlou metodou zadávání anonymní funkce. Tady je syntax funkce šipku.  
  
```JavaScript  
([arg] [, arg]) => {  
    statements  
}  
```  
  
 Hodnoty nalevo od šipku, která může být uzavřena v závorkách, zadejte argumenty předaný funkci. Jeden argument funkce nevyžaduje závorek. Pokud jsou v předán žádný argument, je nutné zadat závorky. V definici funkce napravo od šipku může být buď výrazu, například `v + 1`, nebo blok příkazů, které jsou uvedeny ve složených závorkách ({}).  
  
> [!IMPORTANT]
>  Syntaxe funkce šipku je podporována pouze v [!INCLUDE[jsv12text](../javascript/includes/jsv12text-md.md)].  
  
 Nelze použít `new` operátor s funkcí šipku.  
  
 Následující příklady kódu ukazují použití funkce šipku s výrazy jako definice funkcí. V prvním příkladu v je předána jako argument výrazu. V druhém příkladu v a i jsou předané jako argumenty výraz.  
  
```  
var evens = [2, 4, 6, 8];  
  
// Using standard syntax.  
var odds = evens.map(function(v) { return v + 1; });  
  
// Using arrow function syntax.  
// Add one to each value to produce output.  
var odds = evens.map(v => v + 1);  
  
// The following line of code adds the index value to the passed  
// in value to produce output.  
// Note: the second argument to the callback function in the map   
// method is the index value (i).  
var nums = evens.map((v, i) => v + i);  
  
console.log(odds);  
console.log(nums);  
  
// Output:  
// [object Array] [3, 5, 7, 9]  
// [object Array] [2, 5, 8, 11]  
```  
  
 Následující příklad kódu ukazuje použití funkce šipku s blokem příkaz.  
  
```JavaScript  
var fives = new Array();  
  
// Statement block, re-using nums array from previous example.  
// Note: The first argument to the callback function in forEach  
// is the value of the array element (v).  
nums.forEach(v => {  
  if (v % 5 === 0)  
    fives.push(v);  
});  
  
console.log(fives);  
  
// Output:  
// [object Array] [5]  
```  
  
 Na rozdíl od standardní funkce, funkce šipku sdílet stejný lexikální `this` objektu jako okolního kód, který slouží k vyloučení potřeby alternativní řešení, jako `var self = this;`.  
  
 Následující příklad ukazuje, že hodnota `this` objekt v rámci funkce šipku je stejný jako kód okolního (stále odkazuje `bob` proměnné.  
  
```JavaScript  
var bob = {  
  _name: "Bob",  
  _friends: ["Pete", "Joe", "Larry"],  
  printFriends() {  
    this._friends.forEach(f =>  
      console.log(this._name + " knows " + f));  
  }  
}  
  
// Output:  
// Bob knows Pete  
// Bob knows Joe  
// Bob knows Larry  
```  
  
 Funkce šipku také sdílet stejný lexikální `arguments` objektu jako kód okolního (stejně jako `this` objekt).  
  
<a name="Default"></a>   
## <a name="default-parameters"></a>výchozí parametry  
 Výchozí hodnota pro parametr můžete ve funkci přiřazením počáteční hodnotu. Výchozí hodnota může být konstantní hodnotu nebo výraz.  
  
> [!IMPORTANT]
>  Výchozí parametry jsou podporovány pouze v [!INCLUDE[jsv12textExp](../javascript/includes/jsv12textexp-md.md)].  
  
 V následujícím příkladu výchozí hodnota y je 10 a z výchozí hodnota je 20. Funkce použije 10 jako hodnotu y, pokud má volající předá jedinečné hodnoty (nebo není definovaná) jako druhý argument. Funkce bude používat jako hodnotu z 20, pokud volající předá jedinečné hodnoty (nebo není definovaná) jako třetí argument.  
  
```JavaScript  
var val = 20;  
  
function f(x, y=10, z=val) {  
  return x + y + z;  
}  
  
console.log(f(3));  
console.log(f(3, 3));  
console.log(f(3, 3, 3));  
  
// Output:  
// 33  
// 26  
// 9  
```  
  
<a name="Rest"></a>   
## <a name="rest-parameters"></a>Parametry REST  
 REST parametry, operátorem šíření zadané `...`, vám umožní zapnout po sobě jdoucích argumenty ve volání funkce na pole.  
  
 Parametry REST eliminovat potřebu `arguments` objektu. Parametry REST se liší od `arguments` objektu několika způsoby, například:  
  
-   Parametr rest je skutečný pole instance a proto podporuje operace, které lze provést na pole.  
  
-   Parametr rest obsahuje pouze po sobě jdoucích argumenty, které nejsou předaná jako samostatné argumenty (s názvem) (Pokud naopak `arguments` objekt obsahuje všechny argumenty předána do funkce).  
  
> [!IMPORTANT]
>  Parametry REST a šíření operátor jsou podporovány pouze v [!INCLUDE[jsv12text](../javascript/includes/jsv12text-md.md)].  
  
 V následujícím příkladu kódu se "text hello" a true předané hodnoty pole a uložené v parametru y. Parametr rest musí být poslední parametr funkce.  
  
```JavaScript  
function f(x, ...y) {  
  // y is an array.  
  return x * y.length;  
}  
  
console.log(f(3, "hello", true));  
  
// Output:  
// 6  
  
```  
  
 Pro další použití operátoru šíření, najdete v části [šíří operátor](../javascript/reference/spread-operator-decrement-dot-dot-dot-javascript.md).  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace jazyka JavaScript](../javascript/javascript-language-reference.md)