---
title: Bitový operátor AND (&amp;) (JavaScript) | Microsoft Docs
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
- '&'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- assignment operators, bitwise [JavaScript]
- '& operator, about & operator'
- AND operator
- '& operator'
- bitwise operators, AND operator
- '& operator, bitwise operators'
ms.assetid: a8c17a55-2599-4518-98d7-671699f4d5f3
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fa8b3eec0cbd7c172d08b16120fb54f3be3c6a48
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789177"
---
# <a name="bitwise-and-operator-amp-javascript"></a>Bitový operátor AND (&amp;) (JavaScript)
Provede bitové operace AND na dvou 32-bit výrazů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result = expression1 & expression2  
```  
  
## <a name="parameters"></a>Parametry  
 `result`  
 Výsledek operace.  
  
 `expression1`  
 Jakýkoli výraz.  
  
 `expression2`  
 Jakýkoli výraz.  
  
## <a name="remarks"></a>Poznámky  
 `&` Nemá bitové operace AND do jednotlivých bity dvou 32-bit výrazů. Pokud jsou obě bity 1, výsledkem je 1. Výsledek, jinak hodnota je 0.  
  
|Bit1|Bit2|Hodnota sloučeny pomocí operátoru and.|  
|----------|----------|-----------------|  
|0|0|0|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
  
 Následující příklady ukazují, jak používat `&` operátor.  
  
```JavaScript  
// 9 is 00000000000000000000000000001001  
var expr1 = 9;  
  
// 5 is 00000000000000000000000000000101  
var expr2 = 5;  
  
// 1 is 00000000000000000000000000000001  
var result = expr1 & expr2;  
  
document.write(result);  
// Output: 1  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Operátor přiřazení bitové operace AND (& =)](../../javascript/reference/bitwise-and-assignment-operator-decrement-equal-javascript.md)   
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)