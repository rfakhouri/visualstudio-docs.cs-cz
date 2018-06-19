---
title: getUTCMinutes – metoda (Date) (JavaScript) | Microsoft Docs
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
- getUTCMinutes
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- minutes
- UTC times, returning
- getUTCMinutes method
ms.assetid: b6d92543-b285-4e46-8f47-bba36e53fabd
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fe691d3b52d18340eeeff81a91c049a262277c54
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790551"
---
# <a name="getutcminutes-method-date-javascript"></a>getUTCMinutes – metoda (Date) (JavaScript)
Získá dobu, po které `Date` pomocí světového koordinovaného času (UTC).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.getUTCMinutes()   
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `dateObj` je odkaz `Date` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí celé číslo mezi 0 a 59. Čas je méně než minutu po hodině, bude vrácena nula. Pokud `Date` objekt byl vytvořen bez zadání čas, ve výchozím nastavení čas UTC minutu hodnota je 0. Ale v jiných časových pásmech se může lišit.  
  
## <a name="remarks"></a>Poznámky  
 Počet minut uložené pomocí místního času, použijte `getMinutes` metoda.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `getUTCMinutes` metoda.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getUTCMinutes());  
document.write("<br/>");  
  
date.setMinutes(5);  
document.write(date.getUTCMinutes());  
  
// Output:   
// 0  
// 5  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getMinutes – metoda (Date)](../../javascript/reference/getminutes-method-date-javascript.md)   
 [setMinutes – metoda (Date)](../../javascript/reference/setminutes-method-date-javascript.md)   
 [setUTCMinutes – metoda (Date)](../../javascript/reference/setutcminutes-method-date-javascript.md)