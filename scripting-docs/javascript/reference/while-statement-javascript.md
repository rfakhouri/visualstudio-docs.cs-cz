---
title: while – příkaz (JavaScript) | Microsoft Docs
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
- while_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- loop structures, while statements
- while statement
ms.assetid: d63777cf-0e1a-4555-8d3a-334381001f48
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: de64bf9181a0fc86a528fa7af21216b99530f217
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791886"
---
# <a name="while-statement-javascript"></a>while – příkaz (JavaScript)
Spustí příkaz nebo řadu příkazy, dokud nebude zadanou podmínku `false`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
while (expression) {  
    statements  
}   
```  
  
## <a name="parameters"></a>Parametry  
 `expression`  
 Požadováno. Logický výraz, který je zaškrtnuta možnost před každou iteraci smyčky. Pokud `expression` je `true`, je proveden smyčky. Pokud `expression` je `false`, ukončení smyčky.  
  
 `statements`  
 Volitelné. Jeden nebo více příkazů, které mají být provedeny, pokud `expression` je `true`.  
  
## <a name="remarks"></a>Poznámky  
 `while` Příkaz kontroly `expression` před první provedením smyčku. Pokud `expression` je `false` v tuto chvíli se nikdy spustí smyčky.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `while` příkaz.  
  
```JavaScript  
var i = 0;  
var j = 10;  
while (i < 100) {  
    if (i == j)  
        break;  
    i++;  
}  
document.write(i);  
  
// Output: 10  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Příkaz BREAK](../../javascript/reference/break-statement-javascript.md)   
 [Continue – příkaz](../../javascript/reference/continue-statement-javascript.md)   
 [do... while – příkaz](../../javascript/reference/do-dot-dot-dot-while-statement-javascript.md)   
 [for – příkaz](../../javascript/reference/for-statement-javascript.md)   
 [for... v příkazu](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)