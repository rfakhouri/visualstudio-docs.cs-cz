---
title: "encodeuricomponent – funkce (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: encodeURIComponent
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: encodeURIComponent method
ms.assetid: 8202bce6-1342-40dc-a5ef-ac6d210a7d15
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 56680e9bcfe1de61d8a1eabd0ff8d2eced01d603
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="encodeuricomponent-function-javascript"></a>encodeURIComponent – funkce (JavaScript)
Textový řetězec zakóduje jako platný součástí služby identifikátor URI (Uniform Resource).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
encodeURIComponent(encodedURIString)  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `encodedURIString` argument je hodnotu představující komponentu zakódovaný identifikátor URI.  
  
 `encodeURIComponent` Funkce vrátí zakódovaný identifikátor URI. Pokud předáte výsledek, který má `decodeURIComponent`, je vrácen původní řetězec. Protože `encodeURIComponent` funkce kóduje všechny znaky, buďte opatrní, pokud řetězec představuje cestu, například **/folder1/folder2/default.html**. Znaky lomítko bude být zakódován a nebude platný, pokud odesílá jako požadavek na webový server. Použití `encodeURI` fungovat, pokud řetězec obsahuje více než jedné komponenty identifikátoru URI.  
  
## <a name="example"></a>Příklad  
 Následující kód nejprve kóduje komponenty identifikátoru URI a potom ho dekóduje.  
  
```JavaScript  
var uriEncode = encodeURIComponent ("www.Not a URL.com");  
var uriDecode = decodeURIComponent(uriEncode);  
  
document.write(uriEncode);  
document.write("<br/>");  
document.write(uriDecode);  
  
// Output:  
// www.Not%20a%20URL.com  
// www.Not a URL.com  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [decodeURI – funkce](../../javascript/reference/decodeuri-function-javascript.md)   
 [decodeuricomponent – funkce](../../javascript/reference/decodeuricomponent-function-javascript.md)