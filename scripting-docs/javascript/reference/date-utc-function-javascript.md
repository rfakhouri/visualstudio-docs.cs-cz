---
title: "Date.UTC – funkce (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- UTC
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- UTC function [JavaScript]
- UTC dates, returning
- Date.UTC function [JavaScript]
ms.assetid: c0d67ce1-a47e-4dfd-bbf4-21619c406a0f
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a6a7c5622b74699e3d718ceb65e96638bdb6c3c5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="dateutc-function-javascript"></a>Date.UTC – funkce (JavaScript)
Vrátí počet milisekund, po mezi půlnoc, 1. ledna 1970 světového koordinovaného času (UTC) (nebo GMT) a se zadaným datem.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Date.UTC(year, month, day[, hours[, minutes[, seconds[,ms]]]])   
```  
  
## <a name="parameters"></a>Parametry  
 `year`  
 Požadováno. Je vyžadována pro přesné datum mezi století označení celý rok. Pokud `year` je od 0 do 99 se používá, pak `year` se považuje za 1900 + `year`.  
  
 `month`  
 Požadováno. V měsíci jako celé číslo mezi 0 a 11 (od prosince).  
  
 `day`  
 Požadováno. Datum jako celé číslo od 1 do 31.  
  
 `hours`  
 Volitelné. Je nutné zadat Pokud `minutes` pochází. Celé číslo od 0 do 23 (půlnoc do 23: 00) určující za hodinu.  
  
 `minutes`  
 Volitelné. Je nutné zadat Pokud `seconds` pochází. Celé číslo od 0 do 59 určující dobu, po které.  
  
 `seconds`  
 Volitelné. Je nutné zadat Pokud `milliseconds` pochází. Celé číslo od 0 do 59, určuje sekundách.  
  
 `ms`  
 Volitelné. Celé číslo od 0 do 999 určující milisekundách.  
  
## <a name="remarks"></a>Poznámky  
 `Date.UTC` Funkce vrátí počet milisekund, po mezi půlnoc, 1. ledna 1970 UTC a zadané datum. Mohou být používány tento návratovou hodnotu `setTime` metoda a v `Date` objekt konstruktor. Pokud hodnota argumentu je větší než jeho rozsah, nebo je na záporné číslo, jsou ostatní uložené hodnoty upravit odpovídajícím způsobem. Pokud zadáte 150 sekund, například [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] znovu definuje počet jako dvou minut a 30 sekund.  
  
 Rozdíl mezi `Date.UTC` funkce a `Date` objekt konstruktor, který přijímá datum je, že `Date.UTC` funkce předpokládá UTC a `Date` konstruktor objektu předpokládá místní čas.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `Date.UTC` funkce.  
  
```JavaScript  
// Determine the milliseconds per day.  
 var MinMilli = 1000 * 60;  
var HrMilli = MinMilli * 60;  
var DyMilli = HrMilli * 24;  
  
var date = new Date("June 1, 1990");  
var year = date.getFullYear();  
var month = date.getMonth();  
var day = date.getDay();  
  
var newDay = new Date("January 16, 2020");  
var yeartoday = newDay.getUTCFullYear();  
var monthtoday = newDay.getUTCMonth();  
var dayofmonthtoday = newDay.getUTCDate();  
  
// Get the milliseconds since 1/1/1970 UTC.  
var t1 = Date.UTC(year, month - 1, day)  
var t2 = Date.UTC(yeartoday, monthtoday, dayofmonthtoday);  
  
// Determine the difference in days.  
var days = (t2 - t1) / DyMilli;  
  
document.write(days);  
// Output: 10848  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [setTime – metoda (Date)](../../javascript/reference/settime-method-date-javascript.md)