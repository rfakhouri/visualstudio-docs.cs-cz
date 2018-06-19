---
title: getTime – metoda (Date) (JavaScript) | Microsoft Docs
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
- getTime
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- GetTime method
- time method
ms.assetid: f0da1d4e-337c-497d-9205-093defbc6d3d
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a31e542445e89a0e2f3364d36ae44f8d2d4cf9bb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790506"
---
# <a name="gettime-method-date-javascript"></a>getTime – metoda (Date) (JavaScript)
Získá hodnotu času v milisekundách.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.getTime()   
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `dateObj` je odkaz `Date` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí počet milisekund, po půlnoc, 1. ledna 1970 až hodnotu času v `Date` objektu. Rozsah kalendářních dat je přibližně 285,616 let z obou stranách půlnoc, 1. ledna 1970. Záporná čísla znamenat data před pod hodnotou 1970.  
  
## <a name="remarks"></a>Poznámky  
 Při provádění více výpočty datum a čas, můžete definovat proměnné rovná počet milisekund, po v den, hodinu nebo minutu. Příklad:  
  
```JavaScript  
var minute = 1000 * 60;  
var hour = minute * 60;  
var day = hour * 24;  
```  
  
 V tématu [výpočet dat a časů (JavaScript)](../../javascript/calculating-dates-and-times-javascript.md) Další informace o tom, jak používat `getTime` metoda.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `getTime` metoda.  
  
```JavaScript  
var minute = 1000 * 60;  
var hour = minute * 60;  
var day = hour * 24;  
  
date = new Date("1/1/2001");  
var time = date.getTime();  
  
document.write(Math.round(time / day) + " days from 1/1/1970 to 1/1/2001");  
  
// Output: 11323 days from 1/1/1970 to 1/1/2001  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [setTime – metoda (Date)](../../javascript/reference/settime-method-date-javascript.md)