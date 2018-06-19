---
title: valueOf – metoda (Error) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ca25c57d-c9ad-445b-8235-561390de680c
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c7593937530469142265f8081bf3472fa4935aee
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791568"
---
# <a name="valueof-method-error"></a>valueOf – metoda (Error)
Vrátí hodnotu řetězce k chybě.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
error.valueOf()  
```  
  
#### <a name="parameters"></a>Parametry  
 `error` Je objekt všech instancí k chybě.  
  
## <a name="return-value"></a>Návratová hodnota  
 Řetězec "Chyba:" plus chybovou zprávu.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `valueOF` metoda s datem.  
  
```JavaScript  
var myError = new Error();  
myError.message = "This is an error.";  
var value = myError.valueOf();  
document.write(value);  
  
// Output: Error: This is an error.  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]