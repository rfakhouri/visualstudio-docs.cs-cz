---
title: Number – objekt (JavaScript) | Microsoft Docs
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
- Number_JavaScript
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Number object
ms.assetid: 76e87c37-cf6c-46cc-bafa-04be1fe3d78d
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7cbe58fdc9673a8fffe35b8b15d7edbf86ffa655
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24792024"
---
# <a name="number-object-javascript"></a>Number – objekt (JavaScript)
Objekt, který představuje číslo jakéhokoli druhu. Všechna čísla JavaScript jsou čísla s plovoucí desetinnou čárkou 64-bit.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
numObj = new Number(value)  
```  
  
## <a name="parameters"></a>Parametry  
 `numObj`  
 Požadováno. Název proměnné, do kterého `Number` objekt je přiřazen.  
  
 `value`  
 Požadováno. Číselná hodnota.  
  
## <a name="remarks"></a>Poznámky  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]vytvoří `Number` objekty proměnné nastavena na hodnotu číslo, například `var num = 255.336;`. Obvykle není nutné vytvořit `Number` explicitně objekty.  
  
 `Number` Objekt má svou vlastní vlastnosti a metody, kromě pro vlastnosti a metody zděděno z `Object`. Čísla se převedou na řetězce za určitých okolností pro třeba když je přidána nebo zřetězen s řetězec, stejně jako pomocí číslo znamená z `toString` metoda. Další informace najdete v tématu [operátor sčítání (+)](../../javascript/reference/addition-operator-decrement-javascript.md).  
  
 JavaScript má několik číselné konstanty. Úplný seznam najdete v tématu [číslo konstanty](../../javascript/reference/number-constants-javascript.md).  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="properties"></a>Vlastnosti  
 Následující tabulka uvádí vlastnosti `Number` objektu.  
  
|Vlastnost|Popis|  
|--------------|-----------------|  
|[constructor – vlastnost](../../javascript/reference/constructor-property-object-javascript.md)|Určuje funkci, která vytvoří objekt.|  
|[prototype – vlastnost](../../javascript/reference/prototype-property-object-javascript.md)|Vrátí odkaz na prototyp třídy objektů.|  
  
## <a name="functions"></a>Funkce  
 Následující tabulka uvádí funkce `Number` objektu.  
  
|Funkce|Popis|  
|--------------|-----------------|  
|[Number.isfinite – funkce](../../javascript/reference/number-isfinite-function-number-javascript.md)|Vrátí logickou hodnotu, která určuje, zda je hodnota omezené.|  
|[Number.isinteger – funkce](../../javascript/reference/number-isinteger-function-number-javascript.md)|Vrátí logickou hodnotu, která určuje, zda hodnota je celé číslo.|  
|[Number.isNaN – funkce](../../javascript/reference/number-isnan-function-number-javascript.md)|Vrátí logickou hodnotu, která určuje, zda je hodnota vyhrazenou hodnotou `NaN` (není číslo).|  
|[Number.isSafeInteger](../../javascript/reference/number-issafeinteger-number-javascript.md)|Vrátí logickou hodnotu, která určuje, zda hodnota může být bezpečně reprezentována v jazyce JavaScript.|  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `Number` objektu.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[hasOwnProperty – metoda](../../javascript/reference/hasownproperty-method-object-javascript.md)|Vrátí logickou hodnotu, která označuje, zda má objekt vlastnost se zadaným názvem.|  
|[isPrototypeOf – metoda](../../javascript/reference/isprototypeof-method-object-javascript.md)|Vrátí logickou hodnotu, která určuje, zda objekt existuje v hierarchii prototypu jiný objekt.|  
|[propertyIsEnumerable – metoda](../../javascript/reference/propertyisenumerable-method-object-javascript.md)|Vrátí logickou hodnotu, která označuje, zda zadaná vlastnost je součástí objektu a zda je vyčíslitelná.|  
|[toExponential – metoda](../../javascript/reference/toexponential-method-number-javascript.md)|Vrátí řetězec, který obsahuje počet v exponenciálním zápisu.|  
|[toFixed – metoda](../../javascript/reference/tofixed-method-number-javascript.md)|Vrátí řetězec, který představuje číslo s pevnou desetinnou čárkou notaci.|  
|[toLocaleString – metoda](../../javascript/reference/tolocalestring-number.md)|Vrátí objekt převést na řetězec v závislosti na aktuální národní prostředí.|  
|[toPrecision – metoda](../../javascript/reference/toprecision-method-number-javascript.md)|Vrátí řetězec, který obsahuje čísla, která je reprezentována notaci exponenciální nebo s pevnou desetinnou čárkou a má zadaný počet číslic.|  
|[toString – metoda](../../javascript/reference/tostring-method-object-javascript.md)|Vrátí řetězcovou reprezentaci objektu.|  
|[valueOf – metoda](../../javascript/reference/valueof-method-object-javascript.md)|Vrátí primitivní hodnotu zadaného objektu.|  
  
## <a name="see-also"></a>Viz také  
 [JavaScript – objekty](../../javascript/reference/javascript-objects.md)   
 [Math – objekt](../../javascript/reference/math-object-javascript.md)   
 [New – operátor](../../javascript/reference/new-operator-decrementjavascript.md)