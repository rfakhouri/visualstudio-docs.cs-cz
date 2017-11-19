---
title: "toGMTString – metoda (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: toGMTString
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: toGMTString method
ms.assetid: 9dc1e722-5722-4b8c-a213-a2650f55f207
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cef8a61e04fbb5ada6e03fa946f434327422d9d7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="togmtstring-method-date-javascript"></a>toGMTString – metoda (Date) (JavaScript)
Vrátí datum převedeno na řetězec pomocí greenwichský znamenat Time(GMT).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.toGMTString()   
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `dateObj` odkaz je žádné `Date` objektu.  
  
 `toGMTString` Metoda je zastaralá a stanoví zpětné kompatibility jenom. Je doporučeno používat `toUTCString` metoda místo.  
  
 `toGMTString` Metoda vrátí `String` objekt, který obsahuje datum formátován pomocí konvencí GMT. Formát návratovou hodnotu vypadá takto: "05 ledna 1996 00:00:00 GMT."  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [toUTCString – metoda (Date)](../../javascript/reference/toutcstring-method-date-javascript.md)