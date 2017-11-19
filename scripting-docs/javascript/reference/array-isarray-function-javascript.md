---
title: "Array.IsArray – funkce (JavaScript) | Microsoft Docs"
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
helpviewer_keywords:
- isArray function [JavaScript]
- Array.isArray function [JavaScript]
ms.assetid: 58f7d2e0-d310-4292-b9bc-37a73c585780
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c31bdfe022cd41648117fc80c8df257e48e592ae
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="arrayisarray-function-javascript"></a>Array.isArray – funkce (JavaScript)
Určuje, zda je objekt pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Array.isArray(object)   
```  
  
#### <a name="parameters"></a>Parametry  
 `object`  
 Požadováno. Objekt, který se má ověřit  
  
## <a name="return-value"></a>Návratová hodnota  
 `true`Pokud `object` je pole, jinak hodnota `false`. Pokud `object` argument není objekt, `false` je vrácen.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `Array.isArray` funkce.  
  
```JavaScript  
var ar = [];  
var result = Array.isArray(ar);  
// Output: true  
  
var ar = new Array();  
var result = Array.isArray(ar);  
// Output: true  
  
var ar = [1, 2, 3];  
var result = Array.isArray(ar);  
// Output: true  
  
var result = Array.isArray("an array");  
document.write(result);  
// Output: false  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Array – objekt](../../javascript/reference/array-object-javascript.md)   
 [Použití polí](../../javascript/advanced/using-arrays-javascript.md)   
 [typeof – operátor](../../javascript/reference/typeof-operator-decrementjavascript.md)