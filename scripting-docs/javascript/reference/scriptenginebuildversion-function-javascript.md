---
title: "Scriptenginebuildversion – funkce (JavaScript) | Microsoft Docs"
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
- ScriptEngineBuildVersion
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- ScriptEngineBuildVersion function
ms.assetid: 7e255030-b0a3-420b-9c96-bb3e93c9333f
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fd458d43bebfb0d0e0b2cb6bebb483c22a60b4f0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="scriptenginebuildversion-function-javascript"></a>ScriptEngineBuildVersion – funkce (JavaScript)
Získá číslo verze sestavení skriptovací stroje používán.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
ScriptEngineBuildVersion()  
```  
  
## <a name="remarks"></a>Poznámky  
 Návratová hodnota odpovídá přímo verze informace obsažené v dynamické knihovně (DLL) pro skriptovací jazyk používá.  
  
## <a name="example"></a>Příklad  
 Následující příklad ukazuje použití `ScriptEngineBuildVersion` funkce:  
  
```JavaScript  
if(window.ScriptEngineBuildVersion) {  
    console.log(window.ScriptEngineBuildVersion());  
}  
  
// Output: <current build version>  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [ScriptEngine – funkce](../../javascript/reference/scriptengine-function-javascript.md)   
 [Scriptenginemajorversion – funkce](../../javascript/reference/scriptenginemajorversion-function-javascript.md)   
 [Scriptengineminorversion – funkce](../../javascript/reference/scriptengineminorversion-function-javascript.md)