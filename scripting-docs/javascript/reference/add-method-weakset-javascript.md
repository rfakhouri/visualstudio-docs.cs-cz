---
title: "add – metoda (WeakSet) (JavaScript) | Microsoft Docs"
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
ms.assetid: d35d0287-6b33-4720-b9d7-8954c428ce4e
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3ab486beaba4a26c73930b5ceaee927f73aa077a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="add-method-weakset-javascript"></a>add – metoda (WeakSet) (JavaScript)
Přidá nového elementu `WeakSet`.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
weaksetObj.add(obj)  
```  
  
#### <a name="parameters"></a>Parametry  
 `weaksetObj`  
 Požadováno. A `WeakSet` objektu.  
  
 `obj`  
 Požadováno. Nový element `WeakSet`.  
  
## <a name="remarks"></a>Poznámky  
 Nového elementu musí být objekt, nikoli libovolná hodnota a musí být jedinečný. Pokud přidáte jako element jedinečný `WeakSet`, nového elementu nepřidají do kolekce.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak přidat členy do sady a ověřte, zda byl přidán.  
  
```JavaScript  
var ws = new WeakSet();  
  
var str = new String("Thomas Jefferson");  
var num = new Number(1776);  
  
ws.add(str);  
ws.add(num);  
  
console.log(ws.has(str));  
console.log(ws.has(num));  
  
ws.delete(str);  
console.log(ws.has(str));  
  
// Output:  
// true  
// true  
// false  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]