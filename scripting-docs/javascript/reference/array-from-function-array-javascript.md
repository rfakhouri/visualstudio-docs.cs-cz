---
title: Array.from – funkce (Array) (JavaScript) | Microsoft Docs
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
ms.assetid: 1bf59a99-f860-4c4d-b4c6-d5f1f946a490
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a240cb439942bfeb6b4c9a1febb4d24cef1c5c18
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789042"
---
# <a name="arrayfrom-function-array-javascript"></a>Array.from – funkce (Array) (JavaScript)
Vrátí pole z objektu jako pole nebo iterable.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Array.from (arrayLike [ , mapfn [ , thisArg ] ] );  
```  
  
#### <a name="parameters"></a>Parametry  
 `arrayLike`  
 Požadováno. Objekt jako pole nebo objekt iterable.  
  
 `mapfn`  
 Volitelné. Mapování funkce, která se zavolat na každý prvek v `arrayLike`.  
  
 `thisArg`  
 Volitelné. Určuje, `this` objekt v mapování funkce.  
  
## <a name="remarks"></a>Poznámky  
 `arrayLike` Parametr musí být buď objekt s indexované elementy a `length` vlastnost nebo objekt iterable, například `Set` objektu.  
  
 Volitelné mapování funkce je volána na každý prvek v poli.  
  
## <a name="example"></a>Příklad  
 Následující příklad vrací pole z kolekce uzly elementu DOM.  
  
```JavaScript  
var elemArr = Array.from(document.querySelectorAll('*'));  
var elem = elemArr[0]; // elem contains a reference to the first DOM element  
  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad vrací pole znaků.  
  
```JavaScript  
var charArr = Array.from("abc");  
// charArr[0] == "a";  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad vrací pole objektů obsažených v kolekci.  
  
```JavaScript  
var setObj = new Set("a", "b", "c");  
var objArr = Array.from(setObj);  
// objArr[1] == "b";   
```  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití syntaxe šipku a mapování funkce ke změně hodnoty elementů.  
  
```JavaScript  
var arr = Array.from([1, 2, 3], x => x * 10);  
// arr[0] == 10;  
// arr[1] == 20;  
// arr[2] == 30;  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]