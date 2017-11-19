---
title: "toExponential – metoda (Number) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: toExponential
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: toExponential method
ms.assetid: 7c4a6d84-3c1f-4cc4-a67d-7753e5d4ed66
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fff2f2bc0c443fa9308c8d01dcea42a3cec9ff04
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="toexponential-method-number-javascript"></a>toExponential – metoda (Number) (JavaScript)
Představuje číslo v exponenciálním zápisu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
numObj. toExponential([fractionDigits])  
```  
  
## <a name="parameters"></a>Parametry  
 `numObj`  
 Požadováno. A **číslo** objektu.  
  
 `fractionDigits`  
 Volitelné. Počet číslic za desetinnou čárkou. Musí být v rozsahu 0 – 20, včetně.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí řetězcovou reprezentaci číslo v exponenciálním zápisu. Řetězec, který obsahuje jednu číslici od desetinné čárky a může obsahovat `fractionDigits` číslic za ním.  
  
 Pokud `fractionDigits` se nedodává `toExponential` metoda vrátí počet číslic potřeba jednoznačně zadat číslo.  
  
## <a name="example"></a>Příklad  
  
```JavaScript  
var num = new Number(123);  
var exp = num.toExponential();  
document.write(exp);  
document.write("<br/>");  
  
num = new Number(123.456);  
exp = num.toExponential(5);  
document.write(exp);  
  
// Output:   
// 1.23e+2  
// 1.23456e+2  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Platí pro**: [číslo objektu](../../javascript/reference/number-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [toFixed – metoda (Number)](../../javascript/reference/tofixed-method-number-javascript.md)   
 [toPrecision – metoda (Number)](../../javascript/reference/toprecision-method-number-javascript.md)