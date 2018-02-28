---
title: "setUTCMonth – metoda (Date) (JavaScript) | Microsoft Docs"
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
- setUTCMonth
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, UTC
- setUTCMonth method
- Month method
- UTC dates, setting
ms.assetid: cdac5f64-c4fd-44cc-ba3a-9a8dd3dd3fad
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 02cb69026b66e3f307a8709ab3f5b23d9518643a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="setutcmonth-method-date-javascript"></a>setUTCMonth – metoda (Date) (JavaScript)
Nastaví hodnotu měsíce v `Date` pomocí světového koordinovaného času (UTC).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.setUTCMonth(numMonth[, dateVal])   
```  
  
## <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. Všechny `Date` objektu.  
  
 `numMonth`  
 Požadováno. Číselná hodnota rovna v měsíci. Hodnota pro leden je 0 a ostatní měsíc hodnoty podle za sebou.  
  
 `dateVal`  
 Volitelné. Číselná hodnota představující den v měsíci. Pokud není uvedený hodnota z volání `getUTCDate` metoda se používá.  
  
## <a name="remarks"></a>Poznámky  
 Chcete-li nastavena hodnota měsíce pomocí místního času, použijte `setMonth` metoda.  
  
 Pokud hodnota `numMonth` je větší než 11 (leden je měsíc 0), nebo záporné číslo, uložené roku je zvýšena nebo snížena správně. Například, pokud uložená data "5 ledna 1996 00:00:00.00" a **setUTCMonth(14)** je volána, data se změní na "5 března 1997 00:00:00.00."  
  
 **SetUTCFullYear** metoda slouží k nastavení rok, měsíc a den v měsíci.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `setUTCMonth` metoda.  
  
```JavaScript  
function SetUTCMonthDemo(newmonth){  
   var d, s;                       // Declare variables.  
   d = new Date();                 // Create Date object.  
   d.setUTCMonth(newmonth);        // Set UTC month.  
   s = "Current setting is ";  
   s += d.toUTCString();   
   return(s);                      // Return new setting.  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getMonth – metoda (Date)](../../javascript/reference/getmonth-method-date-javascript.md)   
 [getUTCMonth – metoda (Date)](../../javascript/reference/getutcmonth-method-date-javascript.md)   
 [setMonth – metoda (Date)](../../javascript/reference/setmonth-method-date-javascript.md)