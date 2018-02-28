---
title: "setUTCMinutes – metoda (Date) (JavaScript) | Microsoft Docs"
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
- setUTCMinutes
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- minutes
- dates, UTC
- UTC times, setting
- setUTCMinutes method
ms.assetid: 2415e788-6d28-46dd-a103-0931a1fd1446
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 37df1bcefa358f2c9076a3da877bd642d19178b0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="setutcminutes-method-date-javascript"></a>setUTCMinutes – metoda (Date) (JavaScript)
Nastaví hodnotu minut v `Date` pomocí světového koordinovaného času (UTC).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.setUTCMinutes(numMinutes[, numSeconds[, numMilli]])   
```  
  
## <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. Všechny `Date` objektu.  
  
 `numMinutes`  
 Požadováno. Číselná hodnota stejná jako hodnota minut. Je nutné zadat Pokud některý z následujících argumentů se používá.  
  
 *Počet_sekund*  
 Volitelné. Číselná hodnota stejná jako hodnota sekund. Je nutné zadat Pokud `numMilli` se používá.  
  
 `numMilli`  
 Volitelné. Číselná hodnota stejná jako hodnota milisekundách.  
  
## <a name="remarks"></a>Poznámky  
 Všechny **nastavit** hodnota vrácená z odpovídající pomocí metody trvá volitelné argumenty **získat** metody, pokud nezadáte za volitelným argumentem. Například pokud *Počet_sekund* argument není zadán, [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] používá hodnotu vrácenou z `getUTCSeconds` metoda.  
  
 Chcete-li změnit hodnotu minut pomocí místního času, použijte `setMinutes` metoda.  
  
 Pokud hodnota argumentu je větší než jeho rozsah, nebo je na záporné číslo, jsou ostatní uložené hodnoty upravit odpovídajícím způsobem. Například, pokud uložená data "5 ledna 1996 00:00:00.00" a **setUTCMinutes(70)** je volána, data se změní na "5 ledna 1996 01:10:00.00."  
  
 **SetUTCHours** metoda umožňuje nastavit hodiny, minuty, sekundách a milisekundách.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `setUTCMinutes` metoda:  
  
```JavaScript  
function SetUTCMinutesDemo(nmin, nsec){  
   var d, s;                    // Declare variables.  
   d = new Date();              // Create Date object.  
   d.setUTCMinutes(nmin,nsec);  // Set UTC minutes.  
   s = "Current setting is " + d.toUTCString()   
   return(s);                   // Return new setting.  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getMinutes – metoda (Date)](../../javascript/reference/getminutes-method-date-javascript.md)   
 [getUTCMinutes – metoda (Date)](../../javascript/reference/getutcminutes-method-date-javascript.md)   
 [setMinutes – metoda (Date)](../../javascript/reference/setminutes-method-date-javascript.md)