---
title: "endsWith – metoda (String) (JavaScript) | Microsoft Docs"
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
ms.assetid: c7d836e3-bc43-4d1b-be60-0a93beb8b7a2
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dc6d57d501f0f100f069522e4b51666918168fa0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="endswith-method-string-javascript"></a>endsWith – metoda (String) (JavaScript)
Vrátí hodnotu, která určuje, zda řetězec nebo dílčí řetězec končí s jinou zadat řetězec.  
  
## <a name="syntax"></a>Syntaxe  
  
```vb  
  
stringObj.endsWith(str, [, position]);  
```  
  
#### <a name="parameters"></a>Parametry  
 `stringObj`  
 Požadováno. Objekt řetězec pro vyhledávání proti.  
  
 `str`  
 Požadováno. Vyhledávací řetězec  
  
 `position`  
 Volitelné. Pozice prvního znaku, který vyhledávat na objekt řetězce začínající na 0.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud řetězec, který začíná na `position` končí hledaný řetězec `endsWith` metoda vrátí `true`, jinak vrátí hodnotu `false`.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud `str` je `RegExp`, `TypeError` je vyvolána výjimka.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]