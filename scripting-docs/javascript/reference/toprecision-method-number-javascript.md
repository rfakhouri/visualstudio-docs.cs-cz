---
title: "toPrecision – metoda (Number) (JavaScript) | Microsoft Docs"
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
- toPrecision
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toPrecision method
ms.assetid: ac13c82f-1038-447a-823f-f755bba535ca
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eeab7642dcd88677d1b5a7102e3cf342d7ee1d29
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="toprecision-method-number-javascript"></a>toPrecision – metoda (Number) (JavaScript)
Představuje číslo, buď v notaci exponenciální nebo s pevnou desetinnou čárkou s zadaný počet číslic.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
numObj.toPrecision([precision])  
```  
  
## <a name="parameters"></a>Parametry  
 `numObj`  
 Požadováno. A `Number` objektu.  
  
 `precision`  
 Volitelné. Počet platných číslic. Musí být v rozsahu 1-21, včetně.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě čísel v exponenciálním zápisu `precision` - 1 se vrátí číslice za desetinnou čárkou. Pro čísla pevné notaci `precision` jsou vráceny platných číslic.  
  
 Pokud `precision` není zadána nebo je **nedefinované**, **toString** metoda je volána místo.  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje, jak používat `toPrecision`.  
  
```JavaScript  
var num = new Number(123);  
var prec = num.toPrecision();  
document.write(prec);  
document.write("<br/>");  
  
num = new Number(123.456);  
prec = num.toPrecision(5);  
document.write(prec);  
  
// Output:  
// 123  
// 123.46  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Platí pro**: [číslo objektu](../../javascript/reference/number-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [toFixed – metoda (Number)](../../javascript/reference/tofixed-method-number-javascript.md)   
 [toExponential – metoda (Number)](../../javascript/reference/toexponential-method-number-javascript.md)