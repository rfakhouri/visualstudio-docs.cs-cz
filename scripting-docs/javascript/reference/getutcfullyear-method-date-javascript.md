---
title: "getUTCFullYear – metoda (Date) (JavaScript) | Microsoft Docs"
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
- getUTCFullYear
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- getUTCFullYear method
- Date object
- UTCFullYear method
- dates, UTC
- UTC dates, returning
- Full Year method
- UTC dates, getting
ms.assetid: f11e5363-ef8a-48dd-9d56-4ee7290c7c48
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c8268631a96eed1f61ef4ba908b78680c8522096
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="getutcfullyear-method-date-javascript"></a>getUTCFullYear – metoda (Date) (JavaScript)
Získá roku pomocí světového koordinovaného času (UTC).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.getUTCFullYear()   
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `dateObj` je odkaz `Date` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí rok jako čtyřmístné číslo. Let zadaný jako dvě číslice v `Date` konstruktor nebo v `setFullYear` se předpokládá, že dvacátého století, takže zadané "5/14/12", `getUTCFullYear` vrátí "1912".  
  
## <a name="remarks"></a>Poznámky  
 V roce pomocí místního času, použijte `getFullYear` metoda.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje způsob použití `getUTCFullYear` metoda.  
  
```JavaScript  
var date = new Date("1/9/36");  
document.write(date.getUTCFullYear());  
  
// Output: 1936  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getFullYear – metoda (Date)](../../javascript/reference/getfullyear-method-date-javascript.md)   
 [setFullYear – metoda (Date)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setUTCFullYear – metoda (Date)](../../javascript/reference/setutcfullyear-method-date-javascript.md)