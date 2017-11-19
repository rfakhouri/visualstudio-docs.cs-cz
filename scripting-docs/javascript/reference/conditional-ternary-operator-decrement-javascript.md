---
title: "Podmíněný (Ternární) operátor (?:) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '?:'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- conditional operators
- conditional (Ternary) operator
- ternary
ms.assetid: 7399ac32-9324-4a9a-ae76-be9c0f9df81c
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1dc34b5c633cfc02219cb01061e1aaa017e0f7f2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="conditional-ternary-operator--javascript"></a>Podmíněný (ternární) operátor (?:) (JavaScript)
Vrací jeden ze dvou výrazů v závislosti na podmínce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
test ? expression1 : expression2  
```  
  
## <a name="parameters"></a>Parametry  
 `test`  
 Libovolný výraz Boolean.  
  
 `expression1`  
 Pokud vrácený výraz `test` je `true`. Výrazem může být čárka.  
  
 `expression2`  
 Pokud vrácený výraz `test` je `false`. Více výrazů může být spojeno čárkou.  
  
## <a name="remarks"></a>Poznámky  
 `?:` Operátor lze použít jako zástupce pro `if...else` příkaz. Obvykle se používá jako součást rozsáhlejšího výrazu kde `if...else` příkaz by být nevhodných. Příklad:  
  
```JavaScript  
var now = new Date();  
var greeting = "Good" + ((now.getHours() > 17) ? " evening." : " day.");  
```  
  
 V příkladu se vytvoří řetězec obsahující "Good evening." Pokud je po 18: 00. Ekvivalentní kódu pomocí `if...else` příkaz vypadat takto:  
  
```JavaScript  
var now = new Date();  
var greeting = "Good";  
if (now.getHours() > 17)  
   greeting += " evening.";  
else  
   greeting += " day.";  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [If... else – příkaz](../../javascript/reference/if-dot-dot-dot-else-statement-javascript.md)   
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)   
 [Skript ostatními konfigurace pomůcky ukázkové aplikace](http://code.msdn.microsoft.com/Script-Junkie-Configuration-543ece24)