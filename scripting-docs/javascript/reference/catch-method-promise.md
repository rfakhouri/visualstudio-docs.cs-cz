---
title: "catch – metoda (Promise) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 55266f6a-db4d-4de8-857a-8bc7d35ed4b8
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 307e5b2a501b038542a602df4538523a3fc6eccd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="catch-method-promise"></a>catch – metoda (Promise)
Umožňuje zadat pracovní provést pro zamítnutí příslib.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
promise.catch(onRejected)  
```  
  
#### <a name="parameters"></a>Parametry  
 `promise`  
 Požadováno. Promise objekt.  
  
 `onRejected`  
 Požadováno. Chyba obslužné rutiny spustit, když příslib byl odmítnut.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
 V následujícím příkladu kódu vrátí první volání časový limit po 5000ms. V tento kód byl odmítnut potenciálu a spustí chyba obslužné rutiny.  
  
```JavaScript  
function timeout(duration) {  
    return new Promise(function(resolve, reject) {  
        setTimeout(reject, duration);  
    });  
}  
  
var p = timeout(5000).then(() => {  
    console.log("done!");  
}).catch(err => {  
    console.log("error!");  
})  
  
// Output (after five seconds):  
// error!  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]