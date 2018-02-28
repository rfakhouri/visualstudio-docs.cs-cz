---
title: "Operátor přiřazení bitové operace AND (&amp;=) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- '&='
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '&= operator'
- assignment operators, bitwise [JavaScript]
- AND operator
- bitwise operators, AND operator
ms.assetid: e7e2eabb-4fc1-4fdc-9dd8-1e6d715371fa
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dfd2a77e66296cafc6c8403570f0536e1333e081
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-and-assignment-operator-amp-javascript"></a>Operátor přiřazení bitové operace AND (&amp;=) (JavaScript)
Nastaví výsledek bitové operace AND na hodnotě proměnné a hodnotě výrazu. Proměnnou a výraz jsou považovány za 32bitová celá čísla.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result &= expression  
```  
  
## <a name="parameters"></a>Parametry  
 `result`  
 Všechny proměnné.  
  
 `expression`  
 Jakýkoli výraz.  
  
## <a name="remarks"></a>Poznámky  
 Použití tohoto operátoru je stejné jako zadání:  
  
```JavaScript  
result = result & expression  
```  
  
 [Bitové a – operátor (&)](../../javascript/reference/bitwise-and-operator-decrement-javascript.md) vypadá na binární reprezentace hodnoty `result` a `expression` a nemá bitové operace AND na ně. Výstup této operace se chová takto:  
  
```JavaScript  
// 9 is 00000000000000000000000000001001  
var expr1 = 9;  
  
// 5 is 00000000000000000000000000000101  
var expr2 = 5;  
  
// 1 is 00000000000000000000000000000001  
expr1 &= expr2;  
  
document.write(expr1);  
```  
  
 Vždy, když oba výrazy mít 1 v číslici, výsledek obsahuje 1 v tomto číslice. Výsledek, jinak hodnota obsahuje 0 v této číslice.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Bitový operátor AND (&)](../../javascript/reference/bitwise-and-operator-decrement-javascript.md)   
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)