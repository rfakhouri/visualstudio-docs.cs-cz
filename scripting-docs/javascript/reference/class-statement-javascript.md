---
title: Class – příkaz (JavaScript) | Microsoft Docs
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
ms.assetid: bf45ebad-4678-4062-88df-55d32b603c69
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e828ae86c3f8f585179e3b097d98b3449c3f3b45
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789174"
---
# <a name="class-statement-javascript"></a>class – příkaz (JavaScript)
Deklaruje novou třídu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class classname () [extends object] {    [constructor([arg1 [,... [,argN]]]) {        statements    }]    [[static] method([arg1 [,... [,argN]]]) {        statements    }]}  
```  
  
#### <a name="parameters"></a>Parametry  
 `classname`  
 Požadováno. Název třídy.  
  
 `object`  
 Volitelné. Objekt nebo třída, ze kterého nové třídy dědí vlastnosti a metody.  
  
 `constructor`  
 Volitelné. Funkce konstruktoru, která inicializuje novou instanci třídy.  
  
 `arg1...argN`  
 Volitelné. Volitelné, oddělených čárkami seznam argumentů funkce rozumí.  
  
 `statements`  
 Volitelné. Jeden nebo více [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] příkazy.  
  
 `static`  
 Volitelné. Určuje statickou metodu.  
  
 `method`  
 Volitelné. Jeden nebo více [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] instance nebo statické metody, které lze volat u instance třídy.  
  
## <a name="remarks"></a>Poznámky  
 Třída umožňuje vytvářet nové objekty pomocí založených na prototypu dědičnosti, konstruktory, instanci metody a statické metody. Můžete použít `super` objekt v rámci konstruktoru třídy nebo volat stejné konstruktor metodu – třída nebo metoda v nadřazené třídy nebo objektu. Volitelně můžete pomocí `extends` příkaz po název třídy určete třídu nebo objekt, ze kterého nové třídy dědí metody.  
  
## <a name="example"></a>Příklad  
  
```JavaScript  
class Spelunking extends EXPERIENCE.Outdoor {  
  constructor(name, location) {  
    super(name, location);  
  
    this.minSkill = Spelunking.defaultSkill();  
    //...  
  }  
  update(minSkill) {  
    //...  
    super.update(minSkill);  
  }  
  static defaultSkill() {  
    return new EXPERIENCE.Level3();  
  }  
}  
```  
  
## <a name="example"></a>Příklad  
 Můžete také vytvořit názvy vypočítané vlastnosti pro třídy. Následující příklad kódu vytvoří pomocí názvu vypočítané vlastnosti `set` syntaxe.  
  
```JavaScript  
var propName = "prop_42";  
  
class Spelunking {  
    set [propName](v) {  
        this.value = v;  
    }  
};  
  
var s = new Spelunking();  
console.log(s.value);  
s.prop_42 = 42;  
console.log(s.value);  
  
// Output:  
// undefined  
// 42  
  
```  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu vytvoří název vlastnosti pro třídu dynamicky použitím `get` syntaxe.  
  
```JavaScript  
var propName = "prop_42";  
  
class Spelunking {  
    get [propName]() {  
        return 777;  
    }  
}  
  
var s = new Spelunking();  
console.log(s.prop_42);  
  
// Output:  
// 777  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12exp](../../javascript/reference/includes/jsv12exp-md.md)]