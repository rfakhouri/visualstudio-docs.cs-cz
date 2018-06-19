---
title: Object.Keys – funkce (JavaScript) | Microsoft Docs
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
- Object.keys method [JavaScript]
- keys method [JavaScript]
ms.assetid: cf4a7daf-cf28-4467-bc6b-f7f106ec3876
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0e725c3ab7206b04d9a900cb614b57c37dfc4351
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791433"
---
# <a name="objectkeys-function-javascript"></a>Object.keys – funkce (JavaScript)
Vrátí názvy výčtové vlastnosti a metody objektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```JavaScript  
Object.keys(object)  
```  
  
#### <a name="parameters"></a>Parametry  
  
|Parametr|Definice|  
|---------------|----------------|  
|`object`|Požadováno. Objekt obsahující vlastnosti a metody. To může být objekt, který jste vytvořili nebo existujícího objektu modelu DOM (Document Object).|  
  
## <a name="return-value"></a>Návratová hodnota  
 Pole, které obsahuje názvy výčtové vlastnosti a metody objektu.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud je hodnota zadaná pro `object` argument není název objektu, `TypeError` je vyvolána výjimka.  
  
## <a name="remarks"></a>Poznámky  
 `keys` Metoda vrátí pouze názvy výčtové vlastnosti a metody. Chcete-li vrátit názvy vyčíslitelná a výčtové vlastnosti a metody, můžete použít [Object.getownpropertynames – funkce](../../javascript/reference/object-getownpropertynames-function-javascript.md).  
  
 Informace o `enumerable` atribut vlastnosti, najdete v části [Object.defineproperty – funkce](../../javascript/reference/object-defineproperty-function-javascript.md) a [Object.getownpropertydescriptor – funkce](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md).  
  
## <a name="example"></a>Příklad  
 Následující příklad vytvoří objekt, který má tři vlastnosti a metody. Poté použije `keys` metoda získat vlastnosti a metody objektu.  
  
```JavaScript  
// Create a constructor function.  
function Pasta(grain, width, shape) {  
    this.grain = grain;  
    this.width = width;  
    this.shape = shape;  
  
    // Define a method.  
    this.toString = function () {  
        return (this.grain + ", " + this.width + ", " + this.shape);  
    }  
}  
  
// Create an object.  
var spaghetti = new Pasta("wheat", 0.2, "circle");  
  
// Put the enumerable properties and methods of the object in an array.  
var arr = Object.keys(spaghetti);  
document.write (arr);  
  
// Output:  
// grain,width,shape,toString  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad zobrazuje názvy všech výčtové vlastnosti, které začínat písmenem "g" v těstoviny objektu.  
  
```JavaScript  
// Create a constructor function.  
function Pasta(grain, width, shape) {  
    this.grain = grain;  
    this.width = width;  
    this.shape = shape;  
}  
  
var polenta = new Pasta("corn", 1, "mush");  
  
var keys = Object.keys(polenta).filter(CheckKey);  
document.write(keys);  
  
// Check whether the first character of a string is "g".  
function CheckKey(value) {  
    var firstChar = value.substr(0, 1);  
    if (firstChar.toLowerCase() == "g")  
        return true;  
    else  
        return false;  
}  
  
// Output:  
// grain  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Object.getownpropertynames – funkce](../../javascript/reference/object-getownpropertynames-function-javascript.md)