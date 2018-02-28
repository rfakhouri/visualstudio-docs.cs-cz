---
title: "var – příkaz (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/22/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- var_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- declaring variables, var statement
- var statement
ms.assetid: 56f900af-a5c4-4667-9664-5956d30f0aae
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 839b6904fa59b6f4ea9a5c4d8e00213cd351517a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="var-statement-javascript"></a>var – příkaz (JavaScript)
Deklaruje proměnnou.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
var variable1 = value1  
```  
  
## <a name="parameters"></a>Parametry  
 `variable1`  
 Název proměnné se deklarovat.  
  
 `value1`  
 Počáteční hodnotu přiřazenou proměnné.  
  
## <a name="remarks"></a>Poznámky  
 Použití `var` příkaz deklarovat proměnné. Můžete přiřadit hodnoty proměnných, když je deklarujete nebo později ve vašem skriptu.  
  
 Proměnné je deklarovaná první zobrazí se ve vašem skriptu.  
  
 Je možné deklarovat proměnnou bez použití `var` – klíčové slovo a přiřadit hodnotu k ní. To se označuje jako *implicitní deklarace*, a nedoporučuje. Implicitní deklarace přiřadí proměnné globálním oboru. Po deklarování proměnné na úrovni postup, ale obvykle nechcete, aby mohla mít globální obor. Abyste se vyhnuli, nastavení globální proměnné rozsahu, je nutné použít `var` – klíčové slovo v vaší deklarace proměnné.  
  
 Pokud není inicializovat vaše proměnná v `var` příkaz, je automaticky přiřazen [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] hodnotu `undefined`.  
  
## <a name="example"></a>Příklad  
 Následující příklady ilustrují použití `var` příkaz.  
  
```JavaScript  
var index;  
var name = "Thomas Jefferson";  
var answer = 42, counter, numpages = 10;  
var myarray = new Array();  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Function – příkaz](../../javascript/reference/function-statement-javascript.md)   
 [New – operátor](../../javascript/reference/new-operator-decrementjavascript.md)   
 [Array – objekt](../../javascript/reference/array-object-javascript.md)   
 [Proměnné](../../javascript/variables-javascript.md)