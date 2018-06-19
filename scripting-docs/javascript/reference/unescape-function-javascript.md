---
title: unescape – funkce (JavaScript) | Microsoft Docs
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
- unescape
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Unescape method
ms.assetid: 4adf0270-88b5-4d54-8110-d879d6ae97c2
caps.latest.revision: 9
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 96601fc21f47c86aec8c3702a6861c3676aacacf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791940"
---
# <a name="unescape-function-javascript"></a>unescape – funkce (JavaScript)
Dekóduje `String` objekty zakódovaných pomocí `escape` funkce. Zastaralé  
  
## <a name="syntax"></a>Syntaxe  
  
```  
unescape(charString)   
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `charString` argument je `String` objekt nebo literál kódovaný.  
  
 `unescape` Funkce vrátí hodnotu řetězce, který obsahuje obsah `charstring`. Všechny znaky zakódovaných pomocí %*xx* šestnáctkovém formátu jsou nahrazovány jejich ekvivalenty sadu znaků ASCII.  
  
 V kódování znaků **%u** *xxxx* formátu (znaky Unicode) se nahradí znak Unicode s šestnáctkové kódování *xxxx*.  
  
> [!NOTE]
>  `unescape` Funkce nepoužívejte k dekódování identifikátory URI (Uniform Resource). Použití `decodeURI` a `decodeURIComponent` funkce místo.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **Platí pro**: [Global – objekt](../../javascript/reference/global-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [decodeURI – funkce](../../javascript/reference/decodeuri-function-javascript.md)   
 [decodeuricomponent – funkce](../../javascript/reference/decodeuricomponent-function-javascript.md)   
 [Escape – funkce](../../javascript/reference/escape-function-javascript.md)   
 [String – objekt](../../javascript/reference/string-object-javascript.md)