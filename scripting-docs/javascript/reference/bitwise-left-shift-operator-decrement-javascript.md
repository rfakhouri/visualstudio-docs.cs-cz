---
title: "Bitový operátor posunu vlevo (&lt;&lt;) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: <<
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- << operator
- left shift operators
- << operator, about << operator
- bitwise operators, Left Shift operator
ms.assetid: 18148596-7b86-4add-aeef-106991c69435
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9d63fc50659695f518e581edbed67c009b36577f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-left-shift-operator-ltlt-javascript"></a>Bitový operátor posunu vlevo (&lt;&lt;) (JavaScript)
Levé posune bitů výrazu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result = expression1 << expression2  
```  
  
## <a name="parameters"></a>Parametry  
 *výsledek*  
 Všechny proměnné.  
  
 *Expression1*  
 Jakýkoli výraz.  
  
 *Výraz2*  
 Jakýkoli výraz.  
  
## <a name="remarks"></a>Poznámky  
 **<<**  Operátor posune bitů z *expression1* zbývající počet bitů, zadaný v *Výraz2*. Příklad:  
  
```JavaScript  
var temp  
temp = 14 << 2  
```  
  
 Proměnná *temp* má hodnotu, 56, protože 14 (00001110 v binárním) zapuštěno levé dva bity rovná 56 (00111000 v binárním).  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Operátor přiřazení posunutí doleva (<\<=)](../../javascript/reference/left-shift-assignment-operator-decrement-equal-javascript.md)   
 [Operátor bitového posunutí doprava (>>)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)   
 [Operátor posunutí doprava bez znaménka (>>>)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)   
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)