---
title: setUTCMilliseconds – metoda (Date) (JavaScript) | Microsoft Docs
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
- setUTCMilliseconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- milliseconds
- dates, UTC
- UTC times, setting
- setUTCMilliseconds method
ms.assetid: ed8e4486-d4b2-4b73-836b-dd1d3bb991a0
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 279d00b256b3b0763e2f15f549fdc6ee81c20254
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791532"
---
# <a name="setutcmilliseconds-method-date-javascript"></a>setUTCMilliseconds – metoda (Date) (JavaScript)
Nastaví hodnotu v milisekundách v `Date` pomocí světového koordinovaného času (UTC).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.setUTCMilliseconds(numMilli)   
```  
  
## <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. Všechny `Date` objektu.  
  
 `numMilli`  
 Požadováno. Číselná hodnota stejná jako hodnota milisekundu.  
  
## <a name="remarks"></a>Poznámky  
 Pokud chcete nastavit milisekundách pomocí místního času, použijte `setMilliseconds` metoda.  
  
 Pokud hodnota `numMilli` je větší než 999 nebo záporné číslo, číslo uložené sekund (minut, hodin, a tak dále, v případě potřeby) se zvýší, odpovídající velikostí.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `setUTCMilliseconds` metoda.  
  
```JavaScript  
function SetUTCMSecDemo(nmsec){     
// Create Date object.  
   var d = new Date();             
// Set UTC milliseconds.  
   d.setUTCMilliseconds(nmsec);    
  
   var s = "Current setting is ";  
   s += d.toUTCString();  
   s += " and " + d.getUTCMilliseconds();  
   s += " milliseconds"  
   return(s);  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getMilliseconds – metoda (Date)](../../javascript/reference/getmilliseconds-method-date-javascript.md)   
 [getUTCMilliseconds – metoda (Date)](../../javascript/reference/getutcmilliseconds-method-date-javascript.md)   
 [setmilliseconds – metoda (Date)](../../javascript/reference/setmilliseconds-method-date-javascript.md)