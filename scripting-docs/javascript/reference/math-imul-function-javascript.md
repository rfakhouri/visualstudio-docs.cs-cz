---
title: "Math.imul – funkce (JavaScript) | Microsoft Docs"
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
ms.assetid: dce5e11c-36b9-4c39-84d3-6cd494dd1cbf
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 57820d0926d574c75924f4eef6265ef7fa0766da
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="mathimul-function-javascript"></a>Math.imul – funkce (JavaScript)
Vrátí součin dvou čísel, které jsou považovány za 32bitová podepsaná celá čísla.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Math.imul(x, y);  
```  
  
#### <a name="parameters"></a>Parametry  
 `x`  
 Požadováno. První číslo.  
  
 `y`  
 Požadováno. Druhé číslo.  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce slouží k kompilátory jako Emscripten a Mandreel, které neimplementují celé číslo násobení stejným způsobem jako JavaScript.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak mají vynásobit čísla pomocí `Math.imul`.  
  
```JavaScript  
var result1 = Math.imul(2, 5);  
// result1 == 10  
  
var result2 = Math.imul(Math.pow(2, 32) - 1, Math.pow(2, 32) - 2);  
// result2 == 2   
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]