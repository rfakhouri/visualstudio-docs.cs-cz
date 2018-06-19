---
title: getFullYear – metoda (Date) (JavaScript) | Microsoft Docs
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
- getFullYear
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, returning year
- Date object
- getFullYear method
ms.assetid: f9ec1262-02e9-4791-90b5-48f33b1dc4bc
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 211d6c86435e39eb75b9b1ce3415738541ca07db
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790533"
---
# <a name="getfullyear-method-date-javascript"></a>getFullYear – metoda (Date) (JavaScript)
Získá v roce pomocí místního času.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
dateObj.getFullYear()   
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `dateObj` je odkaz `Date` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Rok jako čtyřmístné číslo. Například v roce 1976 se vrátí jako 1976. Let zadaný jako dvě číslice v `Date` konstruktor nebo v `setFullYear` se předpokládá, že dvacátého století, takže zadané "5/14/12", `getFullYear` vrátí "1912".  
  
## <a name="remarks"></a>Poznámky  
 V roce pomocí světového koordinovaného času (UTC), použijte `getUTCFullYear` metoda.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **getFullYear** metoda.  
  
```JavaScript  
var date = new Date("1/1/01");  
document.write(date.getFullYear());  
  
// Output: 1901  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [datum objektu](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [getUTCFullYear – metoda (Date)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [setFullYear – metoda (Date)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setUTCFullYear – metoda (Date)](../../javascript/reference/setutcfullyear-method-date-javascript.md)