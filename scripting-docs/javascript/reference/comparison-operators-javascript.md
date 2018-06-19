---
title: Operátory porovnávání (JavaScript) | Microsoft Docs
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
- Comparison
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- comparison operators, script
- greater than operator
- comparison operators
- greater than or equal to operator
- inequity operator
- identity operator
ms.assetid: 084f90f0-d010-47cf-96dd-13d637fc9b68
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 067d570523fc2241b4f2e0442785a49aedb15200
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24789159"
---
# <a name="comparison-operators-javascript"></a>Operátory porovnávání (JavaScript)
Vrátí logickou hodnotu udávající výsledek porovnání.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
expression1 comparisonoperator expression2  
```  
  
## <a name="parameters"></a>Parametry  
 `expression1`  
 Jakýkoli výraz.  
  
 `comparisonoperator`  
 Všechny relační operátor.  
  
 `expression2`  
 Jakýkoli výraz.  
  
## <a name="remarks"></a>Poznámky  
 Při porovnávání řetězců, [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] používá znak Unicode hodnotu řetězcového výrazu.  
  
 Následující text popisuje, jak se mají pro různé skupiny operátorů chovat v závislosti na typy a hodnoty `expression1` a `expression2`:  
  
 Relační operátory: `<`, `>`, `<=`,`>=`  
  
-   Pokus o převést i `expression1` a `expression2` do čísla.  
  
-   Pokud jsou oba výrazy řetězce, proveďte porovnání řetězců.  
  
-   Pokud je buď výraz `NaN`, vrátí `false`.  
  
-   Záporné nula rovná kladné nula.  
  
-   Záporné nekonečno je menší než vše, včetně sám sebe.  
  
-   Kladné nekonečno je větší než vše, včetně sám sebe.  
  
 Operátory rovnosti: `==`,`!=`  
  
-   Pokud jsou různé typy dvou výrazů, pokusí se je převést na řetězec, číslo nebo logická hodnota.  
  
-   `NaN`není rovno nic včetně sám sebe.  
  
-   Záporné nula rovná kladné nula.  
  
-   `null`obě rovná `null` a `undefined`.  
  
-   Hodnoty jsou považovány za shodné v případě, že jsou identické řetězce, číselným ekvivalentem čísla, stejný objekt, stejné logické hodnoty, nebo (pokud různé typy) může být převeden do jednoho z těchto situacích.  
  
-   Každý další porovnání se považuje za nerovné.  
  
 Operátory identity: `===`,`!==`  
  
 Tyto operátory chovají stejně jako operátory rovnosti s tím rozdílem, že se provádí žádný převod typů. Pokud typy oba výrazy nejsou stejné, tyto výrazy vždy vrátí `false`.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Priorita operátorů](../../javascript/operator-subtractprecedence-javascript.md)   
 [Souhrn operátorů (JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)