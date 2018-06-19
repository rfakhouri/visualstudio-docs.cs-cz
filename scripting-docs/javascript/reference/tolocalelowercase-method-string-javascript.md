---
title: toLocaleLowerCase – metoda (String) (JavaScript) | Microsoft Docs
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
- toLocaleLowerCase
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toLocaleLowerCase method
ms.assetid: add894d3-d14a-4dbc-a9b9-7ad1d3a2e581
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 642ced387e0d3b4cf763767ec147d6160ed7d36b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24791649"
---
# <a name="tolocalelowercase-method-string-javascript"></a>toLocaleLowerCase – metoda (String) (JavaScript)
Převede všechny znaky abecedy na malá písmena, vezme v úvahu aktuální národní prostředí hostitelském prostředí.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
stringVar.toLocaleLowerCase( )  
```  
  
## <a name="remarks"></a>Poznámky  
 Požadované `stringVar` je odkaz `String` objekt nebo řetězcový literál.  
  
 `toLocaleLowerCase` Metoda převede znaky v řetězci, vezme v úvahu aktuální národní prostředí hostitelském prostředí. Ve většině případů výsledek je stejný jako výsledek `toLowerCase` metoda. Výsledky se liší Pokud pravidla pro jazyk v konfliktu s regulární případy mapování kódování Unicode.  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **Platí pro**: [řetězce objektu](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [tolocaleuppercase – metoda (String)](../../javascript/reference/tolocaleuppercase-method-string-javascript.md)   
 [toLowerCase – metoda](../../javascript/reference/tolowercase-method-javascript.md)