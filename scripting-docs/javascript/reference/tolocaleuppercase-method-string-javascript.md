---
title: "tolocaleuppercase – metoda (String) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: toLocaleUpperCase
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: toLocaleUpperCase method
ms.assetid: e927adb6-475e-44b2-91f7-cedda10a39b0
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 07a89560dde0319598da30fc3451524112b99eac
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="tolocaleuppercase-method-string-javascript"></a>toLocaleUpperCase – metoda (String) (JavaScript)
Vrátí řetězec, kde všechny znaky abecedy byl převeden na velká písmena, s ohledem na účet hostitele prostředí aktuální národní prostředí.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
stringVar.toLocaleUpperCase( )  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `stringVar` je odkaz `String` objekt nebo řetězcový literál.  
  
 `toLocaleUpperCase` Metoda převede znaky v řetězci, vezme v úvahu aktuální národní prostředí hostitelském prostředí. Ve většině případů výsledek je stejný jako výsledek `toUpperCase` metoda. Výsledky se liší Pokud pravidla pro jazyk v konfliktu s regulární případy mapování kódování Unicode.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Platí pro**: [řetězce objektu](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [toLocaleLowerCase – metoda (String)](../../javascript/reference/tolocalelowercase-method-string-javascript.md)   
 [toUpperCase – metoda (String)](../../javascript/reference/touppercase-method-string-javascript.md)