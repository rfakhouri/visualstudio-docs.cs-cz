---
title: "Operátor přiřazení posunutí doprava (&gt;&gt;=) (JavaScript) | Microsoft Docs"
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
- '>>='
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '>>= operator [JavaScript]'
- right shift operators [JavaScript]
- assignment operators, JavaScript
ms.assetid: 8c1f7f90-e3ac-42ee-94f2-5ccc47d7aef6
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cb93d146ad00bd19c09fb4cfca3af776a11f245d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="right-shift-assignment-operator-gtgt-javascript"></a>Operátor přiřazení posunutí doprava (&gt;&gt;=) (JavaScript)
Práva posune hodnotu proměnné podle počtu bitů zadaný v poli hodnota výrazu, zachování přihlášení a přiřadí výsledek proměnné.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result >>= expression  
```  
  
## <a name="parameters"></a>Parametry  
 *výsledek*  
 Všechny proměnné.  
  
 *výraz*  
 Jakýkoli výraz.  
  
## <a name="remarks"></a>Poznámky  
 Pomocí  **>>=**  operátor je přesně stejné jako zadání:  
  
```JavaScript  
result = result >> expression  
```  
  
 **>>=**  Operátor posune bitů z *výsledek* právo podle počtu bitů zadaný v *výraz*. Přihlašovací bit z *výsledek* se používá k vyplnění číslic od levého okraje. Číslic přesunout mimo vpravo se zahodí. Po vyhodnocení následující kód například *temp* má hodnotu -4: 14 (11110010 v binárním) zapuštěno správných bitů dva rovná -4 (11111100 v binárním).  
  
```JavaScript  
var temp  
temp = -14  
temp >>= 2  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Bitový operátor posunu vlevo (<\<)](../../javascript/reference/bitwise-left-shift-operator-decrement-javascript.md)   
 [Operátor bitového posunutí doprava (>>)](../../javascript/reference/bitwise-right-shift-operator-decrement-javascript.md)   
 [Operátor posunutí doprava bez znaménka (>>>)](../../javascript/reference/unsigned-right-shift-operator-decrement-javascript.md)   
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)