---
title: "setMonth – metoda (Date) (JavaScript) | Microsoft Docs"
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
- setMonth
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Month method
- setMonth method
ms.assetid: 4f5be295-d536-46c0-b3a4-ad06457efe82
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0f2672abebd327af8b0da58d46ebc183b8159711
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="setmonth-method-date-javascript"></a>setMonth – metoda (Date) (JavaScript)
Nastaví hodnotu měsíce v `Date` pomocí místního času.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj. setMonth(numMonth[, dateVal])   
```  
  
## <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. Všechny `Date` objektu.  
  
 `numMonth`  
 Požadováno. Číselná hodnota rovna v měsíci. Hodnota pro leden je 0 a ostatní měsíc hodnoty podle za sebou.  
  
 `dateVal`  
 Volitelné. Číselná hodnota představující den v měsíci. Pokud je tato hodnota není zadaný, hodnota z volání `getDate` metoda se používá.  
  
## <a name="remarks"></a>Poznámky  
 Chcete-li nastavena hodnota měsíce pomocí světového koordinovaného času (UTC), použijte `setUTCMonth` metoda.  
  
 Pokud hodnota `numMonth` je větší než 11 (leden je měsíc 0) nebo záporné číslo, je odpovídajícím způsobem upravit uložené roku. Například, pokud uložená data "5 ledna 1996" a **setMonth(14)** je volána, data se změní na "5 března 1997."  
  
 **SetFullYear** metoda slouží k nastavení rok, měsíc a den v měsíci.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `setMonth` metoda.  
  
```JavaScript  
date = new Date('1/1/1990');  
date.setMonth(14);  
document.write(date);  
  
// Output: Fri Mar 1 00:00:00 PST 1991  
// Note that the time zone corresponds to the time zone on the local computer.  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getMonth – metoda (Date)](../../javascript/reference/getmonth-method-date-javascript.md)   
 [getUTCMonth – metoda (Date)](../../javascript/reference/getutcmonth-method-date-javascript.md)   
 [setUTCMonth – metoda (Date)](../../javascript/reference/setutcmonth-method-date-javascript.md)