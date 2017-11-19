---
title: "toTimeString – metoda (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: toTimeString
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: toTimeString method
ms.assetid: a4a8c0f2-55a9-4e84-94c3-f0a547fb04b5
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4d9af1f688fee0c066158d8504e00f22af9b3a21
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="totimestring-method-date-javascript"></a>toTimeString – metoda (Date) (JavaScript)
Vrátí dobu jako hodnotu řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
objDate. toTimeString( )  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `objDate` je odkaz `Date` objektu.  
  
 `toTimeString` Metoda vrací řetězcovou hodnotu obsahující čas v aktuální časové pásmo.  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu čas je nastavena na 2000 milisekund, po půlnoci 1. ledna 1970 UTC a je zapsán.  
  
```JavaScript  
var aDate = new Date();  
     aDate.setTime(2000);  
     document.write(aDate.toTimeString());  
  
// Output depends on the time in the current time zone.  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [toDateString – metoda (Date)](../../javascript/reference/todatestring-method-date-javascript.md)   
 [toLocaleTimeString – metoda (Date)](../../javascript/reference/tolocaletimestring-method-date-javascript.md)