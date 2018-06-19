---
title: startsWith – metoda (String) (JavaScript) | Microsoft Docs
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
ms.assetid: 871def4a-0f96-4675-b6ff-2349f4996511
caps.latest.revision: 2
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 74970a9a3bfe280e91f2df39340732eda8664142
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791550"
---
# <a name="startswith-method-string-javascript"></a>startsWith – metoda (String) (JavaScript)
Vrátí hodnotu, která určuje, zda řetězec nebo dílčí řetězec začíná jiné zadat řetězec.  
  
## <a name="syntax"></a>Syntaxe  
  
```vb  
  
stringObj.startsWith(str, [, position]);  
```  
  
#### <a name="parameters"></a>Parametry  
 `stringObj`  
 Požadováno. Objekt řetězec pro vyhledávání proti.  
  
 `str`  
 Požadováno. Vyhledávací řetězec  
  
 `position`  
 Volitelné. Pozice prvního znaku, který vyhledávat na objekt řetězce začínající na 0.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud řetězec, který začíná na `position` začíná hledaný řetězec `startsWith` metoda vrátí `true`, jinak vrátí `false`.  
  
## <a name="exceptions"></a>Výjimky  
 Pokud `str` je `RegExp`, `TypeError` je vyvolána výjimka.  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]