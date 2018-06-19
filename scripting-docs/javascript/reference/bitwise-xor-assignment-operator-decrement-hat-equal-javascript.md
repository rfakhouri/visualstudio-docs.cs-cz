---
title: Operátor přiřazení bitové operace XOR (^ =) (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- ^=
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- ^= operator, about ^= operator
- assignment operators, bitwise [JavaScript]
- bitwise operators, XOR operator
- XOR operator
- ^= operator
ms.assetid: a6ded216-27b6-4fc4-a51b-7d10cc6f820c
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 511ff5b3346bb2b04bf4c24cb3e0b715b2ccf4c5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789087"
---
# <a name="bitwise-xor-assignment-operator--javascript"></a>Operátor přiřazení bitové operace XOR (^=) (JavaScript)
Bitový exkluzivní OR provádí proměnné a výraz a přiřadí výsledek proměnné.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result ^= expression  
```  
  
## <a name="parameters"></a>Parametry  
 *výsledek*  
 Všechny proměnné.  
  
 *výraz*  
 Jakýkoli výraz.  
  
## <a name="remarks"></a>Poznámky  
 Pomocí  **^=**  operátor je přesně stejné jako zadání:  
  
```JavaScript  
result = result ^ expression  
```  
  
 **^=**  Operátor vypadá na binární reprezentace hodnoty dvou výrazů a nemá bitová operace exkluzivní nebo na nich. Výsledek této operace chová následovně:  
  
```JavaScript  
0101    (result)  
1100    (expression)  
----  
1001    (result)  
```  
  
 Pokud jeden a pouze jeden výraz 1 v číslice, výsledek obsahuje 1 v této číslice. Výsledek, jinak hodnota obsahuje 0 v této číslice.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Bitový operátor XOR (^)](../../javascript/reference/bitwise-xor-operator-decrement-hat-javascript.md)   
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)