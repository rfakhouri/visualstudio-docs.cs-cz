---
title: isPrototypeOf – metoda (Object) (JavaScript) | Microsoft Docs
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
- isPrototypeOf
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- isPrototypeOf method
ms.assetid: 9c821319-c208-480f-915e-565ef6e017b6
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 47ce97faecfade089bbf0b7a725a02ee73b54718
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790722"
---
# <a name="isprototypeof-method-object-javascript"></a>isPrototypeOf – metoda (Object) (JavaScript)
Určuje, zda objekt existuje v jiném řetězci prototypů objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
prototype.isPrototypeOf(object)  
```  
  
## <a name="parameters"></a>Parametry  
 `prototype`  
 Požadováno. Prototyp objektu.  
  
 `object`  
 Požadováno. Jiný objekt, jehož řetězec prototypu má být ověřen.  
  
## <a name="remarks"></a>Poznámky  
 `isPrototypeOf` Metoda vrátí `true` Pokud `object` má `prototype` ve svém řetězu prototypu. Řetězec prototypu se používá ke sdílení funkcí mezi instancemi stejného typu objektu. `isPrototypeOf` Metoda vrátí `false` při `object` není objekt nebo když `prototype` nezobrazí v řetězu prototypu `object`.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `isPrototypeOf` metoda.  
  
```JavaScript  
function Rectangle() {  
}  
  
var rec = new Rectangle();  
  
document.write(Rectangle.prototype.isPrototypeOf(rec));  
  
// Output: true  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [prototype – vlastnost (Object)](../../javascript/reference/prototype-property-object-javascript.md)