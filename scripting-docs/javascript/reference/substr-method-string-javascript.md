---
title: substr – metoda (String) (JavaScript) | Microsoft Docs
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
- substr
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- substr method
ms.assetid: f12541c1-2623-482e-941d-2e22bc3c4a4a
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6b002bfefbeb81c534c882fa4a4720c93ccca185
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791517"
---
# <a name="substr-method-string-javascript"></a>substr – metoda (String) (JavaScript)
Získá dílčí řetězec začínající na zadaném umístění a s určenou délku.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
stringvar.substr(start [, length ])   
```  
  
## <a name="parameters"></a>Parametry  
 `stringvar`  
 Požadováno. Řetězcový literál nebo `String` objekt ze kterého je dílčí řetězec extrahován.  
  
 `start`  
 Požadováno. Počáteční pozice požadované dílčí řetězec. Index prvního znaku v řetězci je nula.  
  
 `length`  
 Volitelné. Počet znaků, které chcete zahrnout do vrácený dílčí řetězec.  
  
## <a name="remarks"></a>Poznámky  
 Pokud `length` je nula nebo záporná, je vrácen prázdný řetězec. Pokud není zadaný, dílčí řetězec pokračuje na konec `stringvar`.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `substr` metoda.  
  
```JavaScript  
var s = "The quick brown fox jumps over the lazy dog.";  
var ss = s.substr(10, 5);    
document.write("[" + ss + "] <br>");  
  
ss = s.substr(10);  
document.write("[" + ss + "] <br>");  
  
ss = s.substr(10, -5);  
document.write("[" + ss + "] <br>");  
  
// Output:  
// [brown]   
// [brown fox jumps over the lazy dog.]   
// []  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [řetězce objektu](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [substring – metoda (String)](../../javascript/reference/substring-method-string-javascript.md)