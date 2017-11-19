---
title: "Promise.race – funkce (Promise) | Microsoft Docs"
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
ms.assetid: 9236eced-d313-4d03-8c3e-d89d762b3084
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fedd512f4565009c8429b43b0d9d93de943d13fb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="promiserace-function-promise"></a>Promise.race – funkce (Promise)
Vytvoří nový promise, který bude vyřešit nebo zamítnout se stejnou hodnotou výsledek jako první promise vyřešit nebo zamítnout mezi předané argumenty.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Promise.race(iterable)  
```  
  
#### <a name="parameters"></a>Parametry  
 `iterable`  
 Požadováno. Jeden nebo více lišící.  
  
## <a name="remarks"></a>Poznámky  
 Pokud jeden z lišící v `iterable` je již ve stavu vyřešení nebo odmítnuté, `Promise.race` vrátí promise přeložit ani odmítnout, stejně jako s hodnotou výsledek stejná jako hodnota používá k vyřešení (nebo odmítnout) této promise. Pokud v, nabízí více `iterable` jsou již vyřešeny nebo zamítnutí, `Promise.race` vrátí příslib vyřešit stejným způsobem jako první promise vstupní. Pokud žádné promise iterable vyřeší nebo odmítne potenciálu vrácená z `Promise.race` také nemá vyřešit nebo zamítnout.  
  
## <a name="example"></a>Příklad  
  
```JavaScript  
var p1 = new Promise(function(resolve, reject) {  
    setTimeout(resolve, 0, 'success');  
});  
var p2 = new Promise(function(resolve, reject) { });  
var p2 = new Promise(function(resolve, reject) { });  
  
var race = Promise.race( [p1, p2, p3] );  
race.then(function(result) {  
    console.log(result);  
});  
  
// Output:  
// success  
  
var race = Promise.race( [Promise.reject('failure'),  
    Promise.resolve('success')] );  
race.catch(function(result) {  
    console.log(result);  
});  
  
// Output:  
// failure  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Promise – objekt](../../javascript/reference/promise-object-javascript.md)