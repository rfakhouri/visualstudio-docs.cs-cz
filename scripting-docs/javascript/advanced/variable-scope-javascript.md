---
title: Obor proměnné (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- scope, JavaScript
- variable scope [JavaScript]
- variables, scope [JavaScript]
ms.assetid: a811a9a6-856f-46e9-8be3-f2d22a0c245f
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5afc99bf3d1006b68e1d6c4c8d5bbcfc90eb776f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789114"
---
# <a name="variable-scope-javascript"></a>Obor proměnné (JavaScript)
[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]má dva obory: globální a místní. Proměnné, která je deklarovaná mimo definici funkce je globální proměnné a jeho hodnota může být přístupné a změn v rámci vašeho programu. Je místní proměnné, která je deklarován v definici funkce. Je vytvořen a zničen pokaždé, když funkce je spuštěna, a není přístupný pomocí kód vně funkce. Jazyk JavaScript nepodporuje oborem bloku (ve kterém složené závorky `{. . .}` definuje nového oboru), s výjimkou ve speciálním případě proměnných s rozsahem bloku.  
  
## <a name="scope-in-javascript"></a>Rozsah v jazyce JavaScript  
 Místní proměnná může mít stejný název jako globální proměnné, ale je zcela samostatné; Změna hodnoty jednu proměnnou nemá žádný vliv na straně druhé. Pouze místní verze má význam uvnitř funkce, ve kterém je deklarovaná.  
  
```JavaScript  
// Global definition of aCentaur.  
var aCentaur = "a horse with rider,";  
  
// A local aCentaur variable is declared in this function.  
function antiquities(){  
  
   var aCentaur = "A centaur is probably a mounted Scythian warrior";  
}  
  
antiquities();  
aCentaur += " as seen from a distance by a naive innocent.";  
  
document.write(aCentaur);  
  
// Output: "a horse with rider, as seen from a distance by a naive innocent."  
```  
  
 V jazyce JavaScript proměnné se vyhodnocují jako kdyby bylo deklarováno na začátku, které existují v oboru. V některých případech to vede k neočekávanému chování, jak je vidět tady.  
  
```JavaScript  
var aNumber = 100;  
tweak();  
  
function tweak(){  
  
    // This prints "undefined", because aNumber is also defined locally below.  
    document.write(aNumber);  
  
    if (false)  
    {  
        var aNumber = 123;    
    }  
}  
```  
  
 Když [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] provádí funkce, je nejprve hledá všechny deklarace proměnných, například `var someVariable;`. Vytvoří proměnné s počáteční hodnotou `undefined`. Pokud je proměnná deklarována s hodnotou, například `var someVariable = "something";`, pak stále původně má hodnotu `undefined` a trvá na základě deklarované hodnoty pouze v případě, že je spouštěn řádek, který obsahuje deklaraci.  
  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]zpracuje všechny deklarace proměnných před provedením žádný kód, zda je deklaraci uvnitř blok podmíněný nebo jiné konstrukce. Jednou [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] má najde všechny proměnné, spustí kód ve funkci. Pokud je proměnná implicitně deklarována uvnitř funkce – to znamená, pokud se zobrazí na levé straně výrazu přiřazení, ale nebyla deklarována s `var` -je vytvořen jako globální proměnné.  
  
 V jazyce JavaScript ukládá vnitřní (vnořená) funkce odkazy na lokální proměnné, které se nacházejí ve stejném oboru jako funkce samostatně, i když funkce vrátí hodnotu. Tato sada odkazů se nazývá uzavření. V následujícím příkladu, druhé volání vnitřní funkce výstupy stejnou zprávu ("Hello faktury") jako první volání, protože vstupní parametr pro funkci vnější `name`, je místní proměnné, která je uložená v uzavření pro vnitřní funkce.  
  
```JavaScript  
function send(name) {  
    // Local variable 'name' is stored in the closure  
    // for the inner function.  
    return function () {  
        sendHi(name);  
    }  
}  
  
function sendHi(msg) {  
    console.log('Hello ' + msg);  
}  
  
var func = send('Bill');  
func();  
// Output:  
// Hello Bill  
sendHi('Pete');  
// Output:  
// Hello Pete  
func();  
// Output:  
// Hello Bill  
```  
  
## <a name="block-scoped-variables"></a>Proměnné s rozsahem bloku  
 Představuje podporu pro aplikace Internet Explorer 11 [umožní](../../javascript/reference/let-statement-javascript.md) a [const](../../javascript/reference/const-statement-javascript.md), které jsou proměnné s rozsahem bloku. Pro tyto proměnné, složené závorky `{. . .}` definovat nového oboru. Když nastavíte jeden z těchto proměnných na určitou hodnotu, hodnotu platí pouze pro obor, ve kterém je nastavena.  
  
 Následující příklad ukazuje použití `let` a obor bloku.  
  
> [!NOTE]
>  Následující kód je podporována v režimu standardů aplikace Internet Explorer 11 a novější.  
  
```JavaScript  
let x = 10;  
var y = 10;  
{  
    let x = 5;  
    var y = 5;  
    {  
        let x = 2;  
        var y = 2;  
        document.write("x: " + x + "<br/>");  
        document.write("y: " + y + "<br/>");  
        // Output:  
        // x: 2  
        // y: 2  
    }  
    document.write("x: " + x + "<br/>");  
    document.write("y: " + y + "<br/>");  
    // Output:  
    // x: 5  
    // y: 2  
}  
  
document.write("x: " + x + "<br/>");  
document.write("y: " + y + "<br/>");  
// Output:  
// x: 10  
// y: 2  
```