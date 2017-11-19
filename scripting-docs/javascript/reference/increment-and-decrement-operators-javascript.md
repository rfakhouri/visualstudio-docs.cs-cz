---
title: "Operátory snížení (--) (JavaScript) a přírůstku (++) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- --
- ++
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- increment operators, syntax
- ++ operator
- ++ operator, about ++ operator
- decrement operators, syntax
- -- operator
ms.assetid: 49eaf4cf-8818-478d-a429-cdd2ece20811
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 806bd321bb1f81d585a6595b8cf2842571164921
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="increment--and-decrement----operators-javascript"></a>Operátory přírůstku (++) a snížení (--) (JavaScript)
Zvýší operátor přírůstku a snížení hodnoty operátor snížení hodnoty proměnné o jednu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      result = ++variable  
result = --variable  
result = variable++  
result = variable--  
```  
  
## <a name="parameters"></a>Parametry  
 `result`  
 Všechny proměnné.  
  
 `variable`  
 Všechny proměnné.  
  
## <a name="remarks"></a>Poznámky  
 Pokud operátor se zobrazuje před proměnnou, je hodnota změněna předtím, než je tento výraz vyhodnocen. Pokud operátor se zobrazí po proměnnou, hodnota je změnit, jakmile je tento výraz vyhodnocen.  Jinými slovy, zadané `j = ++k;`, hodnota `j` je původní hodnota `k` plus jedna; zadaný `j = k++;`, hodnotu `j` je původní hodnota `k`, které se zvýší po jeho hodnota je přiřazena `j`.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)