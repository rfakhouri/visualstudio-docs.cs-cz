---
title: Number.isSafeInteger (Number) (JavaScript) | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: c7ef6ce8-fe71-4e53-be44-4dd440aef21d
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eebc2147bc5043341be7e883548af825922036f9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="numberissafeinteger-number-javascript"></a>Number.isSafeInteger (Number) (JavaScript)
Vrátí logickou hodnotu, která určuje, zda číslo může být bezpečně reprezentována v jazyce JavaScript.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Number.isSafeInteger(numValue)   
```  
  
## <a name="return-value"></a>Návratová hodnota  
 `true`Pokud je číslo mezi `Number.MIN_SAFE_INTEGER` a `Number.MAX_SAFE_INTEGER`, včetně; jinak hodnota `false`.  
  
## <a name="remarks"></a>Poznámky  
 Bezpečné celé číslo v jazyce JavaScript je ten, který je číslo dvojité přesnosti IEEE 754 před všechny zaokrouhlení byl použit.  
  
## <a name="example"></a>Příklad  
  
```JavaScript  
// Returns true  
Number.isSafeInteger(-100)  
Number.isSafeInteger(9007199254740991)  
  
// Returns false  
Number.isSafeInteger(Number.NaN)  
Number.isSafeInteger(Infinity)  
Number.isSafeInteger("100")  
Number.isSafeInteger(9007199254740992);  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
 **Platí pro**: [číslo objektu](../../javascript/reference/number-object-javascript.md)