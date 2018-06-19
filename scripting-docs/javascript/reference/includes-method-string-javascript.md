---
title: Includes – metoda (String) (JavaScript) | Microsoft Docs
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
ms.assetid: 2639e4e5-23ba-424a-80ea-be067a4cd65e
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 848143b64d3e32452aea41f08b6f5c57879d3e17
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790617"
---
# <a name="includes-method-string-javascript"></a>includes – metoda (String) (JavaScript)
Vrátí logickou hodnotu, která určuje, zda je předaný řetězec obsažené v objektu řetězce.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
stringObj.includes(substring [, position]);  
```  
  
#### <a name="parameters"></a>Parametry  
 `stringObj`  
 Požadováno. K testování proti objekt řetězce.  
  
 `substring`  
 Požadováno. Řetězec, který chcete otestovat.  
  
 `position`  
 Volitelné. Pozice prvního znaku k testování proti v objektu řetězce, počínaje 0.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud předaný řetězec je součástí objekt řetězce `includes` metoda vrátí `true`, jinak vrátí `false`.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="example"></a>Příklad  
  
```JavaScript  
// Returns true   
"abcde".includes("cd")  
"abcde".includes("cd", 2)  
  
// Returns false  
"abcde".includes("CD")  
"abcde".includes("cd", 3)  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]