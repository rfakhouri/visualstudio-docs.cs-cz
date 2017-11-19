---
title: "charAt – metoda (String) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: charAt
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- String object, returning characters
- charAt method
- characters, returning part of
ms.assetid: 63173e15-17f6-47c5-8f94-98ef1eb04c1a
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 201d85fec4ba184f0842c7401d986650b9ee078c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="charat-method-string-javascript"></a>charAt – metoda (String) (JavaScript)
Vrátí znak nacházející se na zadaném indexu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
strObj. charAt(index)  
```  
  
## <a name="parameters"></a>Parametry  
 `strObj`  
 Požadováno. Všechny `String` objekt nebo řetězcový literál.  
  
 `index`  
 Požadováno. Index založený na nule požadované znaku.  
  
## <a name="remarks"></a>Poznámky  
 `charAt` Metoda vrátí hodnotu znak rovná znak na zadané `index`. První znak v řetězci je indexem 0, druhý u indexu 1 a tak dále. Hodnoty z `index` které jsou mimo rozsah návratový prázdný řetězec.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `charAt` metoda:  
  
```JavaScript  
var str = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";  
document.write(str.charAt(str.length - 1));  
  
// Output: Z  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [řetězce objektu](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [String – objekt](../../javascript/reference/string-object-javascript.md)