---
title: "setDate – metoda (Date) (JavaScript) | Microsoft Docs"
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
- setDate
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- setDate method
- dates, setting
ms.assetid: a84b9b01-a6d0-489f-8a13-e7af9e9630b2
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8d74340287b3a7348419d302f79775eb610c6983
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="setdate-method-date-javascript"></a>setDate – metoda (Date) (JavaScript)
Nastaví číselnou hodnotu dne v měsíci `Date` pomocí místního času.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.setDate(numDate)   
```  
  
## <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. Všechny `Date` objektu.  
  
 `numDate`  
 Požadováno. Číselná hodnota rovna den v měsíci.  
  
## <a name="remarks"></a>Poznámky  
 Pokud chcete nastavit hodnotu dne v měsíci pomocí světového koordinovaného času (UTC), použijte `setUTCDate` metoda.  
  
 Pokud hodnota `numDate` je větší než počet dní v měsíci, datum zobrazí souhrn přes na novější měsíc nebo rok. Například, pokud uložená datum je 5. ledna 1996 a `setDate(32)` je volána, datum změny 1 února 1996. Pokud `numDate` záporné číslo, datum zobrazí zpět do starší měsíc a rok. Například, pokud uložená datum je 5. ledna 1996 a `setDate(-32)` je volána, datum změny 29 listopadu 1995.  
  
 [SetFullYear – metoda (Date)](../../javascript/reference/setfullyear-method-date-javascript.md) můžete použít k nastavení rok, měsíc a den v měsíci.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `setDate` metoda.  
  
```JavaScript  
var date = new Date("12/15/1990");  
date.setDate(30);  
document.write(date);  
  
// Output (for the PST time zone): Sun Dec 30 00:00:00 PST 1990  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getDate – metoda (Date)](../../javascript/reference/getdate-method-date-javascript.md)   
 [setFullYear – metoda (Date)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setMonth – metoda (Date)](../../javascript/reference/setmonth-method-date-javascript.md)   
 [setUTCDate – metoda (Date)](../../javascript/reference/setutcdate-method-date-javascript.md)