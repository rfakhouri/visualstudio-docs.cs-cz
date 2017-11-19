---
title: "setHours – metoda (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: setHours
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- hours
- setHours method
- dates, setting
ms.assetid: 460f742d-f8d2-4874-9d07-2fb969fef066
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f9757f8416953eaf756dba96b91100527606cf9c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="sethours-method-date-javascript"></a>setHours – metoda (Date) (JavaScript)
Nastaví hodnotu hodiny v `Date` pomocí místního času.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.setHours(numHours[, numMin[, numSec[, numMilli]]])   
```  
  
## <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. Všechny `Date` objektu.  
  
 `numHours`  
 Požadováno. Číselná hodnota stejná jako hodnota hodin.  
  
 `numMin`  
 Volitelné. Číselná hodnota stejná jako hodnota minut. Je nutné zadat Pokud některý z následujících argumentů se používá.  
  
 `numSec`  
 Volitelné. Číselná hodnota stejná jako hodnota sekund. Musíte zadat, pokud se používá následující argument.  
  
 `numMilli`  
 Volitelné. Číselná hodnota stejná jako hodnota milisekundách.  
  
## <a name="remarks"></a>Poznámky  
 Všechny **nastavit** hodnota vrácená z odpovídající pomocí metody trvá volitelné argumenty **získat** metody, pokud nezadáte za volitelným argumentem. Například pokud `numMinutes` argument není zadán, [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] používá hodnotu vrácenou z `getMinutes` metoda.  
  
 Pokud chcete nastavit hodnotu hodiny pomocí světového koordinovaného času (UTC), použijte `setUTCHours` metoda.  
  
 Pokud hodnota argumentu je větší než jeho rozsah, nebo je na záporné číslo, jsou ostatní uložené hodnoty upravit odpovídajícím způsobem. Například, pokud je uložená data "5 ledna 1996 00:00:00", a **setHours(30)** je volána, data se změní na "6 ledna 1996 06:00:00." Záporná čísla se chovají podobně jako.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `setHours` metoda.  
  
```JavaScript  
function SetHoursDemo(nhr, nmin, nsec){  
   var d, s;                     //Declare variables.  
   d = new Date();               //Create Date object.  
   d.setHours(nhr, nmin, nsec);  //Set hours, minutes, & seconds.  
   s = "Current setting is " + d.toLocaleString()   
   return(s);                    //Return new date setting.  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getHours – metoda (Date)](../../javascript/reference/gethours-method-date-javascript.md)   
 [getUTCHours – metoda (Date)](../../javascript/reference/getutchours-method-date-javascript.md)   
 [setUTCHours – metoda (Date)](../../javascript/reference/setutchours-method-date-javascript.md)