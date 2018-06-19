---
title: Bitový operátor NOT (~) (JavaScript) | Microsoft Docs
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
- "~"
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- NOT operator
- bitwise operators, NOT operator
ms.assetid: 39f92474-fe05-4a8b-9ad8-caca93f82bca
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aec64b055b260efb7a4b0d952aed9b3a5d7ddc82
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789189"
---
# <a name="bitwise-not-operator--javascript"></a>Bitový operátor NOT (~) (JavaScript)
Provede bitový operátor NOT (negace) na výrazu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result = ~ expression  
```  
  
## <a name="parameters"></a>Parametry  
 *výsledek*  
 Všechny proměnné.  
  
 *výraz*  
 Jakýkoli výraz.  
  
## <a name="remarks"></a>Poznámky  
 Všechny unární operátory, jako `~` operátor, vyhodnocení výrazů následujícím způsobem:  
  
-   Pokud se aplikují na undefined nebo `null` se vyvolá výrazy, Chyba spuštění.  
  
-   Objekty jsou převedeny na řetězce.  
  
-   Řetězce jsou převedeny na čísla Pokud je to možné. Pokud ne, je vyvolána chyba spuštění.  
  
-   Logické hodnoty jsou považovány za čísla (0, pokud je hodnota false, 1-li hodnota PRAVDA).  
  
 Operátor se použije pro výsledný číslo.  
  
 `~` Operátor vypadá na binární reprezentace hodnoty výrazu a nemá bitovou negaci operaci na něm.  
  
 Všechny číslice, který je 1 ve výrazu se změní na 0 ve výsledku. Všechny číslice, který je 0 ve výrazu se změní na 1 ve výsledku.  
  
 Následující příklad ukazuje použití bitové hodnotě operátor NOT (~).  
  
```  
var temp = ~5;  
```  
  
 Výsledná hodnota je -6, jak je znázorněno v následující tabulce.  
  
|Výraz|Binární hodnotu (dvě na doplňku)|Desetinnou hodnotu|  
|----------------|---------------------------------------|-------------------|  
|5|00000000 00000000 00000000 00000101|5|  
|~5|11111111 11111111 11111111 11111010|-6|  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Logický operátor NOT (!)](../../javascript/reference/logical-not-operator-decrement-exclpt-javascript.md)   
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)