---
title: "Operátor přiřazení sčítání (+=) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: +=
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- addition assignment operator (+=)
- += operator
- assignment operators, JavaScript
ms.assetid: 8517d05c-38b0-4107-bea4-253eb420f438
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 38d86c537dda90dd7f44923b97384b3609dad5ba
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="addition-assignment-operator--javascript"></a>Operátor přiřazení sčítání (+=) (JavaScript)
Přidá hodnotu výrazu na hodnotu proměnné a přiřadí výsledek proměnné.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result += expression   
```  
  
## <a name="parameters"></a>Parametry  
 `result`  
 Všechny proměnné.  
  
 `expression`  
 Jakýkoli výraz.  
  
## <a name="remarks"></a>Poznámky  
 Pomocí tohoto operátoru je přesně stejný jako určující: `result = result + expression`.  
  
 Typy dvou výrazů určují chování `+=` operátor.  
  
|If|Pak...|  
|--------|----------|  
|Oba výrazy jsou číselná nebo logická hodnota|Přidejte|  
|Řetězce jsou oba výrazy|Řetězení|  
|Jeden výraz je číselné a druhá je řetězec|Řetězení|  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Operátor sčítání (+)](../../javascript/reference/addition-operator-decrement-javascript.md)   
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)