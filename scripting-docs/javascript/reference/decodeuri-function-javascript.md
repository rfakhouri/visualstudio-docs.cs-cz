---
title: decodeURI – funkce (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- decodeURI
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- decodeURI method
ms.assetid: af6c81dc-10f4-4243-a7ce-d18ae3ea0fb8
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 97291142083ae88c7dc84d9cd08af5c3c39ff9e8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790380"
---
# <a name="decodeuri-function-javascript"></a>decodeURI – funkce (JavaScript)
Získá nekódovaného verzi z zakódovaný identifikátor URI (Uniform Resource).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
decodeURI(URIstring)  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `URIstring` argument je hodnotu představující zakódovaný identifikátor URI.  
  
 Použití `decodeURI` funkce místo nepoužívané `unescape` funkce.  
  
 `decodeURI` Funkce vrátí hodnotu řetězce.  
  
 Pokud `URIString` není platný, nastane chyba URIError.  
  
 **Platí pro**: [Global – objekt](../../javascript/reference/global-object-javascript.md)  
  
## <a name="example"></a>Příklad  
 Následující kód nejprve kóduje komponenty identifikátoru URI a potom ho dekóduje.  
  
```JavaScript  
var uriEncode = encodeURIComponent ("www.Not a URL.com");  
var uriDecode = decodeURIComponent(uriEncode);  
  
document.write (uriEncode);  
document.write ("<br/>");  
document.write (uriDecode);  
  
// Output:  
// www.Not%20a%20URL.com  
// www.Not a URL.com  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [decodeuricomponent – funkce](../../javascript/reference/decodeuricomponent-function-javascript.md)   
 [encodeURI – funkce](../../javascript/reference/encodeuri-function-javascript.md)   
 [Global – objekt](../../javascript/reference/global-object-javascript.md)