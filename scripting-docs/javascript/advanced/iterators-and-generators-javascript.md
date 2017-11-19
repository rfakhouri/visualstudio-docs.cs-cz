---
title: "Iterátory a generátory (JavaScript) | Microsoft Docs"
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
ms.assetid: 68ef5b2f-0349-492b-b557-73ff2a2f90cf
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 85c27969609a38b87b15c727e9c8aef89ee77032
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="iterators-and-generators-javascript"></a>Iterátory a generátory (JavaScript)
Iterátor je objekt, který se používá k procházení objektu kontejneru jako seznam. V jazyce JavaScript, není objekt jedinečné integrované iterator objekt, ale je objekt, který implementuje `next` metody přístup na další položku v objektu kontejneru.  
  
 V [!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)], můžete vytvořit vlastní vlastní iterátory. Je však obvykle jednodušší použít generátory, které výrazně zjednodušit vytváření iterátory. Generátory jsou typ funkce, která je objekt factory pro iterátory. Pokud chcete vytvořit vlastní iterator pomocí generátoru funkce, najdete v části [generátory](#Generators).  
  
> [!CAUTION]
>  Generátory jsou podporovány v [!INCLUDE[jsv12textExp](../../javascript/includes/jsv12textexp-md.md)].  
  
## <a name="iterators"></a>Iterátory  
 Implementace JavaScript iterator zahrnuje dvě nebo tři objekty, které odpovídají konkrétním rozhraním:  
  
-   Iterable rozhraní  
  
-   Iterator rozhraní  
  
-   IteratorResult rozhraní  
  
 Pomocí těchto rozhraní, můžete vytvořit vlastní iterátory. To vám umožňuje procházet iterable objekt pomocí `for…of` příkaz.  
  
### <a name="iterable-interface"></a>Iterable rozhraní  
 Iterable se vyžaduje rozhraní pro objekt iterable (objekt, u kterého lze získat iterovat). Například `C` v `for (let e of C)` musí implementovat rozhraní Iterable.  
  
 Objekt iterable musíte zadat metodu Symbol.iterator, která vrátí hodnotu iterace.  
  
```JavaScript  
obj[Symbol.iterator] = function() { return iterObj; }  
```  
  
 Tato vlastnost musí být funkce, která přijímá bez argumentů a vrátí objekt (`iterObject`) uložená `Iterator` rozhraní.  
  
 Mnoho předdefinovaných typů, včetně polí, jsou nyní iterable. `for…of` Smyčky využívá iterable objekt. (Ale ne všechny předdefinované iterables jsou iterátory. For example, není objekt Array iterovat sám sebe, ale je iterable, zatímco ArrayIterator je také iterable.)  
  
### <a name="iterator-interface"></a>Iterator rozhraní  
 Musí implementovat objekt vrácený metodou Symbol.iterator `next` metoda. `next` Metoda má následující syntaxi.  
  
```JavaScript  
iterObj.next() = function() { return iterResultObj; };  
```  
  
 `next` Metoda je funkce, která vrátí hodnotu. Funkce vrátí objekt (`iterResultObj`) uložená `IteratorResult` rozhraní. Pokud předchozí volání `next` metoda iterovat vrátila `IteratorResult` objekt, jehož `done` vlastnost na hodnotu true, pak je ukončen iterace a `next` metoda není volán znovu.  
  
 Iterátory může také zahrnovat `return` metoda zajistit iteraci je po dokončení skriptu s ním zlikvidován správně.  
  
### <a name="iteratorresult-interface"></a>IteratorResult rozhraní  
 IteratorResult se vyžaduje rozhraní pro výsledek `next` metodu iterace. Objekt vrácený `next` musíte zadat `done` a `value` vlastnost.  
  
```JavaScript  
var iterResultObj = { done: true|false, value: value }  
```  
  
 `done` Vlastnost vrátí stav iterator `next` volání metody, true nebo false. Pokud byl dosažen konec iteraci, `done` vrací hodnotu true. Pokud nebyl dosažen `done` vrátí hodnotu false a hodnota je k dispozici. Pokud `done` vlastnost (buď jeho vlastní nebo zděděnou vlastnost) neexistuje, výsledek `done` je považován za hodnotu false.  
  
 Pokud `done` je nastavena hodnota false, `value` vlastnost vrací aktuální hodnotu prvku iterací. Pokud `done` má hodnotu true, toto je vrácenou hodnotu iterator, pokud je zadaná návratovou hodnotu. Pokud iterator nemá návratovou hodnotu `value` není definován. V takovém případě `value` vlastnost nemusí být k dispozici z vyhovující objektu Pokud nedědí ve explicitní hodnotu vlastnosti.  
  
<a name="Generators"></a>   
## <a name="generators"></a>Generátory  
 Snadno vytvořit a použít vlastní iterátory, vytvořit funkci generátor pomocí syntaxe funkce * společně s jedním nebo více `yield` výrazy. Vrátí generátor iterator (to znamená, generátor), která umožňuje tělo funkce generátor provést. Funkce provede na další `yield` nebo `return` příkaz.  
  
 Volání `next` metoda iterator vrátit hodnotu dalšího z generátor funkce.  
  
 Následující příklad ukazuje, generátor, který vrátí iterace pro objekt řetězce.  
  
```JavaScript  
function* stringIter() {  
    var str = "bobsyouruncle";  
    var idx = 0;  
    while(idx < str.length)  
        yield str[idx++];  
}  
  
var si = stringIter();  
  
console.log(si.next().value);  
console.log(si.next().value);  
console.log(si.next().value);  
  
// Output:  
// b  
// o  
// b  
  
```  
  
 V generátoru, operand výrazu yield ukončí volání `next` a vrátí `IteratorResult` objekt s dvě vlastnosti `done` (`done=false`) a `value` (`value=operand`). `operand`je volitelný a pokud je ponecháno chybějící potom její hodnota není definován.  
  
 V generátoru `return` příkaz ukončí generátor vrácením `IteratorResult` s `done=true` společně s výsledek volitelné operand pro vlastnost value.  
  
 Můžete použít také `yield*` výraz místě `yield` delegovat na jiné generátor nebo na jinou iterable objektu, například pole nebo řetězec.  
  
 Pokud přidáte následující kód v předcházejícím příkladu `yield*` deleguje `stringIter` generátor.  
  
```JavaScript  
function* strIter() {  
    yield "jo";  
    yield* stringIter();  
}  
  
var si2 = strIter();  
  
console.log(si2.next().value);  
console.log(si2.next().value);  
console.log(si2.next().value);  
console.log(si2.next().value);  
  
// Output:  
// jo  
// b  
// o  
// b  
```  
  
 Můžete také vytvořit pokročilejší generátory předáním argumentu `next` a používá k úpravě stavu generátoru argument. `next`změní hodnotu výsledek dříve spuštění `yield` výraz. V následujícím příkladu, při předání hodnoty od 100 do `next` metody resetujete hodnotu Použití generátoru interní indexu.  
  
```  
function* strIter() {  
    var str = "jobob";  
    var idx = 0;  
    while(idx , str.length) {  
        var modify = yield str[idx++];  
        if(modify == 100) {  
            idx = 0;  
        }  
    }
}
  
var si3 = strIter();  
  
console.log(si3.next().value);  
console.log(si3.next().value);  
console.log(si3.next().value);  
console.log(si3.next(100).value);  
  
// Output:  
// j  
// o  
// b  
// j  
  
```  
  
 Další pokročilé generátory může volat použití generátoru `throw` metoda. Dochází k chybě výjimce dojde k získání vyvolána v okamžiku, kdy byla pozastavena, generátor (před dalším `yield` příkaz).
