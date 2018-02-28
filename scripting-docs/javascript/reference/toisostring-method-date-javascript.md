---
title: "toisostring – metoda (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toISOString method [JavaScript]
ms.assetid: 58577d8f-3ae8-4887-8687-26233ea79ff6
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 31559e1bc44849573ec7dc903411ce98b0a4440d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="toisostring-method-date-javascript"></a>toISOString – metoda (Date) (JavaScript)
Vrátí data jako hodnotu řetězce ve formátu ISO.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
  
objDate.toISOString()  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Řetězcová reprezentace datum v mezinárodní organizace pro normalizaci (ISO) formát.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud `objDate` neobsahuje platné datum `RangeError` je vyvolána výjimka.  
  
## <a name="remarks"></a>Poznámky  
 Není ve formátu ISO zjednodušení formátu ISO 8601. Další informace najdete v tématu [řetězců data a času](../../javascript/date-and-time-strings-javascript.md).  
  
 Časové pásmo je vždy UTC, označený jako přípona Z ve výstupu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `toISOString` metoda.  
  
```JavaScript  
var dt = new Date("30 July 2010 15:05 UTC");  
document.write(dt.toISOString());  
document.write("<br />");  
document.write(dt.toUTCString());  
  
// Output:  
//  2010-07-30T15:05:00.000Z  
//  Fri, 30 Jul 2010 15:05:00 UTC  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Date – objekt](../../javascript/reference/date-object-javascript.md)   
 [Řetězce data a času](../../javascript/date-and-time-strings-javascript.md)