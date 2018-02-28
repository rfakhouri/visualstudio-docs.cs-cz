---
title: "isNaN – funkce (JavaScript) | Microsoft Docs"
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
- isNaN
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- isNaN method
ms.assetid: 5af4eb29-72f6-484f-93bd-04ae1261f849
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7b7e6d3687e795ea5d5e38308a8af0d73ba7f5ff
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="isnan-function-javascript"></a>isNaN – funkce (JavaScript)
Vrátí logickou hodnotu, která určuje, zda je hodnota vyhrazenou hodnotou `NaN` (není číslo).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
isNaN(numValue)   
```  
  
## <a name="return-value"></a>Návratová hodnota  
 `true`Pokud hodnotu převést na `Number` typ je `NaN`, jinak `false`.  
  
## <a name="remarks"></a>Poznámky  
 Požadované `numValue` je hodnota, která má být testována proti `NaN`.  
  
 Obvykle použijete tuto metodu pro testování návratové hodnoty z `parseInt` a `parseFloat` metody.  
  
 Alternativně proměnné, která obsahuje `NaN` nebo jiné hodnoty může porovnání na sebe sama. Pokud porovná jako různé, je `NaN`. Důvodem je, že `NaN` je pouze hodnotu, která se nerovná na sebe sama.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [Global – objekt](../../javascript/reference/global-object-javascript.md)  
  
## <a name="example"></a>Příklad  
  
```JavaScript  
// Returns false.  
isNaN(100);  
  
// Returns false.  
isNaN("100");  
  
// Returns true.  
isNaN("ABC");  
  
// Returns true.  
isNaN("10C");  
  
// Returns true.  
isNaN("abc123");  
  
// Returns true.  
isNaN(Math.sqrt(-1));           
```  
  
## <a name="see-also"></a>Viz také  
 [isFinite – funkce](../../javascript/reference/isfinite-function-javascript.md)   
 [NaN – konstanta](../../javascript/reference/nan-constant-javascript.md)   
 [parseFloat – funkce](../../javascript/reference/parsefloat-function-javascript.md)   
 [parseInt – funkce](../../javascript/reference/parseint-function-javascript.md)