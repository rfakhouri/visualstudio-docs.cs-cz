---
title: toFixed – metoda (Number) (JavaScript) | Microsoft Docs
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
- toFixed
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toFixed method
ms.assetid: b5f03400-865e-4ab2-818c-f734c0f6d6f0
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd51dd67632f4e6417fee72fd19575025423bbf1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791628"
---
# <a name="tofixed-method-number-javascript"></a>toFixed – metoda (Number) (JavaScript)
Představuje číslo s pevnou desetinnou čárkou notaci.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
numObj.toFixed([fractionDigits])  
```  
  
## <a name="parameters"></a>Parametry  
 `numObj`  
 Požadované A `Number` objektu.  
  
 `fractionDigits`  
 Volitelné. Počet číslic za desetinnou čárkou. Musí být v rozsahu 0 – 20, včetně.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí řetězcovou reprezentaci číslo s pevnou desetinnou čárkou notaci obsahující `fractionDigits` číslice za desetinnou čárkou.  
  
 Pokud `fractionDigits` není zadána nebo **nedefinované**, výchozí hodnota je nula.  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje, jak používat `toFixed`.  
  
```JavaScript  
var num = new Number(123);  
var fix = num.toFixed();  
document.write(fix);  
document.write("<br/>");  
  
num = new Number(123.456);  
fix = num.toFixed(5);  
document.write(fix);  
  
// Output:  
// 123  
123.45600  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Platí pro**: [číslo objektu](../../javascript/reference/number-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [toExponential – metoda (Number)](../../javascript/reference/toexponential-method-number-javascript.md)   
 [toPrecision – metoda (Number)](../../javascript/reference/toprecision-method-number-javascript.md)