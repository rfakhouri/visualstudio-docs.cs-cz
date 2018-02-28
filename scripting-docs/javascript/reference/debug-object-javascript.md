---
title: "Debug – objekt (JavaScript) | Microsoft Docs"
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
- debug
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Debug object
- Debug object, about Debug object
ms.assetid: 42a367ec-beb1-4e59-8342-34c326eca042
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6286e5db853daa97e43f36a1467abe90cbced5c8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="debug-object-javascript"></a>Debug – objekt (JavaScript)
Vnitřní globální objekt, který odesílá výstup na ladicí program.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
Debug.function  
```  
  
## <a name="remarks"></a>Poznámky  
 Není vytvoří instanci objektu Debug. Všechny vlastnosti a metody můžete přejít pomocí volání metody `function`.  
  
 Existují různé způsoby k ladění aplikace Internet Explorer a [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace. V [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace, `write` a `writeln` funkce `Debug` objektu řetězců zobrazení v sadě Visual Studio **výstup** okno za běhu. Další informace o ladění [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace, najdete v části [ladění univerzálních aplikací pro Windows v sadě Visual Studio](/visualstudio/debugger/debugging-windows-store-and-windows-universal-apps.md).  
  
 K ladění skriptů aplikace Internet Explorer, musí mít nainstalovaný ladicí program skriptu a skript musí spustit v režimu ladění. Internet Explorer 8 a novější verze zahrnují [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] ladicí program. Pokud používáte starší verzi aplikace Internet Explorer, přečtěte si téma [postupy: povolení a spuštění ladění skriptu z aplikace Internet Explorer](http://go.microsoft.com/fwlink/?LinkId=133801).  
  
 Pokud není probíhá ladění skriptu, funkce nemají žádný vliv.  
  
## <a name="example"></a>Příklad  
 Tento příklad používá `write` funkce Zobrazit hodnotu proměnné.  
  
```JavaScript  
var counter = 42;  
Debug.write("The value of counter is " + counter);  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="constants"></a>Konstanty  
 [Konstanty pro ladění](../../javascript/reference/debug-constants.md)  
  
## <a name="properties"></a>Vlastnosti  
 [Debug.debuggerenabled – vlastnost](../../javascript/reference/debug-debuggerenabled-property.md) &#124; [Debug.setnonusercodeexceptions – vlastnost](../../javascript/reference/debug-setnonusercodeexceptions-property.md)  
  
## <a name="functions"></a>Funkce  
 [Debug.mstraceasynccallbackstarting – funkce](../../javascript/reference/debug-mstraceasynccallbackstarting-function.md) &#124; [Debug.mstraceasynccallbackcompleted – funkce](../../javascript/reference/debug-mstraceasynccallbackcompleted-function.md) &#124; [Debug.mstraceasyncoperationcompleted – funkce](../../javascript/reference/debug-mstraceasyncoperationcompleted-function.md) &#124; [Debug.mstraceasyncoperationstarting – funkce](../../javascript/reference/debug-mstraceasyncoperationstarting-function.md) &#124; [Debug.msupdateasynccallbackrelation – funkce](../../javascript/reference/debug-msupdateasynccallbackrelation-function.md) &#124; [Debug.Write – funkce](../../javascript/reference/debug-write-function-javascript.md) &#124; [Debug.writeln – funkce](../../javascript/reference/debug-writeln-function-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Debugger – příkaz](../../javascript/reference/debugger-statement-javascript.md)