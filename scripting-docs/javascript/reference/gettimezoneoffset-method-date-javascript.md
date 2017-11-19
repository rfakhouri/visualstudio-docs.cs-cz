---
title: "getTimezoneOffset – metoda (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getTimeZoneOffset
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- getTimezoneOffset method
- time zones [Visual Studio]
ms.assetid: 58ee22b0-4688-45bd-a337-cc23119b09ce
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e49a3c8b7060e6097300f8aaf99b2ef869833018
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="gettimezoneoffset-method-date-javascript"></a>getTimezoneOffset – metoda (Date) (JavaScript)
Získá rozdíl v minutách mezi čas v místním počítači a světového koordinovaného času (UTC).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.getTimezoneOffset()   
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `dateObj` je odkaz `Date` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí počet minut mezi čas v počítači, aktuální (klientský počítač nebo, pokud tato metoda je volána ze serveru skriptu, počítač serveru) a UTC. Jedná se kladné, pokud aktuální počítač místní čas je za čas UTC (například tichomořského letního času) a záporná, pokud je aktuální počítač místního času před časem UTC (například Japonsko). Pokud je server v New Yorku kontaktovat klientem v Los Angeles na 1. prosince `getTimezoneOffset` vrátí 480, je-li provést u klienta nebo 300-li provedeno na serveru.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `getTimezoneOffset` metoda.  
  
```JavaScript  
var date =  new Date();  
var minutes = date.getTimezoneOffset();  
  
if (minutes < 0)  
    document.write(minutes / 60 + " hours after UTC");  
else  
    document.write(minutes / 60 + " hours before UTC");  
  
// Output (for example, where local time is PST):   
7 hours before UTC  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getTime – metoda (Date)](../../javascript/reference/gettime-method-date-javascript.md)