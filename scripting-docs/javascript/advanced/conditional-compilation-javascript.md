---
title: "Podmíněná kompilace (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ConditionalComp_JavaScript
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- conditional compilation, overview
- conditional compilation
ms.assetid: a843de4e-3aae-43cd-ad64-477dd00814a2
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6d6a5987b21afcab8c62a609dfba33f963d544de
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="conditional-compilation-javascript"></a>Podmíněná kompilace (JavaScript)
Podmíněná kompilace umožňuje využívat nové [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] funkce jazyka, aniž by došlo ke ztrátě kompatibilitu s starší verze, které nepodporují funkce.  
  
> [!WARNING]
>  Podmíněná kompilace je podporována ve všech verzích aplikace Internet Explorer starších než Internet Explorer 11. Spouštění v režimu Standardy aplikace Internet Explorer 11 a v [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace, podmíněná kompilace není podporován.  
  
## <a name="statements"></a>Příkazy  
 Podmíněná kompilace je aktivovat pomocí `@cc_on` příkaz nebo pomocí `@if` nebo `@set` příkaz. Některé typické použití Podmíněná kompilace patří použití nových funkcí v [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]vložení podporu ladění do skriptu a trasování provádění kódu.  
  
 Kód podmíněné kompilace vždy umístěte do komentářů, aby jej hostitelské aplikace (jako Netscape Navigator), které nepodporují podmíněnou kompilaci, ignorovaly. Zde je příklad.  
  
```JavaScript  
/*@cc_on @*/  
/*@if (@_jscript_version >= 4)  
    alert("JavaScript version 4 or better");  
    @else @*/  
    alert("Conditional compilation not supported by this scripting engine.");  
/*@end @*/  
```  
  
 Tento příklad používá oddělovače speciální komentáře, které se používají pouze v případě, že je aktivován Podmíněná kompilace `@cc_on` příkaz. Skriptovací jádra, která nepodporují podmíněnou kompilaci, vidí pouze zprávu, že podmíněná kompilace není podporována.