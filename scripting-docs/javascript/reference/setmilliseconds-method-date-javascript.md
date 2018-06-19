---
title: setmilliseconds – metoda (Date) (JavaScript) | Microsoft Docs
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
- setMilliseconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- milliseconds
- setMilliseconds method
ms.assetid: 6c398961-130e-4f60-802f-6c30e1ef4de4
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f0cd339e1352511312ef9a9abf9a7ff02955c986
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791448"
---
# <a name="setmilliseconds-method-date-javascript"></a>setMilliseconds – metoda (Date) (JavaScript)
Nastaví hodnotu v milisekundách v `Date` pomocí místního času.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.  
setMilliseconds(  
numMilli  
)   
```  
  
## <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. Všechny `Date` objektu.  
  
 `numMilli`  
 Požadováno. Číselná hodnota stejná jako hodnota milisekundu.  
  
## <a name="remarks"></a>Poznámky  
 Pokud chcete nastavit hodnotu milisekundách pomocí světového koordinovaného času (UTC), použijte `setUTCMilliseconds` metoda.  
  
 Pokud hodnota `numMilli` je větší než 999 nebo záporné číslo, číslo uložené sekund (minut, hodin, a tak dále v případě potřeby) se zvýší, odpovídající velikostí.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `setMilliseconds` metoda.  
  
```JavaScript  
function SetMSecDemo(nmsec){  
   var d, s;                    // Declare variables.  
   d = new Date();              // Create Date object.  
   d.setMilliseconds(nmsec);    // Set milliseconds.  
   s = "Current setting is ";  
   s += d.toLocaleString();  
   s += " and " + d.getMilliseconds();  
   s += " milliseconds";  
   return(s);                   // Return new date setting.  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getMilliseconds – metoda (Date)](../../javascript/reference/getmilliseconds-method-date-javascript.md)   
 [getUTCMilliseconds – metoda (Date)](../../javascript/reference/getutcmilliseconds-method-date-javascript.md)   
 [setUTCMilliseconds – metoda (Date)](../../javascript/reference/setutcmilliseconds-method-date-javascript.md)