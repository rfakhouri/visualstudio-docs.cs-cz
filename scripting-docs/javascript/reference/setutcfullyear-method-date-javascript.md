---
title: setUTCFullYear – metoda (Date) (JavaScript) | Microsoft Docs
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
- setUTCFullYear
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, UTC
- setUTCFullYear method
- UTC dates, setting
ms.assetid: e6c51b49-0149-4f9a-aa74-c73c0306f98e
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2dda8b75dd8bc8dac87ea383546f392b064c1d63
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791808"
---
# <a name="setutcfullyear-method-date-javascript"></a>setUTCFullYear – metoda (Date) (JavaScript)
Nastaví hodnotu roku v `Date` pomocí světového koordinovaného času (UTC).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.setUTCFullYear(numYear[, numMonth[, numDate]])   
```  
  
## <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. Všechny `Date` objektu.  
  
 `numYear`  
 Požadováno. Číselná hodnota rovna v roce.  
  
 `numMonth`  
 Volitelné. Číselná hodnota rovna v měsíci. Hodnota pro leden je 0 a ostatní měsíc hodnoty podle za sebou. Je nutné zadat Pokud *numDate* pochází.  
  
 *numDate*  
 Volitelné. Číselná hodnota rovna den v měsíci.  
  
## <a name="remarks"></a>Poznámky  
 Všechny **nastavit** hodnota vrácená z odpovídající pomocí metody trvá volitelné argumenty **získat** metody, pokud nezadáte za volitelným argumentem. Například pokud `numMonth` argument není zadán, [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] používá hodnotu vrácenou z `getUTCMonth` metoda.  
  
 Kromě toho, pokud je hodnota argumentu větší, její rozsah nebo záporné číslo, jiné uložené hodnoty jsou upraveny odpovídajícím způsobem.  
  
 Pokud chcete nastavit v roce pomocí místního času, použijte `setFullYear` metoda.  
  
 Řadu let v podporované `Date` objektu je přibližně 285,616 let z obou stranách pod hodnotou 1970.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `setUTCFullYear` metoda.  
  
```JavaScript  
var dtFirst = new Date();  
dtFirst.setUTCFullYear(2007);  
  
var dtSecond = new Date();  
// 10 is the value for November.   
dtSecond.setUTCFullYear(2008, 10, 3);   
  
document.write (dtFirst.toUTCString());  
document.write ("<br />");  
document.write (dtSecond.toUTCString());  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getFullYear – metoda (Date)](../../javascript/reference/getfullyear-method-date-javascript.md)   
 [getUTCFullYear – metoda (Date)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [setFullYear – metoda (Date)](../../javascript/reference/setfullyear-method-date-javascript.md)