---
title: "Výpočet dat a časů (JavaScript) | Microsoft Docs"
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
helpviewer_keywords:
- date and time arithmetic [JavaScript]
- JavaScript, date and time
- date comparison [JavaScript]
- date and time calculations [JavaScript]
ms.assetid: ea976f78-d934-479b-9056-880390d8bddd
caps.latest.revision: "34"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 18b4ff307c8f2c48a37ed9ca50e7c5f1ff693ece
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="calculating-dates-and-times-javascript"></a>Výpočet dat a časů (JavaScript)
Můžete použít [Date – objekt](../javascript/reference/date-object-javascript.md) k provádění běžných úloh kalendář a hodiny, jako je například porovnání kalendářních dat a výpočet uplynulá doba.  
  
## <a name="setting-a-date-to-the-current-date"></a>Nastavení data na aktuální datum  
 Při vytváření instance [Date – objekt](../javascript/reference/date-object-javascript.md) bez zadání datum, vrátí hodnotu, která představuje aktuální datum a čas, včetně rok, měsíc, den, hodinu, minutu, sekundu a milisekundu. Potom můžete načíst nebo upravit toto datum a čas.  
  
 Následující příklad ukazuje, jak vytvořit instanci datum bez použití žádné parametry a zobrazit ji ve formátu *mm-dd rr*.  
  
```JavaScript  
var dt = new Date();  
  
// Display the month, day, and year. getMonth() returns a 0-based number.  
var month = dt.getMonth()+1;  
var day = dt.getDate();  
var year = dt.getFullYear();  
document.write(month + '-' + day + '-' + year);  
  
// Output: current month, day, year  
```  
  
## <a name="setting-a-specific-date"></a>Nastavení konkrétního data  
 Můžete nastavit konkrétní datum předáním řetězec datum konstruktoru.  
  
```JavaScript  
var dt = new Date('8/24/2009');  
document.write(dt);  
  
// Output: Mon Aug 24 00:00:00 PDT 2009  
  
```  
  
> [!IMPORTANT]
>  Časové pásmo zobrazí v řetězci Datum odpovídá časové pásmo nastavené v místním počítači.  
>   
>  [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]je flexibilní o formátu řetězce, které můžete použít jako parametr. Můžete například zadat "8 – 24-2009", "24 srpen 2009", nebo "24 srpna 2009".  
  
 Můžete také zadat čas. Následující příklad ukazuje jeden ze způsobů zadejte datum a čas ve formátu ISO. "Z" označuje čas UTC.  
  
```JavaScript  
var dt = new Date('2010-06-09T15:20:00Z');  
document.write(dt);  
document.write("<br />");  
document.write(dt.toISOString());  
  
// Output:  
// Wed Jun 09 2010 08:20:00 GMT-0700 (Pacific Daylight Time)  
// 2010-06-09T15:20:00.000Z  
```  
  
 Další informace o formátech datum, jako je například ISO, najdete v části [řetězců data a času](../javascript/date-and-time-strings-javascript.md).  
  
 Následující příklad ukazuje další způsoby, jak určují dobu.  
  
```JavaScript  
var dtA = new Date('8/24/2009 14:52:10');  
  
// The parameters are year, month, day, hours, minutes, seconds.  
var dtB = new Date(2009, 7, 24, 14, 52, 10);  
document.write(dtA);  
document.write("<br/>");  
document.write(dtB);  
  
// Output:  
// Mon Aug 24 14:52:10 PDT 2009  
// Mon Aug 24 14:52:10 PDT 2009  
  
```  
  
## <a name="adding-and-subtracting-days-months-and-years"></a>Přičítání a odečítání dnů, měsíců a roků  
 Můžete použít metody getX a setX `Date` objekt, který chcete nastavit konkrétní data a časy.  
  
 Následující příklad ukazuje, jak můžete nastavit datum předchozí den. Všimněte si, že v případě potřeby měsíci a roce hodnoty jsou také změnit.  
  
```JavaScript  
var myDate = new Date("1/1/1990");  
var dayOfMonth = myDate.getDate();  
myDate.setDate(dayOfMonth - 1);  
  
document.write(myDate);  
  
// Output: Sun Dec 31 00:00:00 PST 1989  
```  
  
 Následující příklad nastaví datum posledního dne v měsíci odečtením den od prvního dne v měsíci Další.  
  
> [!TIP]
>  Měsíce v roce jsou číslo v rozsahu 0 (leden) do 11 (prosinec). Dny v týdnu jsou číslována od 0 (neděle) do 6 (neděle).  
  
```JavaScript  
var myDate = new Date("1/1/1990")  
myDate.setMonth(myDate.getMonth() + 1);  
  
myDate.setDate (myDate.getDate() - 1);  
  
document.write(myDate);  
  
// Output: Wed Jan 31 00:00:00 PST 1990  
  
```  
  
## <a name="working-with-days-of-the-week"></a>Práce s dny v týdnu  
 [Getday – metoda](../javascript/reference/getday-method-date-javascript.md) získá den v týdnu jako číslo v rozsahu od 0 (neděle) a 6 (neděle). (Toto není stejný jako [getDate – metoda](../javascript/reference/getdate-method-date-javascript.md), který získá den v měsíci jako číslo mezi 1 a 31).  
  
 Následující příklad nastaví datum díkůvzdání, který ve Spojených státech je čtvrtý čtvrtek v listopadu. Skript vyhledá listopadu 1 aktuálního roku, potom vyhledá první čtvrtek a potom přidá tři týdny.  
  
```JavaScript  
var myDate = new Date();  
myDate.setHours(0, 0, 0, 0);  
  
myDate.setYear(2013);  
  
// Determine November 1.  
myDate.setDate(1);  
myDate.setMonth(10);  
  
// Find Thursday.  
var thursday = 4;  
while(myDate.getDay() != thursday) {  
    myDate.setDate(myDate.getDate() + 1);  
}  
  
// Add 3 weeks.  
myDate.setDate(myDate.getDate() + 21);  
  
document.write(myDate);  
  
// Output: Thu Nov 28 00:00:00 <time zone> 2013  
  
```  
  
## <a name="calculating-elapsed-time"></a>Výpočet uplynulého času  
 [GetTime – metoda](../javascript/reference/gettime-method-date-javascript.md) vrátí počet milisekund, po které uplynuly od na 1. ledna 1970. Pro žádné datum před tímto datem vrátí záporné číslo.  
  
 Můžete použít [getTime – metoda](../javascript/reference/gettime-method-date-javascript.md) nastavit počáteční a koncový čas pro výpočet uplynulý čas. Slouží pro měření malých jednotek, jako je několik sekund a velké jednotky, jako je například dnů.  
  
 Následující příklad vypočítá uplynulý čas v sekundách. [GetTime – metoda](../javascript/reference/gettime-method-date-javascript.md) získá počet milisekund od nulové data.  
  
```JavaScript  
var startTime = new Date('1/1/1990');  
var startMsec = startTime.getMilliseconds();  
startTime.setTime(5000000);  
var elapsed = (startTime.getTime() - startMsec) / 1000;   
document.write(elapsed);  
  
// Output: 5000  
  
```  
  
 Pro práci s udržitelnější jednotky, lze rozdělit milisekundách poskytované [getTime – metoda](../javascript/reference/gettime-method-date-javascript.md) podle příslušného počtu. Pro instanci Chcete-li počet milisekund na dny, vydělte 86,400,000 (1000 milisekund x 60 sekund x 60 minut x 24 hodin) číslo.  
  
 Následující příklad ukazuje, jak dlouho uplynul od prvního dne zadaný rok. Operace dělení používá k výpočtu uplynulý čas ve dnech, hodiny, minuty a sekundy. Neanalyzuje letní čas.  
  
```JavaScript  
// Set the unit values in milliseconds.  
var msecPerMinute = 1000 * 60;  
var msecPerHour = msecPerMinute * 60;  
var msecPerDay = msecPerHour * 24;  
  
// Set a date and get the milliseconds  
var date = new Date('6/15/1990');  
var dateMsec = date.getTime();  
  
// Set the date to January 1, at midnight, of the specified year.  
date.setMonth(0);  
date.setDate(1);  
date.setHours(0, 0, 0, 0);  
  
// Get the difference in milliseconds.  
var interval = dateMsec - date.getTime();  
  
// Calculate how many days the interval contains. Subtract that  
// many days from the interval to determine the remainder.  
var days = Math.floor(interval / msecPerDay );  
interval = interval - (days * msecPerDay );  
  
// Calculate the hours, minutes, and seconds.  
var hours = Math.floor(interval / msecPerHour );  
interval = interval - (hours * msecPerHour );  
  
var minutes = Math.floor(interval / msecPerMinute );  
interval = interval - (minutes * msecPerMinute );  
  
var seconds = Math.floor(interval / 1000 );  
  
// Display the result.  
document.write(days + " days, " + hours + " hours, " + minutes + " minutes, " + seconds + " seconds.");  
  
//Output: 164 days, 23 hours, 0 minutes, 0 seconds.  
```  
  
### <a name="determining-the-users-age"></a>Stanovení věku uživatele  
 V následujícím příkladu trvá narozeninách uživatele a vypočítá stáří uživatele v let. Odečítá od roku narození z aktuálního roku a potom odečte 1, pokud nedošlo k narozeniny ještě v do aktuálního roku.  
  
```JavaScript  
var birthday = new Date("8/1/1985");  
var today = new Date();  
var years = today.getFullYear() - birthday.getFullYear();  
  
// Reset birthday to the current year.  
birthday.setFullYear(today.getFullYear());  
  
// If the user's birthday has not occurred yet this year, subtract 1.  
if (today < birthday)  
{  
    years--;  
}  
document.write("You are " + years + " years old.");  
  
// Output: You are <number of years> years old.  
  
```  
  
## <a name="comparing-dates"></a>Porovnávání dat  
 Při porovnání kalendářních dat v [!INCLUDE[javascript](../javascript/includes/javascript-md.md)], byste měli mít na paměti, `==` vrátí operátor `true` pouze v případě, že data na obou stranách operátoru odkazovat na stejný objekt. Proto pokud máte dva samostatné `Date` nastavit objekty na stejné datum, `date1 == date2` vrátí `false`. Kromě toho `Date` objekt nastavit s pouze datum a čas není inicializován půlnoci toto datum. Ano, při porovnání jeden `Date` nastavit bez zadanou dobu `Date.now`, například byste měli vědět, první `Date` je nastavenou na půlnoc a `Date.now` není.  
  
 Následující příklad zkontroluje, jestli aktuální datum je stejné, před nebo po zadaném datu. Nastavit aktuální datum v `todayAtMidn`, vytvoří skript `Date` objekt pro aktuální rok, měsíc a den.  
  
```JavaScript  
// Get the current date at midnight.  
var now = new Date();   
var todayAtMidn = new Date(now.getFullYear(), now.getMonth(), now.getDate());  
  
// Set specificDate to a specified date at midnight.  
var specificDate = new Date("9/21/2009");  
  
// Compare the two dates by comparing the millisecond  
// representations.  
if (todayAtMidn.getTime() == specificDate.getTime())  
{  
    document.write("Same");  
}  
else  
{  
    document.write("Different");  
}  
  
//Output: Different  
```  
  
 Změnou v předchozím příkladu jsme můžete zkontrolovat, zda je zadané datum v rámci konkrétní rozsah.  
  
```JavaScript  
// Get the current date at midnight.  
var now = new Date();  
var todayAtMidn = new Date(now.getFullYear(), now.getMonth(), now.getDate());  
  
// Set start/end dates to a specified date (ISO format).  
var startDate = new Date("2009-06-09T15:20:00Z");  
var endDate = new Date("2011-06-09T15:20:00Z");  
  
// Compare the two dates by comparing the millisecond  
// representations.  
if (todayAtMidn.getTime() > startDate.getTime() &&   
    todayAtMidn.getTime() < endDate.getTime()) {  
    document.write("Specified date is within this range.");  
}  
else {  
    document.write("Specified date is not in this range.");  
}  
  
// Output: Specified date is not in this range.  
```  
  
## <a name="see-also"></a>Viz také  
 [Date – objekt](../javascript/reference/date-object-javascript.md)