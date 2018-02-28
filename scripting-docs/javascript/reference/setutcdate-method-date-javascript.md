---
title: "setUTCDate – metoda (Date) (JavaScript) | Microsoft Docs"
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
- setUTCDate
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, UTC
- dates, setting
- UTC dates, setting
- setUTCDate method
ms.assetid: e6c3b876-70fe-4103-b197-6c84c078ce10
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5631a36c8b1c4f1ee50dcadb39f0f21ae5aa28e3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="setutcdate-method-date-javascript"></a>setUTCDate – metoda (Date) (JavaScript)
Nastaví číselnou den v měsíci v `Date` pomocí světového koordinovaného času (UTC).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.setUTCDate(numDate)   
```  
  
## <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. Všechny `Date` objektu.  
  
 *numDate*  
 Požadováno. Číselná hodnota rovna den v měsíci.  
  
## <a name="remarks"></a>Poznámky  
 Pokud chcete nastavit den v měsíci pomocí místního času, použijte `setDate` metoda.  
  
 Pokud hodnota *numDate* je větší než počet dní v měsíci uložené v **datum** objektu nebo záporné číslo, datum je nastaven na datum rovna *numDate* minus počet dní v měsíci uložené. Například, pokud uložená datum je 5. ledna 1996 a **setUTCDate(32)** je volána, datum změny 1 února 1996. Záporná čísla se chovají podobně jako.  
  
 **SetUTCFullYear** metoda slouží k nastavení rok, měsíc a den v měsíci.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `setUTCDate` metoda.  
  
```JavaScript  
function SetUTCDateDemo(newdayofmonth){  
   var d = new Date();           // Create Date object.  
   d.setUTCDate(newdayofmonth);  // Set UTC day of month.  
   var s = "Current setting is ";  
   s += d.toUTCString();   
   return(s);                    // Return new setting.  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getDate – metoda (Date)](../../javascript/reference/getdate-method-date-javascript.md)   
 [getUTCDate – metoda (Date)](../../javascript/reference/getutcdate-method-date-javascript.md)   
 [setDate – metoda (Date)](../../javascript/reference/setdate-method-date-javascript.md)