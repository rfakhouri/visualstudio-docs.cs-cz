---
title: Array.of – funkce (Array) (JavaScript) | Microsoft Docs
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
ms.assetid: 2884dda3-65d1-4990-9afe-87865c2d4f7f
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 042315bbc3b956e92fff866f7d403b6f87726a74
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789066"
---
# <a name="arrayof-function-array-javascript"></a>Array.of – funkce (Array) (JavaScript)
Vrátí pole z předané argumenty.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Array.of(element0[, element1][, ...][,elementN]);  
```  
  
#### <a name="parameters"></a>Parametry  
 `element0,...,elementN`  
 Volitelné. Prvky, které mají být umístěny do pole. Tím se vytvoří pole s n + 1 elementy a délku n + 1.  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce je podobná volání `new Array(args)`, ale `Array.of` neobsahuje zvláštní chování, pokud je předaná jeden argument.  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří pole z předané čísla.  
  
```JavaScript  
var arr = Array.of(1, 2, 3);  
// arr[0] == 1   
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje rozdíl mezi použitím `Array.of` a `new Array`.  
  
```JavaScript  
var arr1 = Array.of(3);  
// arr1[0] == 3  
  
// With new Array, a single argument specifies  
// the length of the new array.  
var arr2 = new Array(3);  
// arr2[0] is undefined  
// arr2.length == 3  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]