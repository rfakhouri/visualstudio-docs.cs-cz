---
title: Math.acosh – funkce (JavaScript) | Microsoft Docs
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
ms.assetid: 881dd2a0-36a5-403b-a3dc-523d8e1e1317
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1fd75140dfcf3d9ac703c2aeadf68bea4da9e0dc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791220"
---
# <a name="mathacosh-function-javascript"></a>Math.acosh – funkce (JavaScript)
Vrací hyperbolický Arkus kosinus (inverzní hyperbolický kosinus) čísla.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Math.acosh(number)  
```  
  
#### <a name="parameters"></a>Parametry  
 Požadované `number` argument je číselný výraz.  
  
## <a name="return-value"></a>Návratová hodnota  
 Inverzní hyperbolický kosinus `number` argument, v radiánech.  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje způsob použití `acosh` funkce.  
  
```JavaScript  
var v1 = Math.acosh(3);  
vary v2 = Math.acosh(-1);  
  
document.write(v1);  
document.write("</br>");  
document.write(v2);  
  
// Output:  
// 1.762747174039086  
// NaN  
  
```  
  
## <a name="remarks"></a>Poznámky  
 **Platí pro**: [Math – objekt](../../javascript/reference/math-object-javascript.md)  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Math.ACOS – funkce](../../javascript/reference/math-acos-function-javascript.md)   
 [Math.ASIN – funkce](../../javascript/reference/math-asin-function-javascript.md)   
 [Math.Atan – funkce](../../javascript/reference/math-atan-function-javascript.md)   
 [Math.cos – funkce](../../javascript/reference/math-cos-function-javascript.md)   
 [Math.sin – funkce](../../javascript/reference/math-sin-function-javascript.md)   
 [Math.tan – funkce](../../javascript/reference/math-tan-function-javascript.md)   
 [Math – objekt](../../javascript/reference/math-object-javascript.md)