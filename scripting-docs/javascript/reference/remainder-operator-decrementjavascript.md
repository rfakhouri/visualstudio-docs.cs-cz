---
title: Remainder – operátor (JavaScript) | Microsoft Docs
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
- '%'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- remainder operator, JavaScript
- '% operator [JavaScript]'
- Remainder function [JavaScript]
ms.assetid: 087d654f-623b-498d-95ff-596d26bf674d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ce74b8512b25cfe215d294873102b274623b42a2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791379"
---
# <a name="remainder-operator-javascript"></a>Operátor zbytku (JavaScript)
Vydělí hodnoty jeden výraz hodnotou jiného a vrátí zbytek.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
result = number1 % number2  
```  
  
## <a name="arguments"></a>Arguments  
 `result`  
 Všechny proměnné.  
  
 `number1`  
 Jakýkoli číselný výraz.  
  
 `number2`  
 Jakýkoli číselný výraz.  
  
## <a name="remarks"></a>Poznámky  
 Operátor zbytku rozdělí `number1` podle `number2`a vrátí pouze zbytek jako `result`. Znaménko `result` je stejný jako znaménko `number1`. Hodnota `result` je mezi 0 a absolutní hodnotu `number2`.  
  
 Následující kód ukazuje, jak použít operátor zbytku.  
  
```  
var modResult = 19 % 6.7;  
document.write(modResult);  
  
// Output: 5.6  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)
