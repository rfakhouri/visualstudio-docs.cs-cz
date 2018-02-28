---
title: "setMinutes – metoda (Date) (JavaScript) | Microsoft Docs"
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
- setMinutes
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- minutes
- setMinutes method
ms.assetid: 34c959cd-cd29-4cee-8e04-9061cf6d42f3
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1ce40cb3ebf769cdd8f668e246e272833780434d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="setminutes-method-date-javascript"></a>setMinutes – metoda (Date) (JavaScript)
Nastaví hodnotu minut v **datum** pomocí místního času.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.setMinutes(numMinutes[, numSeconds[, numMilli]])   
```  
  
## <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. Všechny `Date` objektu.  
  
 `numMinutes`  
 Požadováno. Číselná hodnota stejná jako hodnota minut. Je nutné zadat Pokud některý z následujících argumentů se používá.  
  
 *Počet_sekund*  
 Volitelné. Číselná hodnota stejná jako hodnota sekund. Musíte zadat, pokud `numMilli` použit argument.  
  
 `numMilli`  
 Volitelné. Číselná hodnota stejná jako hodnota milisekundách.  
  
## <a name="remarks"></a>Poznámky  
 Všechny **nastavit** hodnota vrácená z odpovídající pomocí metody trvá volitelné argumenty **získat** metody, pokud nezadáte za volitelným argumentem. Například pokud *Počet_sekund* argument není zadaný, [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] používá hodnotu vrácenou z `getSeconds` metoda.  
  
 Pokud chcete nastavit hodnotu minut pomocí světového koordinovaného času (UTC), použijte `setUTCMinutes` metoda.  
  
 Pokud hodnota argumentu je větší než jeho rozsah, nebo je na záporné číslo, jsou ostatní uložené hodnoty upravit odpovídajícím způsobem. Například, pokud je uložená data "5 ledna 1996 00:00:00" a **setMinutes(90)** je volána, data se změní na "5 ledna 1996 01:30:00." Záporná čísla se chovají podobně jako.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `setMinutes` metoda.  
  
```JavaScript  
function SetMinutesDemo(nmin, nsec){  
   var d, s;                     // Declare variables.  
   d = new Date();               // Create Date object.  
   d.setMinutes(nmin, nsec);     // Set minutes.  
   s = "Current setting is " + d.toLocaleString()   
   return(s);                    // Return new setting.  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getMinutes – metoda (Date)](../../javascript/reference/getminutes-method-date-javascript.md)   
 [getUTCMinutes – metoda (Date)](../../javascript/reference/getutcminutes-method-date-javascript.md)   
 [setUTCMinutes – metoda (Date)](../../javascript/reference/setutcminutes-method-date-javascript.md)