---
title: "Math.Sign – funkce (JavaScript) | Microsoft Docs"
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
ms.assetid: 8b462020-ceff-4947-8dd1-c78e6aff8d98
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2cae32118f2265e02c67592facff8e49e8edd633
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="mathsign-function-javascript"></a>Math.sign – funkce (JavaScript)
Vrátí znaménko čísla určující, zda je číslo kladné, záporné nebo 0.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Math.sign(number)  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `number` argument je číselného výrazu, pro kterou je potřeba přihlášení.  
  
 Vrácená hodnota je jedním z těchto:  
  
-   `NaN`, pokud `number` je `NaN`.  
  
-   -0, pokud `number` je – 0.  
  
-   + 0, pokud `number` je + 0.  
  
-   -1, pokud `number` záporné a ne - 0.  
  
-   + 1, pokud `number` kladné a ne + 0.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]