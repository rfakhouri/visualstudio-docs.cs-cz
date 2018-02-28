---
title: "Logický operátor OR (|) (JavaScript) | Microsoft Docs"
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
- '||'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- '|| operator'
- logical OR operator
ms.assetid: 95295331-6269-4311-8391-dc1c68e116ab
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 80c8e1bcae57e13642a0c77ae75c7c2aac58ace6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="logical-or-operator--javascript"></a>Logický operátor OR (||) (JavaScript)
Provede logické disjunkce dvou výrazů.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result = expression1 || expression2  
```  
  
## <a name="parameters"></a>Parametry  
 *výsledek*  
 Všechny proměnné.  
  
 *Expression1*  
 Jakýkoli výraz.  
  
 *Výraz2*  
 Jakýkoli výraz.  
  
## <a name="remarks"></a>Poznámky  
 Pokud nebo oba výrazy vyhodnocení **True**, *výsledek* je **True**. Následující tabulka popisuje, jak *výsledek* je určen:  
  
|Pokud `expression1` je|A `expression2` je|`result` Je|  
|-------------------------|--------------------------|---------------------|  
|Hodnota TRUE|Hodnota TRUE|Hodnota TRUE|  
|Hodnota TRUE|False|Hodnota TRUE|  
|False|Hodnota TRUE|Hodnota TRUE|  
|False|False|False|  
  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]pro převedení hodnoty logickou hodnotu na logické hodnoty používá následující pravidla:  
  
-   Všechny objekty jsou považovány za hodnotu true.  
  
-   Řetězce jsou považovány za hodnotu NEPRAVDA, pokud jsou prázdné.  
  
-   `null`a Nedefinovaná jsou považovány za hodnotu false.  
  
-   Čísla jsou false v případě a pouze v případě, jsou 0.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)