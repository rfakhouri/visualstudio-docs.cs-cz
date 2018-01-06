---
title: "Chyba: Lokality používá IP adresu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.error.webdbg_siteusesipaddress
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: debugger, Web application errors
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e6073fd88221e307b46a90173526876f2e2186d4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="error-site-uses-ip-address"></a>Chyba: Server používá adresu IP
K této chybě dojde, když se ladicí program se pokusí automaticky připojit k webové aplikaci, která používá IP adresu. K tomu dojde, pokud změníte **identifikaci webu** k **použít konkrétní IP adresu** ve službě IIS.  
  
 Pro automatické připojte k práci, budete muset vytvořit projekt s konkrétní IP adresu, nikoli jen název počítače. Ladicí program, jinak se změní název počítače localhost, což způsobí selhání odeslat příkaz debug do služby IIS.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Místo toho připojit pomocí ruční (v nabídce ladění zvolte **připojit k procesu**).  
  
     —nebo—  
  
2.  Změna **identifikace serveru webové služby IIS** nastavení.  
  
## <a name="see-also"></a>Viz také  
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)