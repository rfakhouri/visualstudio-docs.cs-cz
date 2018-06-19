---
title: Řetězce data a času (JavaScript) | Microsoft Docs
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
ms.assetid: ba0798c5-3574-4434-89f4-3d90be276001
caps.latest.revision: 47
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6218ba273b26243382d1e825b6da961d604917ab
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789282"
---
# <a name="date-and-time-strings-javascript"></a>Řetězce s hodnotami data a času (JavaScript)
Můžete použít několik technik a zadejte formátování řetězce data a času JavaScript.  
  
## <a name="formatting-dates-using-intldatetimeformat"></a>Formátování kalendářních dat pomocí Intl.DateTimeFormat  
 Představuje podporu pro aplikace Internet Explorer 11 [intl.DateTimeFormat – objekt](../javascript/reference/intl-datetimeformat-object-javascript.md), který je součástí [specifikace rozhraní API internacionalizace ECMAScript](http://www.ecma-international.org/ecma-402/1.0/). K formátování kalendářních dat, tento objekt můžete použít přímo nebo použijete aktualizované implementace [toLocaleDateString – metoda (Date)](../javascript/reference/tolocaledatestring-method-date-javascript.md) a [toLocaleTimeString – metoda (Date)](../javascript/reference/tolocaletimestring-method-date-javascript.md). Tyto metody [Date – objekt](../javascript/reference/date-object-javascript.md) použít `Intl.DateTimeFormat` interně k podpoře nové volitelné parametry pro národní prostředí a další možnosti formátování.  
  
 Následující příklad ukazuje, jak používat `toLocaleDateString` a `toLocaleTimeString` do formátu data a časy. První parametr předaný tyto metody, jako je hodnota národního prostředí "en-us". Druhý parametr, kde existuje, určuje možnosti formátování, jako je například dlouhých úseků pro den týdne.  
  
```JavaScript  
var date = new Date(Date.UTC(2013, 1, 1, 14, 0, 0));  
var options = {  
    weekday: "long", year: "numeric", month: "short",  
    day: "numeric", hour: "2-digit", minute: "2-digit"  
};  
  
document.write(date.toLocaleDateString("en-US"));  
document.write(date.toLocaleTimeString("en-us", options));  
document.write(date.toLocaleDateString("ja-JP"));  
document.write(date.toLocaleTimeString("ja-JP", options));  
  
// Output:  
// ‎2‎/‎1‎/‎2013  
// ‎Friday‎, ‎Feb‎ ‎1‎, ‎2013‎ ‎06‎:‎00‎ ‎AM  
// ‎2013‎年‎2‎月‎1‎日‎  
// ‎2013‎年‎2‎月‎1‎日 ‎金曜日‎ ‎06‎:‎00  
```  
  
 Úplný seznam možnosti formátování, najdete v části [intl.DateTimeFormat – objekt](../javascript/reference/intl-datetimeformat-object-javascript.md).  
  
## <a name="formatting-dates"></a>Formátování kalendářních dat  
 Před Internet Explorer 11 JavaScript neměl konkrétních metod k formátování data a časy. Pokud chcete zadat vlastní datum formátování pro předchozí verze prohlížeče, použijte [getDay – metoda (Date)](../javascript/reference/getday-method-date-javascript.md), [getDate – metoda (Date)](../javascript/reference/getdate-method-date-javascript.md), [getMonth – metoda (Date)](../javascript/reference/getmonth-method-date-javascript.md)a [getFullYear – metoda (Date)](../javascript/reference/getfullyear-method-date-javascript.md) metody. ( [GetYear – metoda (Date)](../javascript/reference/getyear-method-date-javascript.md) je zastaralá a by se neměla používat.)  
  
```JavaScript  
var myDate = new Date("February 3, 2001");  
var myDate = new Date("February 3 2001");  
document.write((myDate.getMonth() + 1) + "-" + myDate.getDate() + "-" + myDate.getFullYear());  
document.write("<br/>");  
document.write((myDate.getMonth() + 1) + "/" + myDate.getDate() + "/" + myDate.getFullYear());  
  
//Output:  
// 2-3-2001  
// 2/3/2001  
```  
  
 Můžete zadat vlastní čas – formátování s použitím [getHours – metoda (Date)](../javascript/reference/gethours-method-date-javascript.md), [getMinutes – metoda (Date)](../javascript/reference/getminutes-method-date-javascript.md), [getSeconds – metoda (Date)](../javascript/reference/getseconds-method-date-javascript.md), a [ getMilliseconds – metoda (Date)](../javascript/reference/getmilliseconds-method-date-javascript.md) metody.  
  
```JavaScript  
myDate = new Date();  
myDate.setHours(10, 30, 53, 400);  
  
document.write(myDate.getHours() + ":" + myDate.getMinutes() + ":" + myDate.getSeconds() +   
":" + myDate.getMilliseconds());  
  
// Output:   
// 10:30:53:400  
```  
  
## <a name="converting-strings-to-dates"></a>Převádění řetězců na data  
 Můžete zadat řetězce vytvořit `Date` objekty buď pomocí `Date(dateStr)` nebo s `Date.parse(dateStr)`. JavaScript Analýza řetězců data používá následující pravidla:  
  
-   Nejprve se pokusí analyzovat řetězec data pomocí [datum formátu ISO](#ISO).  
  
    > [!NOTE]
    >  JavaScript používá zjednodušené verzi rozšířeném formátu ISO 8601.  
  
-   Pokud není datum řetězec ve formátu ISO, JavaScript se pokusí analyzovat data pomocí jiných [ostatní formáty datum](#OtherDateFormats).  
  
<a name="ISO"></a>   
## <a name="iso-date-format"></a>ISO formát data  
 Není ve formátu ISO zjednodušení rozšířeném formátu ISO 8601. Formát vypadá takto:  
  
 `YYYY-MM-DDTHH:mm:ss.sssZ`  
  
> [!IMPORTANT]
>  Data formátu ISO nepodporuje režim standardů aplikace Internet Explorer 8 a Adaptivní režim.  
  
 Následující tabulka popisuje části tohoto formátu.  
  
|Symbol|Popis|Hodnoty|  
|------------|-----------------|------------|  
|`-`, `:`, `.`, `T`|Znaky ve skutečnosti v řetězci. `T`Určuje začátek čas.||  
|`YYYY`|Rok. Rozšířené roku lze namísto rok 4 číslice. Další informace najdete v tématu [rozšířené let](../javascript/date-and-time-strings-javascript.md#bkmk_extend) dál v tomto tématu.||  
|`MM`|Měsíc|01 až 12|  
|`DD`|Den v měsíci|01 až 31.|  
|`HH`|Hodiny|00 až 24|  
|`mm`|minut|00 do 59|  
|`ss`|Sekund. Sekundách a milisekundách jsou volitelné, pokud je zadaný čas.|00 do 59|  
|`sss`|počet milisekund|00 až 999|  
|`Z`|Hodnota v této pozici může být jedna z následujících akcí. Pokud hodnota je vynechán, použije se čas UTC.<br /><br /> -   `Z`označuje čas UTC.<br />-   `+hh:mm`Označuje, že vstupní čas je zadaný posun za čas UTC.<br />-   `-hh:mm`znamená, že vstupní čas není absolutní hodnotu zadaný posun před čas UTC.||  
  
 Řetězec může obsahovat datum, jako v následujících formátech: `YYYY`, `YYYY-MM`, `YYYY-MM-DD`.  
  
 Formátu ISO nepodporuje názvy časové pásmo. Můžete použít `Z` pozice zadat posun od času UTC. Pokud nezadáte hodnotu v `Z` umístit UTC používá čas.  
  
 Půlnoc můžete zadat pomocí 00:00, nebo pomocí 24:00 v předchozí den. Zadejte následující dva řetězce ve stejnou dobu: 2010-05-25T00:00 a 2010-05-24T24:00.  
  
 Chcete-li vrátit datum ve formátu ISO, můžete použít [toisostring – metoda (Date)](../javascript/reference/toisostring-method-date-javascript.md).  
  
<a name="bkmk_extend"></a>   
### <a name="extended-years"></a>Rozšířené roky  
 *Rozšířené roku* má 6 číslic místo 4 číslic a je předponou se znaménkem plus nebo minus. Je například rozšířená roku `+002010`, což je totéž jako `2010`. Rozšířené roku můžete použít k reprezentování let před roku 0 nebo po 9999.  
  
 Pokud používáte 6 číslic formátu, plus nebo mínus musí být přítomen. Když použijete formát 4 číslice, musí být přihlašovací chybí. Proto `0000` a `+000000` jsou přijata, ale `000000` a `-0001` dojít k chybě. Rozšířené roku 0 je považován za kladné a proto předponou znaménkem plus.  
  
 [Toisostring – metoda (Date)](../javascript/reference/toisostring-method-date-javascript.md) vždy používá formát rozšířené roku let, které jsou před 0 a po 9999.  
  
> [!NOTE]
>  [!INCLUDE[jsv9](../javascript/includes/jsv9-md.md)]  
  
<a name="OtherDateFormats"></a>   
## <a name="other-date-formats"></a>Další formáty data  
 Pokud není datum řetězec ve formátu ISO [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] používá následující pravidla jej analyzovat.  
  
 Krátká data  
  
-   Formát musí následovat pořadí měsíc/den/rok, třeba "06/08/2010".  
  
-   Buď "/" nebo "-" lze použít jako oddělovače.  
  
 Dlouhé kalendářních dat  
  
-   Rok, měsíc a den může být v libovolném pořadí. "8 června 2010" a "2010 června 8" jsou platné.  
  
-   V roce může mít dva nebo čtyři číslice. Pokud v roce má jenom dvě číslice, musí být alespoň 70.  
  
-   Měsíc a den názvy musí mít aspoň dva znaky. Dva názvy znaků, které nejsou jedinečné se přeloží na poslední odpovídající název. Například "Džu" Určuje července, není června.  
  
-   Den v týdnu je ignorována, pokud není konzistentní se zbytkem zadaného data. Například "Úterý 9 listopadu 1996" přeloží na "9 1996 listopadu pátek", protože pátek je správný den v týdnu pro toto datum.  
  
 Časy  
  
-   Hodiny, minuty a sekundy jsou oddělené dvojtečkou. Ale některé části lze vynechat. Platné jsou následující: "10:", "10:11" a "10: 11:12".  
  
-   Pokud je zadán PM a určenou hodinu je alespoň 13, je vrácena NaN. Například "23:15 PM" vrátí NaN.  
  
 Obecné  
  
-   Vrátí řetězec, který obsahuje neplatné datum NaN. Například vrátí řetězec, který obsahuje dva roky nebo dvou měsíců NaN.  
  
-   [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]podporuje všechny standardní časových pásmech a světového koordinovaného času (UTC) a greenwichský střední čas (GMT). (Formátu ISO nepodporuje časových pásem.)  
  
-   Text v závorkách, je zpracovaná jako komentář. Mohou být použity závorkách.  
  
-   Čárkami a prostory jsou zpracovány jako oddělovače. Je povoleno více oddělovačů.  
  
## <a name="example"></a>Příklad  
 Následující kód zobrazí výsledky analýzy řetězců různých data a času.  
  
```  
document.writeln((new Date("2010")).toUTCString());   
  
document.writeln((new Date("2010-06")).toUTCString());  
  
document.writeln((new Date("2010-06-09")).toUTCString());  
  
 // Specifies Z, which indicates UTC time.  
document.writeln((new Date("2010-06-09T15:20:00Z")).toUTCString());  
  
 // Specifies -07:00 offset, which is equivalent to Pacific Daylight time.  
document.writeln((new Date("2010-06-09T15:20:00-07:00")).toGMTString());  
  
// Specifies a non-ISO Long date.  
document.writeln((new Date("June 9, 2010")).toUTCString());  
  
// Specifies a non-ISO Long date.  
document.writeln((new Date("2010 June 9")).toUTCString());  
  
// Specifies a non-ISO Short date and time.  
document.writeln((new Date("6/9/2010 3:20 pm")).toUTCString());  
  
// Output:  
// Fri, 1 Jan 2010 00:00:00 UTC  
// Tue, 1 Jun 2010 00:00:00 UTC  
// Wed, 9 Jun 2010 00:00:00 UTC  
// Wed, 9 Jun 2010 15:20:00 UTC  
// Wed, 9 Jun 2010 22:20:00 UTC  
// Wed, 9 Jun 2010 07:00:00 UTC  
// Wed, 9 Jun 2010 07:00:00 UTC  
// Wed, 9 Jun 2010 22:20:00 UTC  
```  
  
 Tam, kde jsou zadány místní časy, výsledkem bude lišit v závislosti na časové pásmo.  
  
> [!IMPORTANT]
>  Data formátu ISO nepodporuje režim standardů aplikace Internet Explorer 8 a Adaptivní režim.  
  
## <a name="see-also"></a>Viz také  
 [Date – objekt](../javascript/reference/date-object-javascript.md)   
 [Date.Parse – funkce](../javascript/reference/date-parse-function-javascript.md)