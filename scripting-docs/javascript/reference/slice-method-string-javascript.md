---
title: Slice – metoda (String) (JavaScript) | Microsoft Docs
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
- slice
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- strings [Visual Studio], returning characters
- slice method
ms.assetid: 80cd77a6-3718-492e-8e96-f909d8721d91
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1baa0a05a2d6aa8c06cc962761c8e557632d034c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791820"
---
# <a name="slice-method-string-javascript"></a>slice – metoda (String) (JavaScript)
Vrátí část řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
stringObj.slice(start, [end])   
```  
  
## <a name="parameters"></a>Parametry  
 `stringObj`  
 Požadováno. A `String` objekt nebo řetězcový literál.  
  
 `start`  
 Požadováno. Index na začátek zadaný část `stringObj`.  
  
 `end`  
 Volitelné. Index na konec zadaný část `stringObj`. Dílčí řetězec až obsahuje znaky, ale ne včetně znak označená `end`. Pokud tato hodnota není zadaná, dílčí řetězec pokračuje na konec `stringObj`.  
  
## <a name="remarks"></a>Poznámky  
 `slice` Metoda vrátí `String` objekt obsahující zadanou část `stringObj`.  
  
 `slice` Metoda zkopíruje až do, nikoli však znak indikován `end`.  
  
 Pokud `start` je záporná, je považován za *délka*  +  `start` kde *délka* je délka řetězce. Pokud `end` je záporná, je považován za *délka* + `end`. Pokud `end` je tento parametr vynechán, kopírování pokračuje na konec `stringObj`. Pokud `end` dojde před `start`, žádné znaky jsou zkopírovány do nového řetězce.  
  
## <a name="example"></a>Příklad  
 V prvním příkladu `slice` metoda vrátí celý řetězec. V druhém příkladu `slice` metoda vrátí celý řetězec, s výjimkou poslední znak.  
  
```JavaScript  
var str1 = "all good boys do fine";  
  
var slice1 = str1.slice(0);  
var slice2 = str1.slice(0,-1);  
var slice3 = str1.slice(4);  
var slice4 = str1.slice(4, 8);  
  
document.write(slice1 + "<br/>");  
document.write(slice2 + "<br/>");  
document.write(slice3 + "<br/>");  
document.write(slice4);  
  
// Output:  
// all good boys do fine  
// all good boys do fin  
// good boys do fine  
// good  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [řetězce objektu](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Metoda slice (pole)](../../javascript/reference/slice-method-array-javascript.md)