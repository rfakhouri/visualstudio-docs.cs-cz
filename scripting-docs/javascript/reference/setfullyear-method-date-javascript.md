---
title: "setFullYear – metoda (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: setFullYear
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Year method
- setFullYear method
- dates, setting
ms.assetid: 635e4f5a-0210-4c01-8152-b0da4146f6ff
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1e5e20a8486d1aefeab9b244c5f1e9d1b1e60c3f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="setfullyear-method-date-javascript"></a>setFullYear – metoda (Date) (JavaScript)
Nastaví rok `Date` pomocí místního času.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.setFullYear(numYear[, numMonth[, numDate]])   
```  
  
## <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. Všechny `Date` objektu.  
  
 `numYear`  
 Požadováno. Číselná hodnota v roce.  
  
 `numMonth`  
 Volitelné. Počítaný od nuly číselnou hodnotu pro daný měsíc (0 pro leden, 11 pro prosinec). Musí být zadán, pokud `numDate` je zadán.  
  
 `numDate`  
 Volitelné. Číselná hodnota rovna dne v měsíci.  
  
## <a name="remarks"></a>Poznámky  
 Všechny **nastavit** hodnota vrácená z odpovídající pomocí metody trvá volitelné argumenty **získat** metody, pokud nezadáte nepovinný argument. Například pokud `numMonth` argument je volitelný, ale není zadaný, [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] používá hodnotu vrácenou z **getMonth** metoda.  
  
 Kromě toho pokud hodnota argumentu je větší než jeho kalendáře rozsah nebo záporné, vrátí datum, nebo předchozí podle potřeby.  
  
 Pokud chcete nastavit v roce pomocí světového koordinovaného času (UTC), použijte `setUTCFullYear` metoda.  
  
 Řadu let podporované v objektu, datum je přibližně 285,616 let před a po pod hodnotou 1970.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `setFullYear` metoda:  
  
```JavaScript  
var date1 = new Date("1/1/2001");  
date1.setFullYear(2007);  
  
var date2 = new Date("1/1/2001");  
date2.setFullYear(2008, 10, 3);   
  
document.write (date1.toLocaleString());  
document.write ("<br />");  
document.write (date2.toLocaleString());  
  
// Output:  
// Monday, January 01, 2007 12:00:00 AM  
// Monday, November 03, 2008 12:00:00 AM  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getFullYear – metoda (Date)](../../javascript/reference/getfullyear-method-date-javascript.md)   
 [getUTCFullYear – metoda (Date)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [setUTCFullYear – metoda (Date)](../../javascript/reference/setutcfullyear-method-date-javascript.md)