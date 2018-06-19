---
title: getUTCSeconds – metoda (Date) (JavaScript) | Microsoft Docs
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
- getUTCSeconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- UTC times, returning
- seconds method
- getUTCSeconds method
ms.assetid: 2d8ea7dc-79f8-4a9b-b2ab-732db2bcd5fd
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4f398145f8e31ed633bf3215de7d5a5ef669b7ef
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790557"
---
# <a name="getutcseconds-method-date-javascript"></a>getUTCSeconds – metoda (Date) (JavaScript)
Získá počet sekund, který `Date` pomocí světového koordinovaného času (UTC).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.getUTCSeconds()   
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `dateObj` je odkaz `Date` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí celé číslo mezi 0 a 59. Čas je kratší než jedna sekunda do aktuální minuty, bude vrácena nula. Pokud `Date` objekt byl vytvořen bez zadání čas, ve výchozím nastavení čas UTC sekund hodnota je 0.  
  
## <a name="remarks"></a>Poznámky  
 Počet sekund v místním čase, použijte `getSeconds` metoda.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `getUTCSeconds` metoda.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date. getUTCSeconds());  
  
// Output: 0  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getSeconds – metoda (Date)](../../javascript/reference/getseconds-method-date-javascript.md)   
 [setSeconds – metoda (Date)](../../javascript/reference/setseconds-method-date-javascript.md)   
 [setUTCSeconds – metoda (Date)](../../javascript/reference/setutcseconds-method-date-javascript.md)