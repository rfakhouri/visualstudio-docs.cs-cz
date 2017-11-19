---
title: "getUTCMonth – metoda (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getUTCMonth
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, UTC
- UTC dates, returning
- Month method
- getUTCMonth method
ms.assetid: eabae139-4da0-4e4a-a4cb-608e6375fc9e
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 07e7ecdc9a9ee8a49c12fc65e4b2ba1056bd377c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="getutcmonth-method-date-javascript"></a>getUTCMonth – metoda (Date) (JavaScript)
Získá měsíc `Date` pomocí světového koordinovaného času (UTC).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.getUTCMonth()   
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `dateObj` je odkaz `Date` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí celé číslo mezi 0 (leden) a 11 (prosinec).  
  
## <a name="remarks"></a>Poznámky  
 V měsíci v místním čase, použijte **getMonth** metoda.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `getUTCMonth` metoda.  
  
```JavaScript  
var date = new Date("2/2/2002");  
document.write(date.getUTCMonth());  
  
// Output: 1  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getMonth – metoda (Date)](../../javascript/reference/getmonth-method-date-javascript.md)   
 [setMonth – metoda (Date)](../../javascript/reference/setmonth-method-date-javascript.md)   
 [setUTCMonth – metoda (Date)](../../javascript/reference/setutcmonth-method-date-javascript.md)