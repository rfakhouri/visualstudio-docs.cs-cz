---
title: Date – objekt (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- Date
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Date object
- dates, determining
ms.assetid: ce2202bb-7ec9-4f5a-bf48-3a04feff283e
caps.latest.revision: 29
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eb5d53f3bddfeb3a3ed1ab36e2b4be822964eba5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792105"
---
# <a name="date-object-javascript"></a>Date – objekt (JavaScript)
Umožňuje základní ukládání a načítání data a časy.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      dateObj = new Date()  
dateObj = new Date(dateVal)  
dateObj = new Date(year, month, date[, hours[, minutes[, seconds[,ms]]]])   
```  
  
## <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. Název proměnné, do kterého `Date` objekt je přiřazen.  
  
 `dateVal`  
 Požadováno. Pokud číselnou hodnotu, `dateVal` představuje počet milisekund, po v světového koordinovaného času mezi k zadanému datu a půlnoc 1. ledna 1970. Pokud řetězec, `dateVal` je analyzována souladu s pravidly v [řetězců data a času](../../javascript/date-and-time-strings-javascript.md). `dateVal` Argument může být také hodnotu VT_DATE – vrácený z některé objekty ActiveX.  
  
 `year`  
 Požadováno. Celý rok, například 1976 (a ne 76).  
  
 `month`  
 Požadováno. V měsíci jako celé číslo mezi 0 a 11 (od prosince).  
  
 `date`  
 Požadováno. Datum jako celé číslo od 1 do 31.  
  
 `hours`  
 Volitelné. Je nutné zadat Pokud `minutes` pochází. Celé číslo od 0 do 23 (půlnoc do 23: 00) určující za hodinu.  
  
 minuty  
 Volitelné. Je nutné zadat Pokud `seconds` pochází. Celé číslo od 0 do 59 určující dobu, po které.  
  
 `seconds`  
 Volitelné. Je nutné zadat Pokud `milliseconds` pochází. Celé číslo od 0 do 59, určuje sekundách.  
  
 `ms`  
 Volitelné. Celé číslo od 0 do 999 určující milisekundách.  
  
## <a name="remarks"></a>Poznámky  
 A `Date` objekt obsahuje číslo, které představuje konkrétní rychlých do čas v rámci milisekund. Pokud hodnota argumentu je větší než jeho rozsah, nebo je na záporné číslo, jsou ostatní uložené hodnoty upravit odpovídajícím způsobem. Pokud zadáte 150 sekund, například [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] znovu definuje počet jako dvou minut a 30 sekund.  
  
 Pokud je číslo `NaN`, objekt nepředstavuje konkrétní rychlých času. Pokud předáte žádné parametry `Date` objekt, je inicializováno aktuální čas (UTC). Hodnota musí být uvedeny do objektu, abyste mohli používat.  
  
 Rozsah kalendářních dat, které může být reprezentován v `Date` objektu je přibližně 285,616 let na obou stranách 1. ledna 1970.  
  
 V tématu [výpočet dat a časů (JavaScript)](../../javascript/calculating-dates-and-times-javascript.md) Další informace o tom, jak používat `Date` objekt a související metody.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `Date` objektu.  
  
```JavaScript  
var dateString = "Today's date is: ";  
  
var newDate = new Date();  
  
// Get the month, day, and year.  
dateString += (newDate.getMonth() + 1) + "/";  
dateString += newDate.getDate() + "/";  
dateString += newDate.getFullYear();  
  
document.write(dateString);  
  
// Output: Today's date is: <date>  
```  
  
## <a name="requirements"></a>Požadavky  
 `Date object` Byla zavedena v [!INCLUDE[jsv1text](../../javascript/reference/includes/jsv1text-md.md)]. Některé členy v následujících seznamech byly zavedeny v pozdějších verzích. Další informace najdete v tématu [informace o verzi](../../javascript/reference/javascript-version-information.md) nebo v dokumentaci pro jednotlivé členy.  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí vlastnosti `Date Object`.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[constructor – vlastnost](../../javascript/reference/constructor-property-date.md)|Určuje funkci, která vytvoří objekt.|  
|[prototype – vlastnost](../../javascript/reference/prototype-property-date.md)|Vrátí odkaz na prototyp třídy objektů.|  
  
## <a name="functions"></a>Funkce  
 Následující tabulka uvádí funkce `Date Object`.  
  
|Funkce|Popis|  
|---------------|-----------------|  
|[Date.Now – funkce](../../javascript/reference/date-now-function-javascript.md)|Vrátí počet milisekund, po mezi 1. ledna 1970 a aktuální datum a čas.|  
|[Date.Parse – funkce](../../javascript/reference/date-parse-function-javascript.md)|Analyzuje řetězec obsahující data a vrátí počet milisekund, mezi které datum a půlnoc, 1. ledna 1970.|  
|[Date.UTC – funkce](../../javascript/reference/date-utc-function-javascript.md)|Vrátí počet milisekund, po mezi půlnoc, 1. ledna 1970 světového koordinovaného času (UTC) (nebo GMT) a zadané datum.|  
  
<a name="js56jsobjdatemeth"></a>   
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `Date Object`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[getDate – metoda](../../javascript/reference/getdate-method-date-javascript.md)|Vrátí den v měsíci hodnotu pomocí místního času.|  
|[getDay – metoda](../../javascript/reference/getday-method-date-javascript.md)|Vrátí den v týdnu hodnotu pomocí místního času.|  
|[getFullYear – metoda](../../javascript/reference/getfullyear-method-date-javascript.md)|Vrátí hodnotu roku pomocí místního času.|  
|[getHours – metoda](../../javascript/reference/gethours-method-date-javascript.md)|Vrátí hodnotu čas pomocí místního času.|  
|[getMilliseconds – metoda](../../javascript/reference/getmilliseconds-method-date-javascript.md)|Vrátí hodnotu milisekundách pomocí místního času.|  
|[getMinutes – metoda](../../javascript/reference/getminutes-method-date-javascript.md)|Vrátí hodnotu minut pomocí místního času.|  
|[getMonth – metoda](../../javascript/reference/getmonth-method-date-javascript.md)|Vrací hodnotu měsíce pomocí místního času.|  
|[getSeconds – metoda](../../javascript/reference/getseconds-method-date-javascript.md)|Vrátí hodnotu sekund pomocí místního času.|  
|[getTime – metoda](../../javascript/reference/gettime-method-date-javascript.md)|Vrátí hodnotu času v `Date` objektu jako počet milisekund od 1. ledna 1970.|  
|[getTimezoneOffset – metoda](../../javascript/reference/gettimezoneoffset-method-date-javascript.md)|Vrátí rozdíl v minutách mezi časem na hostitelském počítači a světového koordinovaného času (UTC).|  
|[getUTCDate – metoda](../../javascript/reference/getutcdate-method-date-javascript.md)|Vrátí den v měsíci hodnotu formátu UTC.|  
|[getUTCDay – metoda](../../javascript/reference/getutcday-method-date-javascript.md)|Vrátí den v týdnu hodnotu formátu UTC.|  
|[getUTCFullYear – metoda](../../javascript/reference/getutcfullyear-method-date-javascript.md)|Vrátí hodnotu roku formátu UTC.|  
|[getUTCHours – metoda](../../javascript/reference/getutchours-method-date-javascript.md)|Vrátí hodnotu čas formátu UTC.|  
|[getUTCMilliseconds – metoda](../../javascript/reference/getutcmilliseconds-method-date-javascript.md)|Vrátí hodnotu milisekundách formátu UTC.|  
|[getUTCMinutes – metoda](../../javascript/reference/getutcminutes-method-date-javascript.md)|Vrátí hodnotu minut pomocí standardu UTC.|  
|[getUTCMonth – metoda](../../javascript/reference/getutcmonth-method-date-javascript.md)|Vrátí hodnotu měsíce formátu UTC.|  
|[getUTCSeconds – metoda](../../javascript/reference/getutcseconds-method-date-javascript.md)|Vrátí počet sekund hodnotu formátu UTC.|  
|[getVarDate – metoda](../../javascript/reference/getvardate-method-date-javascript.md)|Vrátí hodnotu VT_DATE – v `Date` objektu.|  
|[getYear – metoda](../../javascript/reference/getyear-method-date-javascript.md)|Vrátí hodnotu roku.|  
|[hasOwnProperty – metoda](../../javascript/reference/hasownproperty-method-object-javascript.md)|Vrátí logickou hodnotu, která označuje, zda má objekt vlastnost se zadaným názvem.|  
|[isPrototypeOf – metoda](../../javascript/reference/isprototypeof-method-object-javascript.md)|Vrátí logickou hodnotu, která označuje, zda objekt existuje v řetězci prototypu jiného objektu.|  
|[propertyIsEnumerable – metoda](../../javascript/reference/propertyisenumerable-method-object-javascript.md)|Vrátí logickou hodnotu, která označuje, zda zadaná vlastnost je součástí objektu a zda je vyčíslitelná.|  
|[setDate – metoda](../../javascript/reference/setdate-method-date-javascript.md)|Nastaví numerický den v měsíci pomocí místního času.|  
|[setFullYear – metoda](../../javascript/reference/setfullyear-method-date-javascript.md)|Nastaví hodnotu roku pomocí místního času.|  
|[setHours – metoda](../../javascript/reference/sethours-method-date-javascript.md)|Nastaví hodnotu hodiny pomocí místního času.|  
|[setmilliseconds – metoda](../../javascript/reference/setmilliseconds-method-date-javascript.md)|Nastaví hodnotu milisekundách pomocí místního času.|  
|[setMinutes – metoda](../../javascript/reference/setminutes-method-date-javascript.md)|Nastaví hodnotu minut pomocí místního času.|  
|[setMonth – metoda](../../javascript/reference/setmonth-method-date-javascript.md)|Nastaví hodnotu měsíce pomocí místního času.|  
|[setSeconds – metoda](../../javascript/reference/setseconds-method-date-javascript.md)|Nastaví hodnotu pomocí místního času sekundách.|  
|[setTime – metoda](../../javascript/reference/settime-method-date-javascript.md)|Nastaví hodnotu data a času v `Date` objektu.|  
|[setUTCDate – metoda](../../javascript/reference/setutcdate-method-date-javascript.md)|Nastaví numerický den v měsíci, ve formátu UTC.|  
|[setUTCFullYear – metoda](../../javascript/reference/setutcfullyear-method-date-javascript.md)|Nastaví hodnotu roku formátu UTC.|  
|[setUTCHours – metoda](../../javascript/reference/setutchours-method-date-javascript.md)|Nastaví hodnotu hodiny formátu UTC.|  
|[setUTCMilliseconds – metoda](../../javascript/reference/setutcmilliseconds-method-date-javascript.md)|Nastaví hodnotu milisekundách formátu UTC.|  
|[setUTCMinutes – metoda](../../javascript/reference/setutcminutes-method-date-javascript.md)|Nastaví hodnotu minut pomocí standardu UTC.|  
|[setUTCMonth – metoda](../../javascript/reference/setutcmonth-method-date-javascript.md)|Nastaví hodnotu měsíce formátu UTC.|  
|[setUTCSeconds – metoda](../../javascript/reference/setutcseconds-method-date-javascript.md)|Nastaví počet sekund hodnotu formátu UTC.|  
|[setYear – metoda](../../javascript/reference/setyear-method-date-javascript.md)|Nastaví hodnotu roku pomocí místního času.|  
|[toDateString – metoda](../../javascript/reference/todatestring-method-date-javascript.md)|Vrátí data jako hodnotu řetězce.|  
|[toGMTString – metoda](../../javascript/reference/togmtstring-method-date-javascript.md)|Vrátí datum převedeno na řetězec pomocí greenwichský střední čas (GMT).|  
|[toisostring – metoda](../../javascript/reference/toisostring-method-date-javascript.md)|Vrátí data jako hodnotu řetězce ve formátu ISO.|  
|[tojson – metoda](../../javascript/reference/tojson-method-date-javascript.md)|Použitá k transformaci dat typu objektu před serializaci do formátu JSON.|  
|[toLocaleDateString – metoda](../../javascript/reference/tolocaledatestring-method-date-javascript.md)|Vrátí data jako hodnotu řetězce pro aktuální národní prostředí hostitelském prostředí.|  
|[toLocaleString – metoda](../../javascript/reference/tolocalestring-date.md)|Vrátí objekt převedeno na řetězec pomocí aktuální národní prostředí.|  
|[toLocaleTimeString – metoda](../../javascript/reference/tolocaletimestring-method-date-javascript.md)|Vrátí dobu jako hodnotu řetězce pro aktuální národní prostředí hostitelském prostředí.|  
|[toString – metoda](../../javascript/reference/tostring-method-date.md)|Vrátí řetězcovou reprezentaci objektu.|  
|[toTimeString – metoda](../../javascript/reference/totimestring-method-date-javascript.md)|Vrátí dobu jako hodnotu řetězce.|  
|[toUTCString – metoda](../../javascript/reference/toutcstring-method-date-javascript.md)|Vrátí datum převedeno na řetězec formátu UTC.|  
|[valueOf – metoda](../../javascript/reference/valueof-method-date.md)|Vrátí primitivní hodnotu zadaného objektu.|  
  
## <a name="see-also"></a>Viz také  
 [Výpočet dat a časů (JavaScript)](../../javascript/calculating-dates-and-times-javascript.md)   
 [Řetězce data a času](../../javascript/date-and-time-strings-javascript.md)