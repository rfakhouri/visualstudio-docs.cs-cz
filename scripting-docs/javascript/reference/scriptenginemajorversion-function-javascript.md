---
title: "Scriptenginemajorversion – funkce (JavaScript) | Microsoft Docs"
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
- ScriptEngineMajorVersion
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- ScriptEngineMajorVersion function
ms.assetid: 3e251bce-1e14-4cb5-b79f-53845d1920fd
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 815e6fb92744fc2145cae2cbaa6a5574c3ea3ecc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="scriptenginemajorversion-function-javascript"></a>ScriptEngineMajorVersion – funkce (JavaScript)
Získá hlavní číslo verze skriptovací stroje používán.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
ScriptEngineMajorVersion()  
```  
  
## <a name="remarks"></a>Poznámky  
 Návratová hodnota odpovídá přímo verze informace obsažené v dynamické knihovně (DLL) pro skriptovací jazyk používá.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `ScriptEngineMajorVersion` funkce:  
  
```JavaScript  
if (window.ScriptEngineMajorVersion) {  
    console.log(window.ScriptEngine());   
}  
  
Output: <current major version>  
  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [ScriptEngine – funkce](../../javascript/reference/scriptengine-function-javascript.md)   
 [Scriptenginebuildversion – funkce](../../javascript/reference/scriptenginebuildversion-function-javascript.md)   
 [Scriptengineminorversion – funkce](../../javascript/reference/scriptengineminorversion-function-javascript.md)