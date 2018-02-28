---
title: "getMonth – metoda (Date) (JavaScript) | Microsoft Docs"
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
- getMonth
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Date object
- dates, month value
- Month method
- GetMonth method
ms.assetid: c20dd8ba-1d78-42f1-8717-ed3dfd2362dd
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eeffd7ffc7bee5fa63607e342a9a9dced7088d35
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="getmonth-method-date-javascript"></a>getMonth – metoda (Date) (JavaScript)
Získá v měsíci, pomocí místního času.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.getMonth()   
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `dateObj` je odkaz `Date` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 `getMonth` Metoda vrátí celé číslo mezi 0 (leden) a 11 (prosinec). Pro `Date` zkonstruovat s "5 ledna 1996", `getMonth` vrátí hodnotu 0.  
  
## <a name="remarks"></a>Poznámky  
 Hodnota měsíce pomocí světového koordinovaného času (UTC), použijte `getUTCMonth` metoda.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `getMonth` metoda.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getMonth());  
  
// Output: 0  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getUTCMonth – metoda (Date)](../../javascript/reference/getutcmonth-method-date-javascript.md)   
 [setMonth – metoda (Date)](../../javascript/reference/setmonth-method-date-javascript.md)   
 [setUTCMonth – metoda (Date)](../../javascript/reference/setutcmonth-method-date-javascript.md)