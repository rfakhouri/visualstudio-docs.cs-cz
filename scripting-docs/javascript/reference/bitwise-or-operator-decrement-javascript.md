---
title: "Bitový operátor OR (|) (JavaScript) | Microsoft Docs"
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
- '|'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- bitwise operators, OR operator
- OR operator
- '| operator'
ms.assetid: ffc8f758-3151-478e-bafb-fc78f1c469a0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a91c616c84b9d38154bf936f61fb856a4ebad0f7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="bitwise-or-operator--javascript"></a>Bitový operátor OR (|) (JavaScript)
Bitový operátor OR provádí dvou výrazů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result = expression1 | expression2  
```  
  
## <a name="parameters"></a>Parametry  
 *výsledek*  
 Všechny proměnné.  
  
 *Expression1*  
 Jakýkoli výraz.  
  
 *Výraz2*  
 Jakýkoli výraz.  
  
## <a name="remarks"></a>Poznámky  
 **&#124;** operátor vypadá na binární reprezentace hodnoty dvou výrazů a nemá bitové operace OR na ně. Výsledek této operace chová následovně:  
  
```JavaScript  
0101   (expression1)  
1100   (expression2)  
----  
1101   (result)  
```  
  
 Buď kdykoli z výrazů má v číslice 1, výsledek bude mít v této číslice 1. Výsledek, jinak bude mít 0 v této číslice.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Bitový operátor přiřazení OR (&#124; =)](../../javascript/reference/bitwise-or-assignment-operator-decrement-equal-javascript.md)   
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)