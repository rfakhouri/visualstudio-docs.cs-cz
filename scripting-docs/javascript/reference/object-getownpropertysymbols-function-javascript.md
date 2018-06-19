---
title: Object.getownpropertysymbols – funkce (JavaScript) | Microsoft Docs
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
ms.assetid: 68dd69b9-5a33-44c2-ba5f-21a4ae6c0879
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2cc47ae365841332f11cb02da1469a4c9fff80c3
ms.sourcegitcommit: abae48f476832f79cc2c5bac43bb1226d3fe4e48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2018
ms.locfileid: "27814957"
---
# <a name="objectgetownpropertysymbols-function-javascript"></a>Object.getOwnPropertySymbols – funkce (JavaScript)
Vrátí vlastní symbol vlastnosti objektu. Vlastní symbol vlastnosti objektu jsou ty, které jsou definovány přímo na tento objekt a nedědí od objektu prototypu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Object.getOwnPropertySymbols(object);  
```  
  
#### <a name="parameters"></a>Parametry  
 `object`  
 Požadováno. Objekt, který obsahuje vlastní symboly.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pole, které obsahuje vlastní symboly objektu.  
  
## <a name="remarks"></a>Poznámky  
 Budete muset použít `Object.getOwnPropertySymbols` získat symbol vlastnosti objektu. `Object.getOwnPropertyNames`nevrátí vlastnosti symbolu.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje, jak získat symbol vlastnosti objektu.  
  
```JavaScript  
var obj = {};  
var key = Symbol('description');  
  
obj[key] = 'data';  
  
var symbols = Object.getOwnPropertySymbols(obj);  
  
console.log(symbols[0].toString());  
  
// Output:  
// undefined  
// Symbol(description)  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]