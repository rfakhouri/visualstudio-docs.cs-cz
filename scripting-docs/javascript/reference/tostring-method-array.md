---
title: toString – metoda (pole) | Microsoft Docs
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
ms.assetid: 71fbea85-3e00-41b0-b167-25e4281e5e8a
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6dc7cbf843e47ffc2d21f5a2b1d03c43e675a130
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791631"
---
# <a name="tostring-method-array"></a>toString – metoda (Array)
Vrátí řetězcovou reprezentaci pole.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
array.toString()  
```  
  
## <a name="parameters"></a>Parametry  
 `array`  
 Požadováno. Pole představují jako řetězec.  
  
## <a name="return-value"></a>Návratová hodnota  
 Řetězcová reprezentace pole.  
  
## <a name="remarks"></a>Poznámky  
 Elementy `Array` jsou převedeny na řetězce. Výsledný řetězce jsou zřetězeny a oddělených čárkami.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití **toString** metoda s pole.  
  
```JavaScript  
var arr = [1, 2, 3, 4];  
var s = arr.toString();  
document.write(s);  
  
// Output: 1,2,3,4  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]