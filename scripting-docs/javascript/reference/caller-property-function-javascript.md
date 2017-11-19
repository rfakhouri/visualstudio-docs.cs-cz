---
title: "caller – vlastnost (Function) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: caller
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- caller property
- function calls, functions that are executing
ms.assetid: ae210853-7160-4102-9cfd-ab489f180ce1
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8c6eef1b8304612c2ed16a4cc389bf3b2a28b70f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="caller-property-function-javascript"></a>caller – vlastnost (Function) (JavaScript)
Získá funkce, která volá funkci aktuální.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
functionName.caller  
```  
  
## <a name="remarks"></a>Poznámky  
 `functionName` Objektu provádí název žádné funkce.  
  
 `caller` Vlastnost definovaná pro funkci pouze při, provádí funkce. Pokud je tato funkce volána z horní části úroveň [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] programu, `caller` obsahuje `null`.  
  
 Pokud `caller` vlastnost se používá v kontextu řetězec, výsledkem je stejný jako `functionName`.`toString`, to znamená, že se zobrazí decompiled text funkce.  
  
 Následující příklad ukazuje použití `caller` vlastnost:  
  
```JavaScript  
function CallLevel(){  
   if (CallLevel.caller == null)  
      return("CallLevel was called from the top level.");  
   else  
      return("CallLevel was called by another function.");  
}  
  
document.write(CallLevel());  
  
// Output: CallLevel was called from the top level.  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [Function – příkaz](../../javascript/reference/function-statement-javascript.md)