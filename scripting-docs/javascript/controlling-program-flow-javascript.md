---
title: Řízení toku programu (JavaScript) | Microsoft Docs
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
- Boolean values, program flow
- continue statement
- break statement
- control flow, about control flow
ms.assetid: 4ef58c82-e5d6-4b09-9458-cf0aa3b39bf5
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 20c256d26c6991067d7c25c0c835eda6e5e5aac6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789303"
---
# <a name="controlling-program-flow-javascript"></a>Řízení toku programu (JavaScript)
Za normálních okolností příkazy v [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] jsou skript spustit jeden za druhým, v pořadí, ve kterém jsou zapsány. To se označuje jako sekvenční provádění a je výchozí směr toku programu.  
  
 Alternativu ke spuštění sekvenční přenáší toku programu do jiné části souboru skriptu. To znamená místo provedení další příkaz v pořadí, jiná je spustit příkaz místo.  
  
 Chcete-li skript užitečné, je třeba provést tento přenos řízení logicky. Přenos řízení programu podle rozhodnutí, jejímž výsledkem je prohlášení pravdivosti (vrací logickou hodnotu **true** nebo **false**). Můžete vytvořit výraz, a potom otestovat, zda výsledek je true. Existují dva hlavní typy struktur programu, které dosáhnout.  
  
 První je strukturu výběr. Použijte k určení alternativního kurzy toku programu, vytváření spojení v programu (např. rozvětvení v silniční). Nejsou k dispozici v čtyři výběr struktury [!INCLUDE[javascript](../javascript/includes/javascript-md.md)].  
  
-   Struktura jedním výběrem (**Pokud**),  
  
-   Struktura double výběr (**Pokud nebo jiného**),  
  
-   vložené Ternární operátor`?:`  
  
-   Struktura vícenásobného výběru (`switch`).  
  
 Druhý typ ovládacího prvku struktura programu je struktura opakování. Můžete použít k určení, že akce se opakuje, přičemž zůstane nějaká podmínka true. Při splnění podmínek příkazu ovládací prvek (obvykle po některé konkrétní počet iterací), předá řízení další příkaz nad rámec strukturu opakování. Nejsou k dispozici v čtyři struktury opakování [!INCLUDE[javascript](../javascript/includes/javascript-md.md)].  
  
-   výraz je testován v horní části smyčky (`while`),  
  
-   výraz je testován v dolní části smyčky (**udělat / při**),  
  
-   na každé z vlastností objektu pracovat (**pro/v**).  
  
-   Čítač řídí opakování (**pro**).  
  
 Můžete vytvořit poměrně složité skripty vnoření a skládání výběru a opakování řídicí struktury.  
  
 Zpracování výjimek, které není zahrnuté v tomto dokumentu poskytuje třetí formu toku strukturovaných programu.  
  
## <a name="using-conditional-statements"></a>Podmíněné příkazy  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]podporuje **Pokud** a [if... else](../javascript/reference/if-dot-dot-dot-else-statement-javascript.md) podmíněné příkazy. V **Pokud** příkazy testovanou podmínku a splňuje podmínky testu odpovídajícího [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] je kód spuštěn. V `if...else` je spustit příkaz, jiný kód, pokud se test nezdaří podmínku. Nejjednodušší forma **Pokud** příkaz může být napsán na jeden řádek, ale víceřádkových **Pokud** a `if...else` příkazy jsou mnohem častější.  
  
 Následující příklady ukazují syntaxe můžete používat s **Pokud** a `if...else` příkazy. V prvním příkladu zobrazuje Nejjednodušším typem Boolean testu. Pokud (a pouze v případě) položky v závorkách se vyhodnocuje (nebo může být přiřazena) **true**, příkaz nebo blok příkazů po **Pokud** se spustí.  
  
```JavaScript  
function GetReaction(newShip, color, texture, dayOfWeek)  
{  
   // The test succeeds if the newShip Boolean value is true.  
   if (newShip)  
   {  
      return "Champagne Bottle";  
   }  
  
   // The test succeeds if both conditions are true.  
   if (color == "deep yellow" && texture == "large and small wrinkles")  
   {  
      return "Is it a crenshaw melon?";  
   }  
  
   // The test succeeds if either condition is true.  
   if ((dayOfWeek == "Saturday") || (dayOfWeek == "Sunday"))  
   {  
      return "I'm off to the beach!";  
   }  
   else  
   {  
      return "I'm going to work.";  
   }  
}  
  
var reaction = GetReaction(false, "deep yellow", "smooth", "Sunday");  
document.write(reaction);  
  
// Output: I'm off to the beach!  
```  
  
## <a name="conditional-operator"></a>Podmíněný operátor  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]podporuje také implicitní podmíněného formuláře. Používá otazník po podmínka má být testována (místo slovo **Pokud** před podmínku). Určuje také dva alternativy, jeden, který použije, pokud je splněna podmínka a jeden Pokud není. Dvojtečkou musí jednotlivé alternativy.  
  
```JavaScript  
var AMorPM = (theHour >= 12) ? "PM" : "AM";  
```  
  
 Pokud máte několik podmínek, které má být testována společně a víte, že jeden je pravděpodobnější úspěch nebo selhání než ostatní, můžete použít funkci krátké okruh vyhodnocení urychlit provádění skriptu. Když [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] vyhodnocuje logický výraz, vyhodnocuje jenom tolik dílčí výrazy jako vyžadované k získání výsledku.  
  
 Například, pokud máte například výraz a ((x == 123) & & (y == 6)), [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] nejprve ověří, zda x 123. Pokud není, i když je rovno 6 y nemůže být nastavena hodnota true, celý výraz. Proto se nikdy provádí test pro y, a [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] vrátí hodnotu **false**.  
  
 Podobně pokud jenom jedna z několika podmínek musí být **true** (pomocí &#124; &#124; operátor), testování zastaví také všechny jednu podmínku projde testem. Toto je efektivní, pokud podmínky, které má být testována zahrnují provádění volání funkce nebo další složité výrazy. To na paměti, když napíšete nebo výrazy, umístěte nejpravděpodobněji podmínky **true** první. Když napíšete a výrazy, umístěte nejpravděpodobněji podmínky **false** první.  
  
 Výhodou návrh vašeho skriptu tímto způsobem je, že **runsecond()** nebude spuštěn v následujícím příkladu, pokud **runfirst()** vrátí hodnotu 0.  
  
```JavaScript  
if ((runfirst() == 0) || (runsecond() == 0)) {  
    // some code  
}  
```  
  
## <a name="using-loops"></a>Pomocí smyčky  
 Existuje několik způsobů provést příkaz nebo blok příkazů opakovaně. Obecně platí, se nazývá opakovaných provádění *opakování ve smyčce* nebo *iterace*. Iterace je jednoduše jednoho spuštění smyčku. Je obvykle řízen testem proměnné, kde je hodnota, které se změní pokaždé, když smyčky provést. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]podporuje čtyři typy smyčky: [pro](../javascript/reference/for-statement-javascript.md) smyčky, [for... v](../javascript/reference/for-dot-dot-dot-in-statement-javascript.md) smyčky, [při](../javascript/reference/while-statement-javascript.md) smyčky, [do... while](../javascript/reference/do-dot-dot-dot-while-statement-javascript.md) smyčky.  
  
## <a name="using-for-loops"></a>Pomocí smyčky for  
 **Pro** příkaz určuje čítač proměnné, podmínky testu a akce, která aktualizuje čítač. Před každou iteraci smyčky testovanou podmínku. Je-li test úspěšný, se spustí kód uvnitř smyčky. Pokud test neproběhne úspěšně, není proveden kód uvnitř smyčky a program bude pokračovat na první řádek kódu hned za smyčky. Po provedení smyčky proměnnou čítač se aktualizuje před zahájením další iterace.  
  
 Pokud nikdy je splněna podmínka pro opakování ve smyčce, se nikdy spustí smyčky. Pokud je vždy splněna podmínka test, výsledky nekonečné smyčce. Při první může být žádoucí v některých případech, zřídka je, tak buďte opatrní při zápisu vaší podmínkách smyčky.  
  
```JavaScript  
// The update expression ("icount++" in the following examples)  
// is executed at the end of the loop, after the block of  
// statements that forms the body of the loop is executed, and  
// before the condition is tested.  
  
// Set a limit of 10 on the loop.  
var howFar = 10;  
  
// Create an array called sum with 10 members, 0 through 9.  
var sum = new Array(howFar);  
sum[0] = 0;  
  
// Iterate from 0 through 9.  
var theSum = 0;  
for(var icount = 0; icount < howFar; icount++)  
{  
   theSum += icount;  
   sum[icount] = theSum;  
}  
  
// This code is not executed at all, because icount is not greater than howFar.  
var newSum = 0;  
for(var icount = 0; icount > howFar; icount++)  
{  
   newSum += icount;  
}  
  
// This is an infinite loop.  
var sum = 0;  
for(var icount = 0; icount >= 0; icount++)  
{  
   sum += icount;  
}  
```  
  
## <a name="using-forin-loops"></a>Pomocí for... v smyčky  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]poskytuje zvláštní druh smyčky pro procházení všechny uživatelem definované vlastnosti [objekt](../javascript/objects-and-arrays-javascript.md), nebo všechny elementy pole. Čítač smyčky v `for...in` smyčka je řetězec, není číslo. Obsahuje název aktuální vlastnosti nebo index pole aktuálního elementu.  
  
```JavaScript  
// Create an object with some properties  
var myObject = new Object();  
myObject.name = "James";  
myObject.age = "22";  
myObject.phone = "555 1234";  
  
// Enumerate (loop through)_all the properties in the object  
for (var prop in myObject)  
{  
    // This displays "The property 'name' is James", etc.  
    document.write("The property '" + prop + "' is " + myObject[prop]);  
    // New line.  
    document.write("<br />");    
}  
```  
  
 I když `for...in` smyčky vypadat podobně jako na VBScript `For Each...Next` smyčky, nepracují stejným způsobem. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] **For... ve smyčce** iteruje nad vlastnosti [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] objekty. Jazyce VBScript **pro každou... Další** smyčky iteruje nad položky v kolekci. K smyčku kolekcí v [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], budete muset použít [objekt Enumerator](../javascript/reference/enumerator-object-javascript.md) objekt nebo, pokud existuje, `forEach` metoda objektu kolekce. I když některé objekty, například v Internet Exploreru podporovat jazyce VBScript **For Each... Další** smyčky a [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] **for... v** smyčky, většinu objektů nepodporují.  
  
## <a name="using-while-loops"></a>Použití při smyčky  
 A `while` smyčka je podobná **pro** smyčky. Rozdíl je, `while` smyčky nemá čítač předdefinované proměnné nebo aktualizace výraz. Pokud chcete řídit opakovaných spuštění příkazu nebo bloku příkazy, ale potřebovat složitější pravidla než jednoduše "spustit n časy tento kód", použití `while` smyčky. Následující příklad používá objektový model aplikace Internet Explorer a `while` opakování ve smyčce bude požádat uživatele jednoduchý dotaz.  
  
```JavaScript  
var x = 0;  
while ((x != 5) && (x != null))  
{  
    x = window.prompt("What is my favorite number?", x);  
}  
  
if (x == null)  
    window.alert("You gave up!");  
else  
    window.alert("Correct answer!");  
```  
  
> [!NOTE]
>  Protože `while` smyčky nemají explicitní čítač předdefinované proměnné, jsou zranitelnější vůči nekonečné opakování ve smyčce než jiné typy smyčky. Navíc vzhledem k tomu, že to není nezbytně snadno zjistit, kde a kdy je aktualizovaná vzniku smyčky, je snadné pro zápis `while` smyčky v kterém podmínka nikdy získá aktualizovat. Z tohoto důvodu byste měli být opatrní při návrhu `while` smyčky.  
  
 Jak jsme uvedli výše, k dispozici je také **do... while** smyčky v [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] který je podobný chvíli cykly, s tím rozdílem, že je zaručeno provést vždy alespoň jednou, protože podmínka je testován na konci smyčky, nikoli na začátku . Například může být výše smyčky znovu napsané jako:  
  
```JavaScript  
var x = 0;  
do  
{  
    x = window.prompt("What is my favorite number?", x);  
} while ((x != 5) && (x != null));  
  
if (x == null)  
    window.alert("You gave up!");  
else  
    window.alert("Correct answer!");  
```  
  
## <a name="using-break-and-continue-statements"></a>Pomocí přerušení a pokračovat – příkazy  
 V [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], [zalomení](../javascript/reference/break-statement-javascript.md) se použije příkaz Zastavit provádění smyčku, pokud se nesplní nějaká podmínka. (Všimněte si, že **zalomení** slouží také k ukončení `switch` bloku). [Pokračovat](../javascript/reference/continue-statement-javascript.md) příkaz lze použít okamžitě přejít do další iterace, přeskočení zbytek blok kódu při aktualizaci proměnnou čítače, pokud je smyčky **pro** nebo `for...in` smyčky.  
  
 V následujícím příkladu je založený na předchozí příklad použití **zalomení** a **pokračovat** příkazy k řízení smyčky.  
  
```JavaScript  
var x = 0;  
do  
{  
    x = window.prompt("What is my favorite number?", x);  
  
    // Did the user cancel? If so, break out of the loop  
    if (x == null)  
        break;  
  
    // Did they enter a number?  
    // If so, no need to ask them to enter a number.  
    if (Number(x) == x)  
        continue;  
  
    // Ask user to only enter in numbers  
    window.alert("Please only enter in numbers!");  
  
} while (x != 5)  
  
if (x != 5)  
    window.alert("You gave up!");  
else  
    window.alert("Correct answer!");  
```