---
title: Metoda lastIndexOf (pole) (JavaScript) | Microsoft Docs
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
- arrays [JavaScript], lastIndexOf method
- lastIndexOf method [JavaScript]
ms.assetid: 04f5145d-007e-498f-b06f-11ab384c2968
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 12d2a0fca7a7cd82543a83ea19aca49d3cbb93b6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="lastindexof-method-array-javascript"></a>lastIndexOf – metoda (Array) (JavaScript)
Vrátí index posledního výskytu zadané hodnoty v poli.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
array1.lastIndexOf(searchElement[, fromIndex])  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Definice|  
|---------------|----------------|  
|`array1`|Požadováno. Objekt pole pro vyhledávání.|  
|`searchElement`|Požadováno. Hodnota má být vyhledán ve `array1`.|  
|`fromIndex`|Volitelné. Index pole, kdy má začít prohledávání. Pokud `fromIndex` je tento parametr vynechán, spustí vyhledávání v poslední index v poli.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Index posledního výskytu `searchElement` v poli nebo -1, pokud `searchElement` nebyl nalezen.  
  
## <a name="remarks"></a>Poznámky  
 `lastIndexOf` Metoda vyhledá pole pro zadanou hodnotu. Pokud zadaná hodnota není nalezena, vrátí metoda index prvního výskytu nebo -1.  
  
 Hledání dojde v sestupném pořadí indexu (nejprve poslední člen). Chcete-li hledat ve vzestupném pořadí, použijte [metoda indexOf (pole)](../../javascript/reference/indexof-method-array-javascript.md).  
  
 Elementy pole jsou ve srovnání s `searchElement` hodnoty striktní rovnosti, podobně jako porovnání provedené `===` operátor. Další informace najdete v tématu [operátory porovnání](../../javascript/reference/comparison-operators-javascript.md).  
  
 Volitelné `fromIndex` argument určuje hodnotu indexu pole kterého má začít prohledávání. Pokud `fromIndex` je větší než nebo rovna hodnotě Délka pole, je prohledána celé pole. Pokud `fromIndex` je záporné, začíná hledání na plus délka pole `fromIndex`. Pokud počítaný index je menší než 0, vrátí se -1.  
  
## <a name="example"></a>Příklad  
 Následující příklady ilustrují použití `lastIndexOf` metoda.  
  
```JavaScript  
// Create an array.  
var ar = ["ab", "cd", "ef", "ab", "cd"];  
  
// Determine the first location, in descending order, of "cd".  
document.write(ar.lastIndexOf("cd") + "<br/>");  
  
// Output: 4  
  
// Find "cd" in descending order, starting at index 2.  
document.write(ar.lastIndexOf("cd", 2) + "<br/>");  
  
// Output: 1  
  
// Search for "gh" (which is not found).  
document.write(ar.lastIndexOf("gh")+ "<br/>");  
  
// Output: -1  
  
// Find "ab" with a fromIndex argument of -3.  
// The search in descending order starts at index 3,  
// which is the array length minus 2.  
document.write(ar.lastIndexOf("ab", -3) + "<br/>");  
// Output: 0  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Metoda indexOf (pole)](../../javascript/reference/indexof-method-array-javascript.md)   
 [Array – objekt](../../javascript/reference/array-object-javascript.md)   
 [Použití polí](../../javascript/advanced/using-arrays-javascript.md)