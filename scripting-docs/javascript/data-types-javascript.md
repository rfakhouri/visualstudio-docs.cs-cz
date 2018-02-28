---
title: "Datové typy (JavaScript) | Microsoft Docs"
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
- Boolean data type, supported data types
ms.assetid: c7a6bd3a-4b1c-4dbe-8505-106dbf483b41
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aa3a0e4cdbb25019758f89958afdf06c11f01a34
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="data-types-javascript"></a>Datové typy (JavaScript)
V [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], existují dva speciální datové typy, dva složené datové typy a tři primární datové typy.  
  
## <a name="primary-data-types"></a>Primární datové typy  
 Primární (primitivní) datové typy jsou:  
  
-   String  
  
-   Číslo  
  
-   Boolean  
  
## <a name="composite-data-types"></a>Složené datové typy  
 Typy dat složené (referenční dokumentace):  
  
-   Objekt  
  
-   Pole  
  
## <a name="special-data-types"></a>Speciální typy dat  
 Speciální datové typy jsou:  
  
-   Null  
  
-   Nedefinovaná  
  
## <a name="string-data-type"></a>Datový typ String  
 Řetězcová hodnota je řetězec nula nebo více znaků Unicode (písmen, číslic a interpunkčních znamének). Použít datový typ řetězec představuje text v [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]. Textové literály můžete zahrnout skripty uzavřené v jednoduchých nebo dvojitých uvozovek. Dvojité uvozovky, může být obsažený v řetězcích v jednoduchých uvozovkách a apostrofech, mohou být obsaženy v řetězce v uvozovkách. Příkladem řetězce jsou následující:  
  
```JavaScript  
"Happy am I; from care I'm free!"  
'"Avast, ye lubbers!" roared the technician.'   
"45"  
'c'  
```  
  
 Všimněte si, že [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] nemá typ k zastupování jednoho znaku. K zastupování jednoho znaku v [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], můžete vytvořit řetězec, který se skládá z jenom jeden znak. Řetězec, který obsahuje nulové znaky ("") je prázdný řetězec (nulové délky).  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]poskytuje řídicí sekvence, které lze zahrnout v řetězcích vytvořit znaky, které nelze zadat přímo. Například `\t` určuje znaku tabulátoru. Další informace najdete v tématu [speciální znaky](../javascript/advanced/special-characters-javascript.md).  
  
## <a name="number-data-type"></a>Datový typ Number  
 V [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], není žádný rozdíl mezi celé číslo a hodnoty s plovoucí desetinnou čárkou, [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] číslo může být buď (interně [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] reprezentuje všechna čísla jako hodnoty s plovoucí desetinnou čárkou).  
  
### <a name="integer-values"></a>Celočíselné hodnoty  
 Celé číslo hodnoty mohou být kladná celá čísla, záporná celá čísla a 0. Se může být reprezentován v základní 10 (decimální), základní 16 (hexadecimální) a základní 8 (osmičková). Většina čísel ve [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] jsou zapsány v desítkové soustavě.  
  
 Označují hexadecimální celých čísel ("šestnáctkových") podle prefixu je znaky "0 x" (nula a x &#124; X). Číslice 0 až 9 a písmena A až F (velká nebo malá písmena) mohou obsahovat pouze. Písmena A až F se používají k vyjádření, jako jednoho číslic, 10 až 15 v základní 10. To znamená, je ekvivalentní 15, 0xF a 0x10 je ekvivalentní na 16.  
  
 Můžete pomocí prefixu je s "0" (nula) označují osmičková celých čísel. Mohou obsahovat číslice 0 až 7 jenom. Číslo, které má počáteční "0" a obsahuje číslice "8" nebo "9" je interpretován jako s desetinným číslem.  
  
 Hexadecimální i osmičková číslice může být záporná, ale nemohou mít decimal část a nemůže být napsané v matematickém (exponenciálním) zápisu.  
  
> [!NOTE]
>  Počínaje [!INCLUDE[jsv9text](../javascript/includes/jsv9text-md.md)], [funkce parseInt](../javascript/reference/parseint-function-javascript.md) nebude pracovat s řetězec, který má předponu "0" jako osmičková. Pokud nepoužíváte `parseInt` fungovat, ale řetězce s předponou 0, interpretaci jako osmičková.  
  
### <a name="floating-point-values"></a>Hodnoty s plovoucí desetinnou čárkou  
 Hodnoty s plovoucí desetinnou čárkou mohou být celá čísla, s desetinnou část. Kromě toho mohou být vyjádřeny v exponenciální notace. To znamená s velká nebo malá "e" se používá k reprezentování "deset exponentem". [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]představuje přes standardní s plovoucí desetinnou čárkou osm bajtů IEEE 754 pro číselné vyjádření čísla. To znamená, že napíšete čísla tak velké, jaká 1.79769x10<sup>308</sup>a co 5 × 10<sup>-324</sup>. Počet, který obsahuje desetinné čárky a který má jeden "0" od desetinné čárky interpretována jako desítkové číslo s plovoucí desetinnou čárkou.  
  
 Všimněte si, že číslo, které začíná "0 x" nebo "00" a obsahuje desetinné čárky dojde k chybě. Tady jsou některé příklady [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] čísla.  
  
|Číslo|Popis|Decimal ekvivalent|  
|------------|-----------------|------------------------|  
|.0001, 0,0001 1e-4, 1.0e-4|Čtyři ekvivalentní čísla s plovoucí desetinnou čárkou.|0.0001|  
|3.45e2|Číslo s plovoucí desetinnou čárkou.|345|  
|45|Celé číslo.|45|  
|0378|Celé číslo. I když toto vypadá jako osmičkové číslo (začíná nule), 8 není platný osmičková číslice, takže číslo je považován za datový typ decimal.|378|  
|0377|Osmičkové celé číslo. Všimněte si, že i když se zobrazí pouze jako jeden menší než číslo výše, jeho skutečná hodnota je výrazně lišit.|255|  
|0.0001|Číslo s plovoucí desetinnou čárkou. I když to začíná nulu, není osmičkové protože má desetinné čárky.|0.0001|  
|00.0001|Jedná se o chybu. Dva úvodní nuly označit jako osmičkové číslo, ale octals nejsou povoleny komponentu decimal.|Není k dispozici (Chyba kompilátoru)|  
|0Xff|Hexadecimální celé číslo.|255|  
|0x37CF|Hexadecimální celé číslo.|14287|  
|0x3E7|Hexadecimální celé číslo. Všimněte si, že "e" nepovažuje se za exponenciální zápis.|999|  
|0x3.45e2|Jedná se o chybu. Hexadecimální číslice nemůže mít desetinné části.|Není k dispozici (Chyba kompilátoru)|  
  
 Kromě toho [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] obsahuje čísel speciální hodnotami. Jsou to:  
  
-   NaN (není číslo). To se používá při provádění matematické operace je v nevhodném data, jako třeba řetězce nebo nedefinovanou hodnotu  
  
-   Kladné nekonečno. To se používá při příliš velký, aby reprezentoval v kladné číslo.[!INCLUDE[javascript](../javascript/includes/javascript-md.md)]  
  
-   Záporné nekonečno. Používá se při záporné číslo je příliš velký představují v[!INCLUDE[javascript](../javascript/includes/javascript-md.md)]  
  
-   Kladné a záporné 0. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]rozlišuje kladné a záporné nuly.  
  
## <a name="boolean-data-type"></a>Datový typ Boolean  
 Zatímco číselné datové typy a řetězci může mít prakticky neomezený počet různé hodnoty, Boolean – datový typ může mít pouze dva. Jsou literály `true` a `false`. Logická hodnota je truth-value: Určuje, zda je podmínka pravdivá, nebo ne.  
  
 Porovnání, které provedete ve skriptech, vždy mít logický výsledek. Vezměte v úvahu následující řádek [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] kódu.  
  
```JavaScript  
y = (x == 2000);  
```  
  
 Tady, hodnota proměnné `x` se porovnává se číslo 2000. Pokud se jedná, výsledkem porovnání je logická hodnota **true**, který je přiřazen k proměnné `y`. Pokud `x` není roven 2000, pak je výsledkem porovnání je logická hodnota `false`.  
  
 Logické hodnoty jsou obzvláště užitečná v řídicí struktury. Následující kód kombinuje porovnání, které vytvoří logickou hodnotu přímo pomocí příkazu, který se používá. Vezměte v úvahu následující [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] ukázka kódu.  
  
```JavaScript  
if (x == 2000) {  
    z = z + 1;  
}  
else {  
    x = x + 1;  
}  
```  
  
 `if/else` Příkaz v [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] provádí jednu akci, pokud je logická hodnota `true` (`z = z + 1`) a pokud je logická hodnota alternativní akci `false` (`x = x + 1`).  
  
 Můžete použít libovolný výraz jako srovnávací výraz. Libovolný výraz, který se vyhodnotí na hodnotu 0, null, nedefinované nebo na prázdný řetězec je interpretován jako `false`. Výraz, který se vyhodnotí jako jakákoli jiná hodnota interpretována jako `true`. Například můžete použít výraz například:  
  
```JavaScript  
// This may not do what you expect. See below!  
if (x = y + z)   
```  
  
 Všimněte si, že výše řádku nekontroluje, jestli `x` rovná `y + z`, protože se používá jen jeden symbol rovná se (operátor přiřazení). Místo toho výše uvedený kód přiřadí hodnota `y + z` proměnnou `x`a poté ověří, zda výsledek celý výraz (hodnota `x`) je nulová. Chcete-li zkontrolovat zda `x` rovná `y + z`, budete muset použít následující kód.  
  
```JavaScript  
// This is different from the code above!  
if (x == y + z)   
```  
  
 Další informace o porovnání najdete v tématu [řízení toku programu](../javascript/controlling-program-flow-javascript.md).  
  
## <a name="the-null-data-type"></a>Datový typ null  
 `null` Datový typ má pouze jednu hodnotu v [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]: hodnotu null. `null` – Klíčové slovo nelze použít jako název funkce nebo proměnná.  
  
 Proměnné, která obsahuje `null` obsahuje žádné platné číslo, řetězec, logická hodnota, pole nebo objekt. Můžete vymazat obsah proměnné (bez odstraňování proměnné) podle jeho přiřazení `null` hodnotu.  
  
 Všimněte si, že v [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], `null` není stejný jako 0 (jako je C a C++). Všimněte si také, že `typeof` operátor v [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] sestavy `null` hodnoty jako typu `Object`, není typu `null`. Toto chování potenciálně matoucí slouží potřebám zpětné kompatibility.  
  
## <a name="the-undefined-data-type"></a>Datový typ undefined  
 `undefined` Hodnota je vrácena, pokud používáte vlastnost objektu, který ještě neexistuje, nebo hodnota přiřazená k němu měl proměnné, která byla deklarována, ale má nikdy.  
  
 můžete zkontrolovat, jestli existuje proměnné tak, že porovnáte jej do `undefined`, i když můžete zkontrolovat, jestli je její typ `undefined` tak, že porovnáte typ proměnné řetězec "undefined". Následující příklad ukazuje, jak zjistit proměnnou `x` bylo deklarováno:  
  
```JavaScript  
  
var x;  
  
// This method works.  
if (x == undefined) {  
    document.write("comparing x to undefined <br/>");  
}  
.  
// This method doesn't work - you must check for the string "undefined".  
if (typeof(x) == undefined) {  
    document.write("comparing the type of x to undefined <br/>");  
}  
// This method does work.   
if (typeof(x) == "undefined") {  
    document.write("comparing the type of x to the string 'undefined'");  
}  
  
// Output:   
// comparing x to undefined   
// comparing the type of x to the string 'undefined'  
  
```  
  
 Také můžete porovnat nedefinované hodnotu `null`. Toto porovnání se `true` Pokud vlastnost `someObject.prop` je `null` nebo, pokud vlastnost `someObject.prop` neexistuje.  
  
```JavaScript  
someObject.prop == null;  
```  
  
 Chcete-li zjistit, jestli existuje vlastnost objektu, můžete použít **v** operátor:  
  
```JavaScript  
if ("prop" in someObject)  
    // someObject has the property 'prop'  
```  
  
## <a name="see-also"></a>Viz také  
 [Objekty a pole](../javascript/objects-and-arrays-javascript.md)   
 [typeof – operátor](../javascript/reference/typeof-operator-decrementjavascript.md)