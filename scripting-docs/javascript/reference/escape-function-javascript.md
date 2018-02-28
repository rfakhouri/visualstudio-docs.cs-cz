---
title: "Escape – funkce (JavaScript) | Microsoft Docs"
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
- escape
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- encoding string objects
- Escape method
- hexadecimal
- String object, encoding
ms.assetid: caa92bea-ba69-4109-a68a-6e2debda463a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b53a447ae6dde917c12a4711d9038136dc4500cf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="escape-function-javascript"></a>escape – funkce (JavaScript)
Kóduje řetězce, může být číst na všech počítačích. Zastaralé  
  
## <a name="syntax"></a>Syntaxe  
  
```  
escape(charString)   
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `charString` argument je žádné `String` objekt nebo literál, který je zakódován.  
  
 **Řídicí** funkce vrátí hodnotu řetězce (ve formátu Unicode), který obsahuje obsah `charstring`. Všechny mezery, interpunkční znaménka, akcenty znaky a žádné jiné sady než ASCII znaky jsou nahrazeny `%` *xx* kódování, kde *xx* je ekvivalentní hexadecimální číslo představující znak. Například mezeru se vrátí jako "% 20."  
  
 Znaky s hodnotou vyšší než 255 ukládají pomocí **%u** *xxxx* formátu.  
  
> [!NOTE]
>  **Řídicí** funkce by neměl být použitá ke kódování identifikátory URI (Uniform Resource). Použití `encodeURI` a `encodeURIComponent` funkce místo.  
  
 **Platí pro**: [Global – objekt](../../javascript/reference/global-object-javascript.md)  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [encodeURI – funkce](../../javascript/reference/encodeuri-function-javascript.md)   
 [encodeuricomponent – funkce](../../javascript/reference/encodeuricomponent-function-javascript.md)   
 [String – objekt](../../javascript/reference/string-object-javascript.md)   
 [unescape – funkce](../../javascript/reference/unescape-function-javascript.md)