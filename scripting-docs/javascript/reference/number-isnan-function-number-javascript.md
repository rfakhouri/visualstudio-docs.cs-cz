---
title: Number.isNaN funkce (Number) (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 2d9813d6-ec9c-433b-b060-8e3c3ff62ca4
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7c11abe2dd2fc70431800d31f4c44279a88cd75d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791226"
---
# <a name="numberisnan-function-number-javascript"></a>Number.isNaN – funkce (Number) (JavaScript)
Vrátí logickou hodnotu, která určuje, zda je hodnota vyhrazenou hodnotou `NaN` (není číslo).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Number.isNaN(numValue)   
```  
  
#### <a name="parameters"></a>Parametry  
 `numValue`  
 Požadováno. Hodnota, která má být testována proti `NaN`.  
  
## <a name="return-value"></a>Návratová hodnota  
 `true`Pokud hodnotu převést na `Number` typ je `NaN`, jinak `false`.  
  
## <a name="remarks"></a>Poznámky  
 Obvykle použijete tuto metodu pro testování návratové hodnoty z `parseInt` a `parseFloat` metody.  
  
 `Number.isNaN`vyřeší problémy s globální `isNaN` funkce. `Number.isNaN`pouze převede její argument na typ Number po porovná se s `NaN`. V důsledku toho vrátí `true` jenom v případě předaný argument je přesně stejnou hodnotu jako `NaN`. Na globální `isNaN` funkce převede její argument typ Číslo před porovnání, což může vést k vrácení hodnoty číslo- `true`, zatímco se nemusí vracet `true` pro `Number.isNaN`.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
 **Platí pro**: [číslo objektu](../../javascript/reference/number-object-javascript.md)  
  
## <a name="example"></a>Příklad  
  
```JavaScript  
// Returns true.  
Number.isNaN(NaN);  
Number.isNaN(Number.NaN);  
Number.isNaN(0 / 0);  
  
// Returns false.  
Number.isNaN(100);  
// Returns false.  
// Strings are converted to numbers and return false.  
Number.isNaN("100");  
Number.isNaN("ABC");  
Number.isNaN("10C");  
Number.isNaN("abc123");  
  
```