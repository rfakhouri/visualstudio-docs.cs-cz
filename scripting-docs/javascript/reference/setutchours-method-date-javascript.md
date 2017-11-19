---
title: "setUTCHours – metoda (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: setUTCHours
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, UTC
- UTC times, setting
- setUTCHours method
ms.assetid: 257e36fd-fb06-4a4d-8634-d66a020a1511
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9fe83735028f86d38ef270beac6c44dfa4caae7f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="setutchours-method-date-javascript"></a>setUTCHours – metoda (Date) (JavaScript)
Nastaví hodnotu hodiny v `Date` pomocí světového koordinovaného času (UTC).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.setUTCHours(numHours[, numMin[, numSec[, numMilli]]])   
```  
  
## <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. Všechny `Date` objektu.  
  
 `numHours`  
 Požadováno. Číselná hodnota stejná jako hodnota hodin.  
  
 `numMin`  
 Volitelné. Číselná hodnota stejná jako hodnota minut. Je nutné zadat Pokud buď `numSec` nebo `numMilli` se používají.  
  
 `numSec`  
 Volitelné. Číselná hodnota stejná jako hodnota sekund. Je nutné zadat Pokud `numMilli` použit argument.  
  
 `numMilli`  
 Volitelné. Číselná hodnota stejná jako hodnota milisekundách.  
  
## <a name="remarks"></a>Poznámky  
 Všechny **nastavit** hodnota vrácená z odpovídající pomocí metody trvá volitelné argumenty **získat** metody, pokud nezadáte za volitelným argumentem. Například pokud `numMin` argument není zadán, [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] používá hodnotu vrácenou z `getUTCMinutes` metoda.  
  
 Pokud chcete nastavit hodnotu hodiny pomocí místního času, použijte `setHours` metoda.  
  
 Pokud hodnota argumentu je větší než jeho rozsah, nebo je na záporné číslo, jsou ostatní uložené hodnoty upravit odpovídajícím způsobem. Například, pokud uložená data "5 ledna 1996 00:00:00.00" a **setUTCHours(30)** je volána, data se změní na "6 ledna 1996 06:00:00.00."  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `setUTCHours` metoda.  
  
```JavaScript  
function SetUTCHoursDemo(nhr, nmin, nsec){     
   var d, s;                        // Declare variables.  
   d = new Date();                  // Create Date object.  
   d.setUTCHours(nhr, nmin, nsec);  // Set UTC hours, minutes, seconds.  
   s = "Current setting is " + d.toUTCString()   
   return(s);                       // Return new setting.  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getHours – metoda (Date)](../../javascript/reference/gethours-method-date-javascript.md)   
 [getUTCHours – metoda (Date)](../../javascript/reference/getutchours-method-date-javascript.md)   
 [setHours – metoda (Date)](../../javascript/reference/sethours-method-date-javascript.md)