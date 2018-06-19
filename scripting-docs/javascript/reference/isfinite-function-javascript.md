---
title: isFinite – funkce (JavaScript) | Microsoft Docs
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
- isFinite
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- finite numbers
- isFinite method
ms.assetid: ea9287d2-892f-496b-86b7-f9196868d5cf
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ce78afe59190a03fb079841e7691f84c01eebedd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790608"
---
# <a name="isfinite-function-javascript"></a>isFinite – funkce (JavaScript)
Určuje, zda zadaný počet je omezený.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
isFinite(number)   
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `number` argument je libovolná číselná hodnota.  
  
 `isFinite` Funkce vrátí `true` Pokud `number` jiné než je jakákoli hodnota `NaN`, záporné nekonečno nebo kladné nekonečno. V takových případech tři vrátí **false**.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [Global – objekt](../../javascript/reference/global-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [isNaN – funkce](../../javascript/reference/isnan-function-javascript.md)