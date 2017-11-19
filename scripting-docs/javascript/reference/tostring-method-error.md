---
title: "toString – metoda (Error) | Microsoft Docs"
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
ms.assetid: 5d6d9712-c06d-4b31-9bc9-e46f6bb5cd38
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d774ff8c0f5338f4178b2262bf8ac8cadc074453
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="tostring-method-error"></a>toString – metoda (Error)
Vrátí řetězcovou reprezentaci k chybě.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
error.toString()  
```  
  
## <a name="parameters"></a>Parametry  
 `date`  
 Požadováno. Chyba představují jako řetězec.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí "Chyba:" plus chybovou zprávu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `toString` metoda s chybou.  
  
```JavaScript  
var myError = new Error();  
myError.message = "My Error";  
var errorString = myError.toString();  
document.write(errorString);  
  
// Output: Error: My Error  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]