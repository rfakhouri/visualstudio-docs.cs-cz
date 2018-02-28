---
title: "Logický operátor NOT (!) (JavaScript) | Microsoft Docs"
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
- '!'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Logical NOT operator
- '! operator'
- '! operator, about ! operator'
ms.assetid: 68c3dc71-ae95-4293-9155-67405846d71d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 29c27b9cd670989eb2112de5067e68bd09d76903
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="logical-not-operator--javascript"></a>Logický operátor NOT (!) (JavaScript)
Provede logickou negaci výrazu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result = !expression  
```  
  
## <a name="parameters"></a>Parametry  
 *výsledek*  
 Všechny proměnné.  
  
 *výraz*  
 Jakýkoli výraz.  
  
## <a name="remarks"></a>Poznámky  
 Následující tabulka popisuje, jak *výsledek* je určen.  
  
|Pokud `expression` je|Potom `result` je|  
|------------------------|----------------------|  
|Hodnota TRUE|False|  
|False|Hodnota TRUE|  
  
 Všechny unární operátory, jako **!** operátor, vyhodnocení výrazů následujícím způsobem:  
  
-   Pokud se aplikují na undefined nebo `null` se vyvolá výrazy, Chyba spuštění.  
  
-   Objekty jsou převedeny na řetězce.  
  
-   Řetězce jsou převedeny na čísla Pokud je to možné. Pokud ne, je vyvolána chyba spuštění.  
  
-   Logické hodnoty jsou považovány za čísla (0, pokud je hodnota false, 1-li hodnota PRAVDA).  
  
 Operátor se použije pro výsledný číslo.  
  
 Pro **!** operátor, pokud *výraz* nenulový, *výsledek* je nulová. Pokud *výraz* rovná nule, *výsledek* je 1.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Bitový operátor NOT (~)](../../javascript/reference/bitwise-not-operator-decrement-tilde-javascript.md)   
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)