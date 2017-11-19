---
title: "Operátor odčítání (-) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '-'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '- operator, about - operator'
- '- operator'
- negation operator
- subtraction operator, syntax
- arithmetic operators, subtraction
- operators, subtraction
ms.assetid: cd0681d3-15cd-49fe-b4dd-e087de55d778
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb79aab0a57c733871dbfc73ac96c7ddbf4db37c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="subtraction-operator---javascript"></a>Operátor odčítání (-) (JavaScript)
Odečte hodnotu jeden výraz z jiného nebo poskytuje unární negace jeden výraz.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result = number1 - number2;  
```  
  
## <a name="parameters"></a>Parametry  
 *výsledek*  
 Všechny číselné proměnné.  
  
 `number`  
 Jakýkoli číselný výraz.  
  
 `number1`  
 Jakýkoli číselný výraz.  
  
 `number2`  
 Jakýkoli číselný výraz.  
  
## <a name="remarks"></a>Poznámky  
 V syntaxi 1  **-**  operátor je operátor odčítání aritmetické použít k vyhledání rozdíl dvou čísel. V syntaxi 2  **-**  operátor slouží jako operátor unární negace k označení záporné hodnoty výrazu.  
  
 Pro syntaxi 2 jako u všech unární operátory, se vyhodnotí výrazy následujícím způsobem:  
  
-   Pokud se aplikují na undefined nebo `null` se vyvolá výrazy, Chyba spuštění.  
  
-   Objekty jsou převedeny na řetězce.  
  
-   Řetězce jsou převedeny na čísla Pokud je to možné. Pokud ne, je vyvolána chyba spuštění.  
  
-   Logické hodnoty jsou považovány za čísla (0, pokud je hodnota false, 1-li hodnota PRAVDA).  
  
 Operátor se použije pro výsledný číslo. V syntaxi 2, pokud je výsledný číslo nenulové hodnoty *výsledek* se rovná výsledné číslo s jeho přihlašovací vrátit zpět. Pokud je výsledný číslo nula, *výsledek* je nulová.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Operátor přiřazení odčítání (-)](../../javascript/reference/subtraction-assignment-operator-decrement-equal-javascript.md)   
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)