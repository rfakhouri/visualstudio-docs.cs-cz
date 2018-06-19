---
title: Operátor přiřazení posunutí doleva (&lt;&lt;=) (JavaScript) | Microsoft Docs
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
- <<=
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- <<= operator [JavaScript]
- left shift assignment operator (<<=) [JavaScript]
- left shift operators [JavaScript]
- assignment operators, JavaScript
ms.assetid: 9f30ff46-48cc-4931-b260-edef31ff0076
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bf00545947f6a84f99c519fcbed887b84c179fb5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790773"
---
# <a name="left-shift-assignment-operator-ltlt-javascript"></a>Operátor přiřazení posunutí doleva (&lt;&lt;=) (JavaScript)
Přesune zadaný počet bitů doleva a přiřadí výsledek, který má `result`. Službu bits uprázdnili operaci hodnotu 0.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result <<= expression  
```  
  
## <a name="parameters"></a>Parametry  
 `result`  
 Všechny proměnné.  
  
 `expression`  
 Počet bitů přesunout.  
  
## <a name="remarks"></a>Poznámky  
 Pomocí `<<=` operátor je stejné jako zadání`result = result << expression`  
  
 Následující příklad ukazuje způsob použití `<<=` operátor.  
  
```JavaScript  
// 14 is 00000000000000000000000000001110  
var temp = 14;  
temp <<= 2;   
document.write(temp);  
// 56 is 00000000000000000000000000111000  
Output: 56  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Bitový operátor posunu vlevo (<\<)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)   
 [Operátor bitového posunutí doprava (>>)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)   
 [Operátor posunutí doprava bez znaménka (>>>)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)   
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)