---
title: setTime – metoda (Date) (JavaScript) | Microsoft Docs
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
- setTime
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- SetTime method
- time method
ms.assetid: 86584748-7219-495b-bf56-e27f5782778c
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e66b1fbf5d668330eb727e8bfc50ee9d11a28be3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791757"
---
# <a name="settime-method-date-javascript"></a>setTime – metoda (Date) (JavaScript)
Nastaví hodnotu data a času v `Date` objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.setTime(milliseconds)   
```  
  
## <a name="parameters"></a>Parametry  
 `dateObj`  
 Požadováno. Všechny `Date` objektu.  
  
 *počet milisekund*  
 Požadováno. Číselná hodnota představující počet milisekund, po uplynulé od půlnoci 1. ledna 1970 GMT.  
  
## <a name="remarks"></a>Poznámky  
 Pokud *milisekundách* je záporná, znamená to datum bylo pod hodnotou 1970. Rozsah kalendářních dat k dispozici je přibližně 285,616 let z obou stranách pod hodnotou 1970.  
  
 Nastavení data a času s `setTime` metoda je nezávislá na časové pásmo.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `setTime` metoda.  
  
```JavaScript  
function SetTimeTest(newtime){  
   var d, s;                  //Declare variables.  
   d = new Date();            //Create Date object.  
   d.setTime(newtime);        //Set time.  
   s = "Current setting is ";  
   s += d.toUTCString();  
   return(s);                 //Return new setting.  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getTime – metoda (Date)](../../javascript/reference/gettime-method-date-javascript.md)