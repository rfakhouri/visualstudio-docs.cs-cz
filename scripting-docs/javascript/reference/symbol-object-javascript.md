---
title: "Symbol – objekt (JavaScript) | Microsoft Docs"
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
ms.assetid: 2ad059f1-4b7f-4758-882a-c74ce1283ab0
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cd755d5b753eb91b89b869645287685a97f8f571
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="symbol-object-javascript"></a>Symbol – objekt (JavaScript)
Umožňuje vytvořit jedinečný identifikátor.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
obj = Symbol(desc)  
```  
  
#### <a name="parameters"></a>Parametry  
 `desc`  
 Volitelné. Popis symbolu.  
  
## <a name="remarks"></a>Poznámky  
 Symbol objekty povolit vlastnosti, které chcete přidat do stávajících objektů se možné narušení s existující vlastnosti objektu, žádné nezamýšleným viditelnost a žádné nekoordinovaná dodatky jiným kódem.  
  
 Symbol je typu primitivní datové. Symbol objekty nelze vytvořit pomocí `new` operátor.  
  
 Přidat symbol objekty globální symbol registru, použijte `Symbol.for` a `Symbol.keyFor` funkce. Pokud jste serializovat symboly jako řetězce, ujistěte se, že konkrétní řetězec mapuje na správný symbol pro vyhledávání všech pomocí registru globální symbol.  
  
 JavaScript zahrnuje následující hodnoty vestavěný symbol, které jsou k dispozici v globálním oboru.  
  
|Symbol|Popis|  
|------------|-----------------|  
|`Symbol.hasInstance`|Tato metoda určuje, zda objekt konstruktor rozpozná objekt jako jednu z instancí v konstruktoru. Používá se interně pomocí `instanceof` operátor.|  
|`Symbol.isConcatSpreadable`|Tato vlastnost vrací logickou hodnotu, která určuje, zda objekt by měl vyrovnány na jeho pole elementy ve `Array.concat`.|  
|`Symbol.iterator`|Tato metoda vrátí výchozí iterator pro objekt. Používá se interně pomocí `for...of` příkaz.|  
|`Symbol.toPrimitive`|Tato metoda převede objekt na odpovídající primitivní hodnota. Používá se interně pomocí `ToPrimitive` abstraktní operace.|  
|`Symbol.toStringTag`|Tato vlastnost vrátí hodnotu řetězce, který slouží k usnadnění vytváření výchozí řetězec popis objektu. Se používá interně předdefinované metodou `Object.toString` metoda.|  
|`Symbol.unscopables`|Tato vlastnost vrátí objekt, jehož vlastnosti jsou vyloučeny z `with` prostředí vazby přidruženého objektu.|  
  
## <a name="functions"></a>Funkce  
 Následující tabulka uvádí funkce `Symbol` objektu.  
  
|||  
|-|-|  
|Vlastnost|Popis|  
|[Symbol.for –](../../javascript/reference/symbol-for-function-javascript.md)|Vrátí symbol pro zadaný klíč, nebo pokud klíč neexistuje, vytvoří nový objekt symbol pomocí nového klíče.|  
|[Symbol.keyfor –](../../javascript/reference/symbol-keyfor-function-javascript.md)|Vrátí klíč pro zadaný symbol.|  
|||  
  
## <a name="example"></a>Příklad  
  
```JavaScript  
(function() {  
  
    // module-scoped symbol  
    var key = Symbol("description");  
  
    function MyClass(privateData) {  
      this[key] = privateData;  
    }  
  
    MyClass.prototype = {  
      someFunc: function() {  
        return "data: " + this[key];  
      }  
    };  
  
    var c = new MyClass("private data")  
    console.log(key);  
    console.log(c["key"]);  
    console.log(c.someFunc());  
  
})();  
  
// Output:  
// undefined  
// undefined  
// data: private data  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]