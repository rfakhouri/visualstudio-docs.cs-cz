---
title: 'Chyba: Server používá adresu IP | Dokumentace Microsoftu'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.webdbg_siteusesipaddress
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 66e63a85ecbf42d0d4091a7ce9315c91184078ea
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53871366"
---
# <a name="error-site-uses-ip-address"></a>Chyba: Server používá adresu IP
K této chybě dochází, když se ladicí program se pokusí o automatické připojení k webové aplikaci, která používá IP adresu. K tomu dojde, pokud změníte **identifikaci webu** k **použít konkrétní IP adresu** ve službě IIS.  
  
 Pro automatické připojení k práci, je potřeba vytvořit projekt s konkrétní IP adresu, nikoli jen název počítače. Ladicí program v opačném případě se změní název počítače na místního hostitele, což způsobí selhání odeslat příkaz debug. do služby IIS.  
  
### <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Použití ručně připojit místo toho (v nabídce ladění zvolte **připojit k procesu**).  
  
     —nebo—  
  
2.  Změnit **identifikace serveru služby IIS** nastavení.  
  
## <a name="see-also"></a>Viz také  
 [Ladění webových aplikací: Chyby a řešení potíží](../debugger/debugging-web-applications-errors-and-troubleshooting.md)