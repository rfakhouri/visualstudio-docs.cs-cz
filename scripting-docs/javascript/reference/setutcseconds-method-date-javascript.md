---
title: setUTCSeconds – metoda (Date) (JavaScript) | Microsoft Docs
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
- setUTCSeconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, UTC
- setUTCSeconds method
- UTC times, setting
- seconds method
ms.assetid: e035e282-b39d-4d1d-8771-c17542fd6493
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f3df010cd84332d8957f1c08c41c4543dec36e4a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791670"
---
# <a name="setutcseconds-method-date-javascript"></a>setUTCSeconds – metoda (Date) (JavaScript)
Nastaví hodnotu sekundách v `Date` pomocí světového koordinovaného času (UTC).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.setUTCSeconds(numSeconds[, numMilli])   
```  
  
## <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. Všechny `Date` objektu.  
  
 *Počet_sekund*  
 Požadováno. Číselná hodnota stejná jako hodnota sekund.  
  
 `numMilli`  
 Volitelné. Číselná hodnota stejná jako hodnota milisekundách.  
  
## <a name="remarks"></a>Poznámky  
 Všechny **nastavit** hodnota vrácená z odpovídající pomocí metody trvá volitelné argumenty **získat** metody, pokud nezadáte za volitelným argumentem. Například pokud `numMilli` argument není zadán, [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] používá hodnotu vrácenou z `getUTCMilliseconds` metoda.  
  
 Chcete-li nastavit hodnotu pomocí místního času sekundách, použijte `setSeconds` metoda.  
  
 Pokud hodnota argumentu je větší než jeho rozsah, nebo je na záporné číslo, jsou ostatní uložené hodnoty upravit odpovídajícím způsobem. Například, pokud uložená data "5 ledna 1996 00:00:00.00" a **setSeconds(150)** je volána, data se změní na "5 ledna 1996 00:02:30.00."  
  
 **SetUTCHours** metoda umožňuje nastavit hodiny, minuty, sekundách a milisekundách.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `setUTCSeconds` metoda.  
  
```JavaScript  
function SetUTCSecondsDemo(nsec){  
// Create Date object.  
    var d = new Date();       
// Set UTC seconds.  
    d.setUTCSeconds(nsec);    
    var s = "Current setting is ";  
    s += d.toUTCString();  
// Return new setting.  
    return(s);                
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getSeconds – metoda (Date)](../../javascript/reference/getseconds-method-date-javascript.md)   
 [getUTCSeconds – metoda (Date)](../../javascript/reference/getutcseconds-method-date-javascript.md)   
 [setSeconds – metoda (Date)](../../javascript/reference/setseconds-method-date-javascript.md)