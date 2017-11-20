---
title: "ScriptEngine – funkce (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: ScriptEngine
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: ScriptEngine function
ms.assetid: 65674b2b-d2c2-4493-99b3-f0d20fda8249
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d441fcce065677f7b673a9979acff9cf9aa2ce90
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="scriptengine-function-javascript"></a>ScriptEngine – funkce (JavaScript)
Získá název skriptovací jazyk používán.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
ScriptEngine()  
```  
  
## <a name="remarks"></a>Poznámky  
 `ScriptEngine` Funkce vrátí "JScript", což znamená, že [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] je aktuální skriptovacího stroje.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `ScriptEngine` funkce:  
  
```JavaScript  
if (window.ScriptEngine) {  
    console.log(window.ScriptEngine());  
}  
  
// Output: JScript  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Scriptenginebuildversion – funkce](../../javascript/reference/scriptenginebuildversion-function-javascript.md)   
 [Scriptenginemajorversion – funkce](../../javascript/reference/scriptenginemajorversion-function-javascript.md)   
 [Scriptengineminorversion – funkce](../../javascript/reference/scriptengineminorversion-function-javascript.md)