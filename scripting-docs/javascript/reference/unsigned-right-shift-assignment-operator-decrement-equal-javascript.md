---
title: Operátor přiřazení posunutí doprava bez znaménka (&gt;&gt;&gt;=) (JavaScript) | Microsoft Docs
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
- '>>>='
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '>>>= operator'
- unsigned right shift assignment operator (>>>=)
- assignment operators, JavaScript
ms.assetid: f67c3737-7d39-41ae-9c11-8b16d38f6179
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1272cbb58645df605743c6790642cd0e295442aa
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791937"
---
# <a name="unsigned-right-shift-assignment-operator-gtgtgt-javascript"></a>Operátor přiřazení posunutí doprava bez znaménka (&gt;&gt;&gt;=) (JavaScript)
Práva posune hodnotu proměnné podle počtu bitů zadaný v poli hodnota výrazu, bez zachování přihlášení a přiřadí výsledek proměnné.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result >>>= expression  
```  
  
## <a name="parameters"></a>Parametry  
 *výsledek*  
 Všechny proměnné.  
  
 *výraz*  
 Jakýkoli výraz.  
  
## <a name="remarks"></a>Poznámky  
 Pomocí >>> = operátor je přesně stejný jako následujícím způsobem:  
  
```JavaScript  
result = result >>> expression  
```  
  
 **>>>=**  Operátor posune bitů z *výsledek* právo podle počtu bitů zadaný v *výraz*. Nul se vyplní od levého okraje. Číslic přesunout mimo vpravo se zahodí. Příklad:  
  
```JavaScript  
var temp  
temp = -14  
temp >>>= 2  
```  
  
 Proměnná *temp* má počáteční hodnotu-14 (11111111 11111111 11111111 11110010 ve dvou na binární doplňku). Když zapuštěno správných bitů dva, je hodnota 1073741820 (00111111 11111111 11111111 11111100 v binárním).  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Operátor posunutí doprava bez znaménka (>>>)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)   
 [Bitový operátor posunu vlevo (<\<)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)   
 [Operátor bitového posunutí doprava (>>)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)   
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)