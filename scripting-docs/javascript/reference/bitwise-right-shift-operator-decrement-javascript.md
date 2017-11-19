---
title: "Operátor bitového posunutí doprava (&gt;&gt;) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '>>'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '>> operator'
- '>> operator, about >> operator'
- '>> operator, bitsets'
- bitwise operators, right shift operator
ms.assetid: 89dc57e0-0b0d-49a4-a8ed-56d8bb20f3e3
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 70db0c176b475886a26cfe4c06f7f2f0c9d4fc2a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-right-shift-operator-gtgt-javascript"></a>Operátor bitového posunutí doprava (&gt;&gt;) (JavaScript)
Pravé posune bitů výrazu, zachování přihlášení.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result = expression1 >> expression2  
```  
  
## <a name="parameters"></a>Parametry  
 *výsledek*  
 Všechny proměnné.  
  
 *Expression1*  
 Jakýkoli výraz.  
  
 *Výraz2*  
 Jakýkoli výraz.  
  
## <a name="remarks"></a>Poznámky  
 >> Operátor posune bitů z *expression1* právo podle počtu bitů zadaný v *Výraz2*. Přihlašovací bit z *expression1* se používá k vyplnění číslic od levého okraje. Číslic přesunout mimo vpravo se zahodí. Po vyhodnocení následující kód například *temp* má hodnotu -4:-14 (11110010 ve dvou na doplňku binární) zapuštěno správných bitů dva rovná -4 (11111100 ve dvou na doplňku binární).  
  
```JavaScript  
var temp  
temp = -14 >> 2  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Bitový operátor posunu vlevo (<\<)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)   
 [Operátor přiřazení posunutí doprava (>> =)](../../javascript/reference/right-shift-assignment-operator-decrement-equal-javascript.md)   
 [Operátor posunutí doprava bez znaménka (>>>)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)   
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)