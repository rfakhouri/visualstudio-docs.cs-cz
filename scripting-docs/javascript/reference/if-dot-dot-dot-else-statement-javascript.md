---
title: If... else – příkaz (JavaScript) | Microsoft Docs
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
- else_JavaScriptKeyword
- if_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- if statement, if...else
- loop structures, if...else statements
ms.assetid: dfbe86e8-9c1e-4ef5-bb9c-7d1db7ce2506
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fad12b970f69a15040acb59195f957a2a6eec3e0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790707"
---
# <a name="ifelse-statement-javascript"></a>if...else – příkaz (JavaScript)
Podmíněně spustí skupinu příkazů v závislosti na hodnotě výrazu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
if (condition1) {  
    statement1  
}  
[else if (condition2) {  
    statement2  
}]  
[else {  
    statement3]   
}]  
```  
  
## <a name="parameters"></a>Parametry  
 `condition1`  
 Požadováno. Logický výraz. Pokud `condition1` je `null` nebo `undefined`, `condition1` je považován za `false`.  
  
 `statement1`  
 Volitelné. Příkaz tak, aby provést, pokud `condition1` je **true**. Může být složený příkaz.  
  
 `condition2`  
 Podmínku, která má být vyhodnocen.  
  
 `statement2`  
 Volitelné. Příkaz tak, aby provést, pokud `condition2` je `true`. Může být složený příkaz.  
  
 `statement3`  
 Pokud oba `condition1` a `condition2` jsou `false`, je-li spustit tento příkaz.  
  
## <a name="example"></a>Příklad  
 Následující kód ukazuje, jak používat `if`, `if else`, a `else`.  
  
 Je dobrým zvykem uzavřete `statement1` a `statement2` v závorkách ({}) pro přehlednost a aby se zabránilo nechtěnému chyby.  
  
```JavaScript  
var z = 3;  
if (x == 5) {  
    z = 10;  
}  
else if (x == 10) {  
    z = 15;  
}  
else {  
    z = 20;  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Podmíněný (Ternární) operátor (?:)](../../javascript/reference/conditional-ternary-operator-decrement-javascript.md)