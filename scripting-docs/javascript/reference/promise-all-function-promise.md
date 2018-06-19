---
title: Promise.all – funkce (Promise) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 02a7b90c-96f6-4484-9466-d261efa1b494
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 997a419a990b407ae018f7da39fd75673ea28b6d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791481"
---
# <a name="promiseall-function-promise"></a>Promise.all – funkce (Promise)
Spojí dva nebo více lišící a vrátí pouze v případě, že všechny zadané lišící dokončíte nebo bylo odmítnuto.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Promise.all(func1, func2 [,funcN])  
```  
  
#### <a name="parameters"></a>Parametry  
 `func1`  
 Požadováno. Funkce, která vrátí příslib.  
  
 `func2`  
 Požadováno. Funkce, která vrátí příslib.  
  
 `funcN`  
 Volitelné. Jeden nebo více funkce, které vrací příslib.  
  
## <a name="remarks"></a>Poznámky  
 Výsledek vrácený je pole hodnot vrácených dokončené lišící. Pokud jeden z připojeného k lišící se odmítne, `Promise.all` okamžitě vrátí důvod odmítnutých promise (jiných vrátí hodnoty ztraceny).  
  
## <a name="example"></a>Příklad  
 V tento kód vrátí první volání časový limit po 5000ms. Dokončení volání obslužné rutiny `Promise.all`, která vrací jenom v případě, že jsou obě volání do vypršení časového limitu byla dokončena nebo odmítl.  
  
```JavaScript  
function timeout(duration) {  
    return new Promise(function(resolve, reject) {  
        setTimeout(resolve, duration);  
    });  
}  
  
var p = timeout(5000).then(() => {  
    return Promise.all([timeout(100), timeout(200)]);  
})  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Promise – objekt](../../javascript/reference/promise-object-javascript.md)