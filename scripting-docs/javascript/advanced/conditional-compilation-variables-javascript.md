---
title: "Proměnné podmíněné kompilace (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: conditional compilation, variables
ms.assetid: d6f9827d-c558-412c-8e68-de04c19c3d9d
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 900a44dab0ad418cd2899af6423f78016c90fe2b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="conditional-compilation-variables-javascript"></a>Proměnné podmíněné kompilace (JavaScript)
Následující předdefinované proměnné jsou dostupné pro podmíněnou kompilaci. Pokud není proměnné **true**, ho není definována a chová jako `NaN` při přístupu k.  
  
> [!WARNING]
>  Podmíněná kompilace je podporována ve všech verzích aplikace Internet Explorer starších než Internet Explorer 11. Spouštění v režimu Standardy aplikace Internet Explorer 11 a v [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] aplikace, podmíněná kompilace není podporován.  
  
## <a name="variables"></a>Proměnné  
  
|Proměnná|Popis|  
|--------------|-----------------|  
|@_win32|True, je-li program spuštěn v systému Win32.|  
|@_win16|True, je-li program spuštěn v systému Win16.|  
|@_mac|True, je-li program spuštěn v systému Apple Macintosh.|  
|@_alpha|True, je-li program spuštěn na procesoru DEC Alpha.|  
|@_x86|True, je-li program spuštěn na procesoru Intel.|  
|@_mc680x0|True, je-li program spuštěn na procesoru Motorola 680x0.|  
|@_PowerPC|True, je-li program spuštěn na procesoru Motorola PowerPC.|  
|@_jscript|Vždy true.|  
|@_jscript_build|Obsahuje číslo sestavení [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] skriptovacího stroje.|  
|@_jscript_version|Obsahuje [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] číslo verze ve formátu major.minor.|