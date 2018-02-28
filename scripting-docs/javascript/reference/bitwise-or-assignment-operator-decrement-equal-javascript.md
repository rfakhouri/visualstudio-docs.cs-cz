---
title: "Bitový operátor přiřazení OR (| =) (JavaScript) | Microsoft Docs"
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
- '|='
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- assignment operators, bitwise [JavaScript]
- '|= operator'
- bitwise operators, OR operator
- OR operator
ms.assetid: 9b424ff6-4442-4621-b3b6-83e7fd1e5cd5
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8ce9cadcf07906c9eba6749706620ae6293c2682
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-or-assignment-operator--javascript"></a>Operátor přiřazení bitové operace OR (|=) (JavaScript)
Bitový operátor OR provádí hodnota proměnné a hodnotu výrazu a přiřadí výsledek proměnné.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result |= expression  
```  
  
## <a name="parameters"></a>Parametry  
 *výsledek*  
 Všechny proměnné.  
  
 *výraz*  
 Jakýkoli výraz.  
  
## <a name="remarks"></a>Poznámky  
 Použití tohoto operátoru je přesně stejné jako zadání:  
  
```JavaScript  
result = result | expression  
```  
  
 **&#124; =** operátor vypadá na binární reprezentace hodnoty *výsledek* a *výraz* a nemá bitové operace OR na ně. Výsledek této operace se chová takto:  
  
```JavaScript  
0101    (result)  
1100    (expression)  
----  
1101    (output)  
```  
  
 Buď kdykoli z výrazů má v číslice 1, výsledek obsahuje v této číslice 1. Výsledek, jinak hodnota obsahuje 0 v této číslice.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Bitový operátor OR – operátor (&#124;)](../../javascript/reference/bitwise-or-operator-decrement-javascript.md)   
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)