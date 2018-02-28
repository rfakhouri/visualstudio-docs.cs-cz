---
title: "encodeURI – funkce (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- encodeURI
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- encodeURI method
ms.assetid: 17bab5a2-bcd4-46c2-8b52-b2b5a0ed98a3
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8cf9bbdf34c0481c889d1176bc32ab0246a333a4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="encodeuri-function-javascript"></a>encodeURI – funkce (JavaScript)
Textový řetězec zakóduje jako platný identifikátor URI (Uniform Resource)  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
encodeURI(  
URIString  
)  
  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `URIString` argument je hodnotu představující zakódovaný identifikátor URI.  
  
 `encodeURI` Funkce vrátí zakódovaný identifikátor URI. Pokud předáte výsledek, který má `decodeURI`, je vrácen původní řetězec. `encodeURI` Funkce neprovádí kódování následující znaky: ":", "/", ";" a "?". Použití `encodeURIComponent` ke kódování těchto znaků.  
  
## <a name="example"></a>Příklad  
 Následující kód nejprve kóduje a pak dekóduje identifikátoru URI.  
  
```JavaScript  
var uriEncode = encodeURI ("http://www.Not a URL.com");  
var uriDecode = decodeURIComponent(uriEncode);  
  
document.write(uriEncode);  
document.write("<br/>");  
document.write(uriDecode);  
  
// Output:  
// http://www.Not%20a%20URL.com  
// http://www.Not a URL.com  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [decodeURI – funkce](../../javascript/reference/decodeuri-function-javascript.md)   
 [decodeuricomponent – funkce](../../javascript/reference/decodeuricomponent-function-javascript.md)