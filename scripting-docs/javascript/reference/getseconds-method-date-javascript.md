---
title: "getSeconds – metoda (Date) (JavaScript) | Microsoft Docs"
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
- getSeconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- seconds method
- GetSeconds method
ms.assetid: 97b10674-af0b-4681-a846-38f972196501
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 151d720b92fb9d7068c320983a25b965078f1b2e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="getseconds-method-date-javascript"></a>getSeconds – metoda (Date) (JavaScript)
Získá počet sekund, který `Date` objektu pomocí místního času.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.getSeconds()   
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `dateObj` je odkaz `Date` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí celé číslo mezi 0 a 59. Čas je kratší než jedna sekunda do aktuální minuty, bude vrácena nula. Pokud `Date` objekt byl vytvořen bez zadání čas, ve výchozím nastavení sekund hodnota je 0.  
  
## <a name="remarks"></a>Poznámky  
 Počet sekund hodnotu pomocí světového koordinovaného času (UTC), použijte `getUTCSeconds` metoda.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `getSeconds` metoda.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getSeconds());  
document.write("<br/>");  
  
date.setSeconds(5);  
document.write(date.getSeconds());  
  
// Output:  
// 0  
// 5  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getUTCSeconds – metoda (Date)](../../javascript/reference/getutcseconds-method-date-javascript.md)   
 [setSeconds – metoda (Date)](../../javascript/reference/setseconds-method-date-javascript.md)   
 [setUTCSeconds – metoda (Date)](../../javascript/reference/setutcseconds-method-date-javascript.md)