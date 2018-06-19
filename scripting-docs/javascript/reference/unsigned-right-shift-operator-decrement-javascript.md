---
title: Operátor posunutí doprava bez znaménka (&gt;&gt;&gt;) (JavaScript) | Microsoft Docs
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
- '>>>'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- unsigned right shift operator (>>>)
- '>>> operator'
ms.assetid: df48bdfc-8741-46ab-b681-449da57ac95c
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: efb873bedc0a64089c7ec892d6378b4869c0ca21
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792015"
---
# <a name="unsigned-right-shift-operator-gtgtgt-javascript"></a>Operátor posunutí doprava bez znaménka (&gt;&gt;&gt;) (JavaScript)
Pravé posune bitů výrazu, bez zachování přihlášení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result = expression1 >>> expression2  
```  
  
## <a name="parameters"></a>Parametry  
 *výsledek*  
 Všechny proměnné.  
  
 *Expression1*  
 Jakýkoli výraz.  
  
 *Výraz2*  
 Jakýkoli výraz.  
  
## <a name="remarks"></a>Poznámky  
 **>>>**  Operátor posune bitů z *expression1* právo podle počtu bitů zadaný v *Výraz2*. Nul se vyplní od levého okraje. Číslic přesunout mimo vpravo se zahodí. Příklad:  
  
```JavaScript  
var temp  
temp = -14 >>> 2  
```  
  
 Proměnná *temp* má počáteční hodnotu-14 (11111111 11111111 11111111 11110010 ve dvou na binární doplňku). Pokud je posunuté správných bitů dva, je hodnota 1073741820 (00111111 11111111 11111111 11111100 v binárním).  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Operátor přiřazení posunutí doprava bez znaménka (>>> =)](../../javascript/reference/unsigned-right-shift-assignment-operator-decrement-equal-javascript.md)   
 [Bitový operátor posunu vlevo (<\<)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)   
 [Operátor bitového posunutí doprava (>>)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)   
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)