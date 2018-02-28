---
title: "getMilliseconds – metoda (Date) (JavaScript) | Microsoft Docs"
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
- getMilliseconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- milliseconds
- getMilliseconds method
ms.assetid: 1b512146-1e8a-44a4-89da-6cc5338d15cb
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 33e5fc54dffbe06e47f0978e6cef94b1f650c90f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="getmilliseconds-method-date-javascript"></a>getMilliseconds – metoda (Date) (JavaScript)
Získá data, pomocí místního času milisekundách.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.getMilliseconds()   
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `dateObj` je odkaz `Date` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí počet milisekund data. Hodnota v rozsahu 0-999. Pokud datum má byl vytvořený bez zadání milisekundách, vrácená hodnota je 0.  
  
## <a name="remarks"></a>Poznámky  
 Počet milisekund, po světového koordinovaného času (UTC), použijte `getUTCMilliseconds` metoda.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak používat **getMilliseconds** metoda.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getMilliseconds());  
document.write("<br/>");  
  
date.setMilliseconds(5);  
document.write(date.getMilliseconds());  
// Output:   
// 0  
// 5  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getUTCMilliseconds – metoda (Date)](../../javascript/reference/getutcmilliseconds-method-date-javascript.md)   
 [setmilliseconds – metoda (Date)](../../javascript/reference/setmilliseconds-method-date-javascript.md)   
 [setUTCMilliseconds – metoda (Date)](../../javascript/reference/setutcmilliseconds-method-date-javascript.md)