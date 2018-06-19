---
title: Debug.writeln – funkce (JavaScript) | Microsoft Docs
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
- writeln
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- writeIn method
ms.assetid: c3aad0cd-0486-4161-9ba6-31d672da72af
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 848760e59632b05605de2d73615a2b025df363da
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24790392"
---
# <a name="debugwriteln-function-javascript"></a>Debug.writeln – funkce (JavaScript)
Odešle řetězců ladicí program skriptu, za nímž následuje znak nového řádku.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
Debug.writeln([str1 [, str2 [, ... [, strN]]]])  
```  
  
## <a name="parameters"></a>Parametry  
 *Str1, str2..., strN*  
 Volitelné. Řetězce k odeslání do skriptu ladicího programu.  
  
## <a name="remarks"></a>Poznámky  
 `Debug.writeln` Funkce odešle řetězce, za nímž následuje znak nového řádku, na okamžitou okno Nástroj Microsoft Script Debugger za běhu. Pokud není probíhá ladění skriptu, `Debug.writeln` funkce nemá žádný vliv.  
  
 `Debug.writeln` Funkce je téměř identický `Debug.write` funkce. Jediným rozdílem je, že `Debug.write` funkce neodesílá po odeslání řetězce znak nového řádku.  
  
## <a name="example"></a>Příklad  
 Tento příklad používá `Debug.writeln` funkce, která se v podokně hodnot proměnných nástroj Microsoft Script Debugger umožňuje zobrazit hodnotu proměnné.  
  
> [!NOTE]
>  Pro spuštění tohoto příkladu, musí mít nainstalovaný ladicí program skriptu a skript musí spustit v režimu ladění.  
>   
>  Internet Explorer 8 zahrnuje [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] ladicí program. Pokud používáte starší verzi aplikace Internet Explorer, přečtěte si téma [postupy: povolení a spuštění ladění skriptu z aplikace Internet Explorer](http://go.microsoft.com/fwlink/?LinkId=133801).  
  
```JavaScript  
var counter = 42;  
Debug.writeln("The value of counter is " + counter);  
```  
  
## <a name="requirements"></a>Požadavky  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **Platí pro**: [Debug – objekt](../../javascript/reference/debug-object-javascript.md)  
  
## <a name="see-also"></a>Viz také  
 [Debug.Write – funkce](../../javascript/reference/debug-write-function-javascript.md)