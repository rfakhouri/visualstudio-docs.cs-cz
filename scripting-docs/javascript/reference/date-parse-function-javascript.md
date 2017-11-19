---
title: "Date.Parse – funkce (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: parse
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- parse function [JavaScript]
- Date.parse function [JavaScript]
ms.assetid: ed737e50-6398-4462-8779-2af3c03f8325
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0a73fda66ef24df17a5213a182c04667fc4dfabf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="dateparse-function-javascript"></a>Date.parse – funkce (JavaScript)
Analyzuje řetězec obsahující data a vrátí počet milisekund, mezi které datum a půlnoc, 1. ledna 1970.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Date.parse(dateVal)   
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `dateVal` argument je řetězec obsahující datum nebo VT_DATE – hodnota načtena z objektu ActiveX nebo jiného objektu. Pro informace o datu řetězců, které `Date.parse` funkce lze analyzovat. v tématu [řetězců data a času](../../javascript/date-and-time-strings-javascript.md).  
  
 `Date.parse` Funkce vrátí celočíselnou hodnotu představující počet milisekund, po mezi půlnoc, 1. ledna 1970 a datum zadaný v `dateVal`.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `Date.parse` funkce.  
  
```JavaScript  
var dateString = "November 1, 1997 10:15 AM";  
var mSec = Date.parse(dateString);  
document.write(mSec);  
// Output: 878404500000  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad vrátí rozdíl mezi datem zadaný a 1/1/1970.  
  
```JavaScript  
var minMilli = 1000 * 60;  
var hrMilli = minMilli * 60;  
var dyMilli = hrMilli * 24;  
  
var testDate = new Date("June 1, 1990");  
var ms = Date.parse(testDate);  
var days = Math.round(ms / dyMilli);  
  
var dateStr = "";  
dateStr += "There are " + days + " days ";  
dateStr += "between 01/01/1970 and " + testDate;  
document.write(dateStr);  
  
// Output: There are 7456 days between 01/01/1970 and Fri Jun 1 00:00:00 PDT 1990  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [getDate – metoda (Date)](../../javascript/reference/getdate-method-date-javascript.md)