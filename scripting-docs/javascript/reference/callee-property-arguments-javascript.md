---
title: "callee – vlastnost (arguments) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: callee
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: callee property
ms.assetid: ad9d4d21-73f0-44f6-8bec-502f3456cd23
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 33f1c2926d76c0a1f088c8f4222b6f24c004b73b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="callee-property-arguments-javascript"></a>callee – vlastnost (arguments) (JavaScript)
Vrátí `Function` objekt vykonáván, který je základní text zadaného `Function` objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
[function.]arguments.callee  
```  
  
## <a name="remarks"></a>Poznámky  
 Volitelné *funkce* argument je název aktuálně spuštěných `Function` objektu.  
  
 `callee` Vlastnost je členem skupiny **argumenty** objekt, který bude k dispozici pouze při provádění související funkce.  
  
 Počáteční hodnota `callee` vlastnost je `Function` objektu spouštěna. To umožňuje anonymní funkce jako rekurzivní.  
  
## <a name="example"></a>Příklad  
  
```JavaScript  
function factorial(n){  
  if (n <= 0)  
     return 1;  
  else  
     return n * arguments.callee(n - 1)  
}  
document.write(factorial(4));  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Platí pro**: [objekt arguments](../../javascript/reference/arguments-object-javascript.md)&#124; [Funkce objektu](../../javascript/reference/function-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [caller – vlastnost (Function)](../../javascript/reference/caller-property-function-javascript.md)