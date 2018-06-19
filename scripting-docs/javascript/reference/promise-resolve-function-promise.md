---
title: Promise.Resolve – funkce (Promise) | Microsoft Docs
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
ms.assetid: 0fb6bff9-54ab-41be-97d7-04f7e6fe9cff
caps.latest.revision: 6
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6d815c9c23da48c877f7f1d995df8991429375e1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791076"
---
# <a name="promiseresolve-function-promise"></a>Promise.resolve – funkce (Promise)
Vytvoří nový přeložit promise se výsledek rovná se jeho argumentem.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Promise.resolve(x)  
```  
  
#### <a name="parameters"></a>Parametry  
 `x`  
 Požadováno. Hodnota vrácená s dokončené promise.  
  
## <a name="remarks"></a>Poznámky  
 Splnění zpracování funkce `then` metoda se spustí, jakmile se vrátí objekt dokončené promise.  
  
## <a name="example"></a>Příklad  
  
```JavaScript  
var p = Promise.resolve('success');  
p.then(function(result) {  
    console.log(result);  
});  
  
// Output:  
// success  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Promise – objekt](../../javascript/reference/promise-object-javascript.md)