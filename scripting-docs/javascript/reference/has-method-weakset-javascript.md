---
title: "has – metoda (WeakSet) (JavaScript) | Microsoft Docs"
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
ms.assetid: e24f0876-26bd-4007-b12a-360bb6fa0951
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0dbc7e17e3fd73730386293c5e3f894455e41a93
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="has-method-weakset-javascript"></a>has – metoda (WeakSet) (JavaScript)
Vrátí `true` Pokud `WeakSet` obsahuje zadaný element.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
setObj.has(obj)  
```  
  
#### <a name="parameters"></a>Parametry  
 `setObj`  
 Požadováno. A `WeakSet` objektu.  
  
 `obj`  
 Požadováno. Elementu, který chcete otestovat.  
  
## <a name="property-valuereturn-value"></a>Hodnota vlastnosti / návratová hodnota  
 `true`Pokud sada obsahuje zadaný element.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje, jak přidávat členy do `WeakSet` a potom zkontrolujte, zda sada obsahuje konkrétní člena.  
  
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