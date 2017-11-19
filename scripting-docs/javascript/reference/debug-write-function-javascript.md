---
title: "Debug.Write – funkce (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Write
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: write method [JavaScript]
ms.assetid: fd1cfbb3-46cb-47cc-896c-a70d457dd413
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 74aad7a01e0dc166f22173cf193b312e1fd4d804
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="debugwrite-function-javascript"></a>Debug.write – funkce (JavaScript)
Odešle řetězců ladicí program skriptu.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Debug.write([str1 [, str2 [, ... [, strN]]]])  
```  
  
## <a name="parameters"></a>Parametry  
 *Str1, str2..., strN*  
 Volitelné. Řetězce k odeslání do skriptu ladicího programu.  
  
## <a name="remarks"></a>Poznámky  
 `Debug.write` Funkce odešle řetězce hodnot proměnných ladicí program skriptu v době běhu. Pokud není probíhá ladění skriptu, `Debug.write` funkce nemá žádný vliv.  
  
 `Debug.write` Funkce je téměř identický `Debug.writeln` funkce. Jediným rozdílem je, že `Debug.writeln` funkce odešle znak nového řádku po odeslání řetězce.  
  
## <a name="example"></a>Příklad  
 Tento příklad používá `Debug.write` funkce Zobrazit hodnotu proměnné v okně okamžitou nástroje pro ladění skriptů.  
  
> [!NOTE]
>  Pro spuštění tohoto příkladu, musí mít nainstalovaný ladicí program skriptu a skript musí spustit v režimu ladění.  
>   
>  Internet Explorer 8 zahrnuje [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] ladicí program. Pokud používáte starší verzi aplikace Internet Explorer, přečtěte si téma [postupy: povolení a spuštění ladění skriptu z aplikace Internet Explorer](http://go.microsoft.com/fwlink/?LinkId=133801).  
  
```JavaScript  
var counter = 42;  
Debug.write("The value of counter is " + counter);  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [Debug – objekt](../../javascript/reference/debug-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Debug.writeln – funkce](../../javascript/reference/debug-writeln-function-javascript.md)