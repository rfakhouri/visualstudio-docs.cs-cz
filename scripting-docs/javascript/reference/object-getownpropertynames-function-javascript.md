---
title: Object.getownpropertynames – funkce (JavaScript) | Microsoft Docs
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
helpviewer_keywords:
- getOwnPropertyNames method [JavaScript]
- Object.getOwnPropertyNames method [JavaScript]
ms.assetid: 59f4b6b1-02be-44b3-a06c-a5ca8f70c3d8
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 76ca0036b9dedf7b4cee7b543469939e35dfe8d1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791487"
---
# <a name="objectgetownpropertynames-function-javascript"></a>Object.getOwnPropertyNames – funkce (JavaScript)
Vrátí názvy vlastních vlastností objektu. Vlastní vlastnosti objektu jsou ty, které jsou definovány přímo na tento objekt a nedědí od objektu prototypu. Vlastnosti objektu obsahovat pole (objektů) a funkce.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
Object.getOwnPropertyNames(object)  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Definice|  
|---------------|----------------|  
|`object`|Požadováno. Objekt, který obsahuje vlastní vlastnosti.|  
  
## <a name="return-value"></a>Návratová hodnota  
 Pole, které obsahuje názvy vlastních vlastností objektu.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud je hodnota zadaná pro `object` argument není název objektu, `TypeError` je vyvolána výjimka.  
  
## <a name="remarks"></a>Poznámky  
 `getOwnPropertyNames` Metoda vrátí názvy vyčíslitelná a výčtové vlastnosti a metody. Chcete-li vrátit pouze názvy vyčíslitelná vlastností a metod, můžete použít [Object.Keys – funkce](../../javascript/reference/object-keys-function-javascript.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří objekt, který má tři vlastnosti a metody. Poté použije `getOwnPropertyNames` metoda získat vlastní vlastnosti (včetně metodu) objektu.  
  
```JavaScript  
function Pasta(grain, width, shape) {  
    // Define properties.  
    this.grain = grain;  
    this.width = width;  
    this.shape = shape;  
    this.toString = function () {  
        return (this.grain + ", " + this.width + ", " + this.shape);  
    }  
}  
  
// Create an object.  
var spaghetti = new Pasta("wheat", 0.2, "circle");  
  
// Get the own property names.  
var arr = Object.getOwnPropertyNames(spaghetti);  
document.write (arr);  
  
// Output:  
//   grain,width,shape,toString  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad zobrazuje názvy vlastností, které začínají na písmeno ' v **špagety** objekt zkonstruován pomocí **těstoviny** konstruktor.  
  
```JavaScript  
function Pasta(grain, size, shape) {  
    this.grain = grain;   
    this.size = size;   
    this.shape = shape;   
}  
  
var spaghetti = new Pasta("wheat", 2, "circle");  
  
var names = Object.getOwnPropertyNames(spaghetti).filter(CheckKey);  
document.write(names);   
  
// Check whether the first character of a string is 's'.   
function CheckKey(value) {  
    var firstChar = value.substr(0, 1);   
    if (firstChar.toLowerCase() == 's')  
        return true;   
    else  
         return false;   
}  
// Output:  
// size,shape  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Object.Keys – funkce](../../javascript/reference/object-keys-function-javascript.md)