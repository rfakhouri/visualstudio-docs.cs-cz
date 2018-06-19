---
title: Object.Assign – funkce (Object) (JavaScript) | Microsoft Docs
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
ms.assetid: 2dd6b312-dcd3-414e-8d53-088c6341c46d
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c156369299e58eac556d43a87476de2ce09173e1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791154"
---
# <a name="objectassign-function-object-javascript"></a>Object.assign – funkce (Object) (JavaScript)
Zkopíruje hodnoty ze jeden nebo více objektů zdrojového na cílový objekt.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Object.assign(target, ...sources );  
```  
  
#### <a name="parameters"></a>Parametry  
 `target`  
 Požadováno. Objekt, ke kterému se zkopírují výčtové vlastnosti.  
  
 `...sources`  
 Požadováno. Jeden nebo více objektů, ze kterých se zkopírují výčtové vlastnosti.  
  
## <a name="exceptions"></a>Výjimky  
 Tato funkce vyvolá `TypeError` Pokud dojde k chybě přiřazení, která ukončí operaci kopírování. A `TypeError` bude vyvolána, pokud vlastnost target není zapisovatelná.  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce vrátí cílový objekt. Pouze *vyčíslitelná vlastní* vlastnosti jsou zkopírovány ze zdrojového objektu na objekt cíle. Tato funkce slouží k sloučit nebo klonovat objekty.  
  
 `null`nebo `undefined` zdroje jsou zpracovány jako objekty prázdná a přispívat nic na objekt cíle.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak sloučení objekt pomocí `Object.assign`.  
  
```JavaScript  
var first = { name: "Bob" };  
var last = { lastName: "Smith" };  
  
var person = Object.assign(first, last);  
console.log(person);  
  
// Output:  
// { name: "Bob", lastName: "Smith" }   
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak klonovat objekt pomocí `Object.assign`.  
  
```JavaScript  
var obj = { person: "Bob Smith"};  
var clone = Object.assign({}, obj);  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]