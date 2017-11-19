---
title: "JOIN – metoda (pole) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: join
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Join method
- concatenating strings, join method
- arrays [Visual Studio], joining
ms.assetid: 20f8fde1-014b-488e-9008-464a86e6b21f
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4591b12b3556384fef3e367d20cf9545d2f3dedd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="join-method-array-javascript"></a>join – metoda (Pole) (JavaScript)
Přidá všechny elementy pole oddělené řetězce zadaného oddělovače.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
arrayObj.join([separator])   
```  
  
## <a name="parameters"></a>Parametry  
 `arrayObj`  
 Požadováno. `Array` Objektu.  
  
 `separator`  
 Volitelné. Řetězec, který slouží k oddělení jeden element pole z další v výsledná `String`. Pokud tento parametr vynechán, jsou elementy pole odděleny čárkami.  
  
## <a name="remarks"></a>Poznámky  
 Pokud je libovolný element pole **nedefinované** nebo `null`, je považován za prázdný řetězec.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **spojení** metoda.  
  
```JavaScript  
var a, b;  
a = new Array(0,1,2,3,4);  
b = a.join("-");  
document.write(b);  
  
// Output:  
// 0-1-2-3-4  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [String – objekt](../../javascript/reference/string-object-javascript.md)