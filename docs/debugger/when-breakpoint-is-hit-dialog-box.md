---
title: "Když je volána zarážka dialogové | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vs.debug.whenbreakpointishit
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
ms.assetid: 476e3d98-cf35-4338-b124-cd0f3010d854
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: c03e68315c8c0818d6b9cf6a102adde4ea4f8a10
ms.sourcegitcommit: 9e6ff74da1afd8bd2f0e69387ce81f2a74619182
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/04/2018
---
# <a name="when-breakpoint-is-hit-dialog-box"></a>Dialogové okno Při průchodu zarážkou
S toto dialogové okno můžete přizpůsobit akci, která nastane, když je dosaženo zarážky.  
  
## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní  
 **Tisk – zpráva**  
 Vytiskne zprávu pomocí syntaxe DebuggerDisplay. Další informace najdete v tématu [používání atributu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md).  
  
 Tomuto textovému poli také podporuje klíčová speciální slova (například $ADDRESS), které může být použito samostatně nebo do složených závorek DebuggerDisplay výrazu. K dispozici klíčová slova jsou uvedeny v dialogovém okně.  
  
 **Pokračovat v provádění**  
 Tento ovládací prvek je povoleno pouze tehdy, když **vytiskněte zprávu** je vybrána. Pro tento ovládací prvek vybrán zarážku jako tracepoint můžete použít ke sledování vaší spuštění programu, místo pozastavení při umístění přístupů.  
  
## <a name="see-also"></a>Viz také  
 [Použití zarážek](../debugger/using-breakpoints.md)   
 [Používání atributu DebuggerDisplay](../debugger/using-the-debuggerdisplay-attribute.md)