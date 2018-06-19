---
title: ladicího programu – příkaz (JavaScript) | Microsoft Docs
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
- debugger_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- debugger statement
ms.assetid: c6d2e193-c1f7-4fb3-8a4e-cc9823174ae4
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9e64e860cebd065f357857484e932b4aea3f05ea
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790368"
---
# <a name="debugger-statement-javascript"></a>debugger – příkaz (JavaScript)
Pozastaví spuštění.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
debugger  
```  
  
## <a name="remarks"></a>Poznámky  
 Můžete umístit `debugger` příkazy kdekoli v postupech pozastavit provádění. Pomocí `debugger` příkaz je podobná nastavením zarážky v kódu.  
  
 `debugger` Příkaz pozastaví spuštění, ale nebudou zavřete všechny soubory a zrušte zaškrtnutí všech proměnných.  
  
> [!NOTE]
>  `debugger` Příkaz nemá žádný vliv, pokud je laděné skript.  
  
## <a name="example"></a>Příklad  
 Tento příklad používá `debugger` příkaz pozastavit provádění pro každou iteraci prostřednictvím `for` smyčky.  
  
> [!NOTE]
>  Pro spuštění tohoto příkladu, musí mít nainstalovaný ladicí program skriptu a skript musí spustit v režimu ladění.  
>   
>  Internet Explorer 8 zahrnuje [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] ladicí program. Pokud používáte starší verzi aplikace Internet Explorer, přečtěte si téma [postupy: povolení a spuštění ladění skriptu z aplikace Internet Explorer](http://go.microsoft.com/fwlink/?LinkId=133801).  
  
```JavaScript  
for(i = 1; i<5; i++) {  
   // Print i to the Output window.  
   Debug.write("loop index is " + i);  
   // Wait for user to resume.  
   debugger  
}  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>Viz také  
 [JavaScript – příkazy](../../javascript/reference/javascript-statements.md)   
 [Podmíněná kompilace](../../javascript/advanced/conditional-compilation-javascript.md)