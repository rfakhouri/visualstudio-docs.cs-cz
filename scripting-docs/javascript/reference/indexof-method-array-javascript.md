---
title: Metoda indexOf (pole) (JavaScript) | Microsoft Docs
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
helpviewer_keywords:
- arrays [JavaScript], indexOf method
- indexOf method [JavaScript]
ms.assetid: 5bee31ae-aaf1-4466-8cfd-ed287e3cdf17
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 63685219faf42991da6b798493c58b356ab97279
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="indexof-method-array-javascript"></a>indexOf – metoda (Array) (JavaScript)
Vrátí index prvního výskytu hodnoty v poli.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
array1.indexOf(searchElement[, fromIndex])  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Definice|  
|---------------|----------------|  
|`array1`|Požadováno. Objekt Array.|  
|`searchElement`|Požadováno. Hodnota má být vyhledán ve `array1`.|  
|`fromIndex`|Volitelné. Index pole, kdy má začít prohledávání. Pokud `fromIndex` je tento parametr vynechán, spustí vyhledávání na pozici 0.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Index prvního výskytu `searchElement` v poli nebo -1, pokud `searchElement` nebyl nalezen.  
  
## <a name="remarks"></a>Poznámky  
 `indexOf` Metoda vyhledá pole pro zadanou hodnotu. Pokud zadaná hodnota není nalezena, vrátí metoda index prvního výskytu nebo -1.  
  
 Hledání dochází ve vzestupném pořadí index.  
  
 Elementy pole jsou ve srovnání s `searchElement` hodnoty striktní rovnosti, podobně jako `===` operátor. Další informace najdete v tématu [operátory porovnání](../../javascript/reference/comparison-operators-javascript.md).  
  
 Volitelné `fromIndex` argument určuje hodnotu indexu pole kterého má začít prohledávání. Pokud `fromIndex` je větší než nebo rovna hodnotě Délka pole, je vrácen -1. Pokud `fromIndex` je záporné, začíná hledání na plus délka pole `fromIndex`.  
  
## <a name="example"></a>Příklad  
 Následující příklady ilustrují použití `indexOf` metoda.  
  
```JavaScript  
// Create an array. (The elements start at index 0.)  
var ar = ["ab", "cd", "ef", "ab", "cd"];  
  
// Determine the first location of "cd".  
document.write(ar.indexOf("cd") + "<br/>");  
  
// Output: 1  
  
// Find "cd" starting at index 2.  
document.write(ar.indexOf("cd", 2) + "<br/>");  
  
// Output: 4  
  
// Find "gh" (which is not found).  
document.write (ar.indexOf("gh")+ "<br/>");  
  
// Output: -1  
  
// Find "ab" with a fromIndex argument of -2.  
// The search starts at index 3, which is the array length plus -2.  
document.write (ar.indexOf("ab", -2) + "<br/>");  
// Output: 3  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Metody jazyka JavaScript](../../javascript/reference/javascript-methods.md)   
 [Array – objekt](../../javascript/reference/array-object-javascript.md)   
 [Použití polí](../../javascript/advanced/using-arrays-javascript.md)